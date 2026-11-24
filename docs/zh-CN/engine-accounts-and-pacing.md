[← SailorBridge](README.md)

# 引擎账号与限速

Agent 使用你在机器上登录的引擎账号。你可以查看团队能用哪些账号、还剩多少额度，以及工作何时恢复。SailorBridge 套餐决定可同时运行的 Agent 数量。可用模型和额度由引擎提供商决定。

## 查找或添加账号

1. 在要运行引擎的机器上登录 Claude Code 或 Codex。运行 `sail account list`。默认登录会被自动识别。它的名称通常是引擎名，后接 `@` 和机器名。
2. 要添加另一个登录，请在单独的账号目录中登录引擎。运行 `sail account add <name> <directory>`，指定该目录和一个在该机器上唯一、长度为 1–64 个字符且没有空格或斜杠的名称。例如，如果第二个登录在相应目录中，可运行 `sail account add work "$HOME/codex-work"`。下次读取额度时会识别它，无需重启。
3. 打开 **资源**，再打开 **账号**。选择账号，查看其所在机器、额度和可用模型。不同机器上同一引擎以相同名称上报的账号会显示在同一行。登录目录、邮箱和凭证留在机器上。

Codex 支持订阅登录。Claude Code 支持订阅登录或 API 密钥。Gemini CLI、Copilot CLI、OpenCode、Qwen Code 和 Pi 仅支持账号登记和本机检查。这 5 种引擎中，Gemini CLI 和 OpenCode 支持识别单独命名的目录。

## 使用兼容 Claude 的端点

如要使用 DeepSeek 或 GLM 等提供商，请在机器上单独配置一个 Claude Code 账号目录。在该目录的 `settings.json` 中，将提供商的基础 URL 填入 `env.ANTHROPIC_BASE_URL`，将凭证填入 `env.ANTHROPIC_API_KEY` 或 `env.ANTHROPIC_AUTH_TOKEN`。在同一 `env` 对象中，将 `ANTHROPIC_MODEL` 设置为提供商的模型名称。你还可以分别用 `ANTHROPIC_DEFAULT_OPUS_MODEL`、`ANTHROPIC_DEFAULT_SONNET_MODEL` 和 `ANTHROPIC_DEFAULT_HAIKU_MODEL` 映射 Opus、Sonnet 和 Haiku 系列。

在这台机器上运行 `sail account add <name> <directory>`，使用你选定的名称和路径。账号通过 Claude Code 运行。打开 **可用模型**，查看从目录中读到的模型名称。端点模型采用上述映射，没有推理强度设置。任务详情会显示实际运行的模型。

## 用模板配置 GLM、DeepSeek 或 Kimi 账号

`sail account create` 会在本机写入 Claude Code 配置文件，其中包含提供商的端点、高中低 3 档的建议模型，以及密钥占位符。命令不会询问、读取或发送你的密钥，也不会登记账号。

要配置 GLM，请在打算使用该账号的机器上运行以下命令。

```sh
sail account create glm
```

命令会输出 3 行。这里的 `~` 代表你的用户主目录。

```text
建议模型（Opus/Fable、Sonnet、Haiku/子代理）：glm-5.3、glm-5.2、glm-5.3-flash。
三个不同的模型 ID。Sonnet 是建议的中档。
编辑 ~/.sailorbridge/account-templates/glm/settings.json，把占位符换成自己的 API 密钥，再运行 sail account add <name> ~/.sailorbridge/account-templates/glm。
```

生成的 `settings.json` 包含以下模板。

```json
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "REPLACE_WITH_YOUR_API_KEY",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "ANTHROPIC_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-5.2",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-5.3-flash",
    "ANTHROPIC_DEFAULT_FABLE_MODEL": "glm-5.3",
    "CLAUDE_CODE_SUBAGENT_MODEL": "glm-5.3-flash"
  }
}
```

用文本编辑器打开该文件，例如 `nano`。

```sh
nano ~/.sailorbridge/account-templates/glm/settings.json
```

将 `REPLACE_WITH_YOUR_API_KEY` 替换为你自己的 GLM 密钥，保留引号并保存文件。用你选定的名称登记该目录。本例用 `glm`。名称在这台机器上须唯一，长度为 1–64 个字符，不得包含空白字符或 `/`。

```sh
sail account add glm ~/.sailorbridge/account-templates/glm
sail account list
```

在终端的列表中查找 `glm`。机器上报账号后，在应用中打开 **资源**，再打开 **账号**。选择 `glm`，查看它的 **可用模型**。

对于 DeepSeek 或 Kimi，先运行对应提供商的命令。打开命令显示的 `settings.json` 路径，将占位符替换为该提供商的密钥。使用输出的 `sail account add` 命令和你选定的名称，再用 `sail account list` 检查。

| 生成模板的命令 | 文件中的端点 | 输出的建议模型 |
| --- | --- | --- |
| `sail account create deepseek` | `https://api.deepseek.com/anthropic` | 高档使用 `deepseek-v4-pro`，中档和低档共用 `deepseek-flash`。 |
| `sail account create kimi` | `https://api.kimi.com/coding/` | 使用 Kimi Coding Plan 密钥。3 个档位均使用 `k3.1-pro[1m]`。 |

MiniMax 需要指定 `--region international` 或 `--region china`。GLM、DeepSeek 和 Kimi 不接受 `--region`。

## 查看额度并为自己预留一部分

在 **账号** 中打开账号。结合查看 **额度**、**重置** 和 **读数于**。订阅的读数可能显示 5 小时窗口、周窗口，或特定模型的每周额度。Codex 上报其标准的每周额度池。读取额度不消耗模型 token。读取失败时，最多 1 小时前的成功读数仍可能显示，并会标记为旧读数。没有读数时会显示原因，账号仍可能接活。

- **能用** 控制你所有团队是否可向该账号分配新工作。关闭后，已在运行的工作可以完成。
- **预留线** 为你自己保留一定百分比的额度。可在 0% 到 100% 之间以 5 个百分点为步长设置。对于超过 1 天的窗口，剩余额度降到该比例或更低时，工人和 **小组长** 都停止使用该账号。短窗口可用完全部额度。
- 对于按费用计量的账号，用 **每月上限** 设置这台机器在一个自然月内可花费的最大金额。例如 DeepSeek 适用这一设置。GLM 会提供自己的额度读数。达到上限后，新工作会等到下月 1 日 UTC 零点，除非你提高上限。已经开始的步骤可以完成，即使超出上限。同一账号登记在多台机器上时，每台机器单独统计开支。如果出现 **费用不可计算**，你可以看到 token 数，上限无法生效。
- Claude 或 Codex 上报时会显示 **重置券**。打开一张重置券，查看它重置的范围及有效期，再选择 **兑换** 并确认。从账号列表选择 **兑换重置** 会使用最先到期且可用的重置券。持有账号的机器会执行重置。先检查结果，再使用另一张券。

## 为一个团队选择账号和模型

从团队聊天室菜单打开 **账号列表**。默认包含团队机器上的账号。把 **用途** 设置为 **都可**、**只写** 或 **只审**，控制哪些工人步骤能使用账号。用 **仅小组长用** 将它保留给该团的聊天。**移出本团** 和 **加号进本团** 可以更改账号在该团的可用性。

在 **团队详情** 中打开派发设置。在 **小组长模型** 下，选择团队机器上一个启用的账号，再选择检测到的模型和可用的推理强度。选择另一台机器的账号，会让 **小组长** 从下一条消息起转到那里。如果选定的账号无法运行，回复会注明改用的引擎和模型。

对于工人，在团队的模型设置里为各难度和引擎设置首选模型与推理强度。流程的撰写和审查选项决定使用哪个引擎。采用自动审查时，审查者会尽量避开写手实际使用的模型系列。如果流程指定的引擎在团队里没有符合该角色的账号，该次任务可改用自动选择。任务详情会说明变化。

一件任务需要一台能够完成全部步骤的机器。在这台机器上，每个步骤都会使用已启用且允许用于相应引擎和角色的账号。在符合条件的账号中，优先使用等待续登录的账号。其次是 1 天内重置的账号，按重置时间从早到晚选择。重置时间更远时，综合考虑可用额度、套餐容量和距重置的时间。没有读数的账号排在最后。增量审查或改动不超过 120 行的首次审查，优先用仍有余量的较小套餐。

## 设置新工作领取速度

打开 **资源**，再打开 **限速方式**。默认的 **按额度限速** 会将工作分摊到整个额度窗口。如果使用百分比比已用时间百分比高 100/7 个百分点以上（约 14.3），且时间窗口还剩超过七分之一，则该账号用得过快。如果所有可用账号都用得过快，机器会等待再领新任务。已运行的任务和与 **小组长** 的聊天仍可继续。

选择 **不限速**，让所有团队领取新任务时无需等待回到限速线内。账号的预留阈值和额度已用完的窗口仍然适用。如果某个账号被你的任一团队选为 **小组长** 的账号，且在账号级窗口内只剩不到 10% 的额度，工人会将它留给聊天。可以在同一页切回 **按额度限速**。

## 遇到问题时

- 如果模板文件已存在，命令不会覆盖，并会显示路径。编辑现有文件再登记它所在的目录。
- 如果命令拒绝使用目录，请检查它显示的路径。目录必须属于当前用户且权限为 `0700`，这样只有你能访问。确认所有者和权限正确后，再次运行生成模板的命令。
- `sail uninstall` 会删除 `~/.sailorbridge/`，包括这些配置文件，请在别处另存一份密钥。
- 如果登记失败，请按终端显示的命令登录到你提供的目录。该目录必须只对应一种引擎。用 `sail account list` 检查名称。要撤销登记或忽略默认登录，运行 `sail account remove <name>`。本地凭证会保留。要重新识别默认登录，运行 `sail account restore claude` 或 `sail account restore codex`，也可以打开机器的 **已忽略的登录** 并选择 **恢复**。
- 对于 **登录已过期**，请在指定机器上重新登录。对于 **登录待续期**，机器会尝试续登录。对于 **网络不可用**，请检查该机器的网络连接。如果提供商限流或不可用，稍后会重试。模型选择器中的账号若显示 **还没读到模型**，请等待读数，或选择已检测到模型的账号。
- 如果团队拒绝移除其 **小组长** 的账号，先在 **小组长模型** 下选择另一个账号。如果任务缺少写手或审查者，请在详情中选择 **去账号**，并在能完成整件任务的机器上启用缺失角色的账号。
- 打开 **任务列表**，阅读 **为什么没在跑**。限速等待会给出预估时间。你可以等待，或确认对所有团队使用 **切到不限速**。用尽可用账号额度的任务会在同一机器上等待，并在显示的时间重新检查。登录或恢复额度后会自动继续。
