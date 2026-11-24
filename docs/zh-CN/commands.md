[← SailorBridge](README.md)

# 命令

在团队聊天室向 **小组长** 提出请求或启动流程。在终端用 `sail` 管理安装了它的机器、查看团队工作，或在同一团队的另一台机器上运行命令。

## 在团队聊天室选择命令

打开团队的 **聊天** 并输入 `/`。菜单依次列出 4 个快捷命令、团队已启用的流程，最后是 `/clear`。选择一项，用自己的语言补充请求并发送。命令名称保持英文。选择 `/clear` 会立即生效。

| 输入内容 | 结果 |
| --- | --- |
| `/job #12 What is this waiting for?` | **小组长** 会收到任务 12 和你的问题。 |
| `/event #6 Move this to weekdays.` | **小组长** 会收到定时事件 6 和你要求的改动。 |
| `/memory #3 When does this apply?` | **小组长** 会收到记忆条目 3 和你的问题。 |
| `/do Check the current branch.` | **小组长** 会在本轮聊天中执行工作并报告结果，包括未能完成的事项。 |
| `/clear` | 隐藏该团队聊天室中之前的消息，开始新对话。 |

使用相应团队列表中的编号。任务、事件和记忆分别编号。详情页上的 **去聊天室** 会填好对应的快捷命令和编号。要按名称指定机器，输入 `@` 并从团队列表中选择。

## 按名称运行流程

| 命令 | 结果 |
| --- | --- |
| `/ask` | 每次问一个问题，最后在聊天中给出需求说明。 |
| `/plan` | 启动规划任务。读完计划后，决定是否将提议的任务加入队列。 |
| `/agent` | 由一个工人完成任务并报告结果。 |
| `/write-review` | 由写手执行工作、运行检查，并按流程的审查设置修改结果。 |
| `/memory-tidy` | 启动任务，检查、合并或删除团队记忆条目。 |
| `/docs-tidy` | 启动任务，检查项目文档并报告需要你判断的问题。 |
| `/code-sweep` | 进行只读检查，列出带编号的清理任务供你选择执行。 |
| `/write-flow` | 描述可重复的任务。运行成功后，新流程会保存到此团队。 |
| `/edit-flow` | 给出流程名称和改动。成功修改后，会替换自定义流程。修改内置流程会以新名称创建自定义流程。 |

例如，发送 `/agent Count the top-level files in this project.`。自行发送后台流程命令即授权执行任务。**小组长** 会根据对话编写任务说明。如果启用了 **直接起**，你的原话会直接进入队列。在聊天中的任务条目上打开 **看详情** 以跟进进度。**小组长** 在普通聊天中提出后台流程时，先读确认卡，再选择 **对,做** 启动。[流程与定时事件](flows-and-scheduled-events.md)

## 配对、检查或移除机器

| 终端命令 | 使用场景 |
| --- | --- |
| `sail login` | 安装命令会代为运行它。再次运行可获取新的配对码，或使用现有凭证恢复同一地址的服务。 |
| `sail host status` | 检查配对、连接、服务、版本和日志位置。加上 `--trust` 可以查看已保存的服务器密钥指纹。 |
| `sail --version` | 显示已安装的版本。 |
| `sail upgrade` | 立即检查更新。结果会说明是否装了新版本、是否已经是最新版，或更新是否失败。 |
| `sail host service status` | 检查后台服务。用 `sail host service install` 安装、用 `sail host service restart` 重启、用 `sail host service stop` 停止服务。 |
| `sail host run` | 在没有其他实例运行时，在前台运行机器服务。 |
| `sail confirm` | 在 **确认是你** 页面，从已配对机器的终端获取一次性登录验证码。 |
| `sail recover` | 在 **忘了密码?** 页面，从已配对机器的终端获取船长号和一次性密码恢复码。 |
| `sail uninstall` | 移除 SailorBridge 及其本地数据，包括工作副本和日志。保留你自己的项目目录和引擎登录。 |

对于引擎登录，`sail account list` 会列出这台机器识别到的账号。用 `sail account add <name> <directory>` 登记登录目录，用 `sail account remove <name>` 移除登记或忽略默认登录，用 `sail account restore <provider>` 重新识别已忽略的默认登录。对于兼容端点，`sail account create <provider>` 会在 `~/.sailorbridge/` 下生成配置模板，`sail uninstall` 会删除该目录。[用模板配置 GLM、DeepSeek 或 Kimi 账号](engine-accounts-and-pacing.md#用模板配置-glmdeepseek-或-kimi-账号)

## 操作带编号的团队条目

在已配对机器的终端，进入为团队配置的项目目录，再运行以下命令。使用你团队里的条目编号。例如，在聊天中显示为 `#12` 的任务，在终端命令中写作 `12`。

| 操作 | 可在终端运行的命令 |
| --- | --- |
| 查找任务 | `sail job list` 列出尚未结束的任务。加上 `--all` 可包含已结束的任务。`sail job get 12` 显示任务 12。加上 `--json` 可查看完整详情。 |
| 停止或删除任务 | `sail job stop 12` 停止任务。`sail job delete 12` 删除已结束的任务记录。 |
| 查找事件 | `sail event list` 列出已启用且仍待触发的事件。加上 `--all` 可包含已停用或已完成的事件。`sail event get 6` 显示消息和时间安排。 |
| 删除事件 | `sail event delete 6` 移除定时事件。 |
| 删除记忆 | `sail memory delete 3` 永久删除条目。要删除锁定的条目，请使用应用中的 **团队记忆**。 |

以下命令需要正在运行的 **小组长** 会话或任务。即使在团队目录中，直接从终端运行也会返回 `local_team_context_missing`。请在团队聊天室向 **小组长** 提出请求。要自行操作现有条目，可在应用中打开 **任务列表**、**定时事件** 或 **团队记忆**。工人对任务和事件只有读取权限。

| 执行者 | 操作和命令 |
| --- | --- |
| **小组长** | `sail job create <flow> "<task>"` 将后台流程加入队列。`sail job edit 12 "<revised task>"` 修改未结束的任务。`sail job retry 12` 以同一编号继续符合条件的任务。 |
| **小组长** | `sail event create "Check the queue" --weekdays 09:00` 按机器的时区设置一条团队定时消息。其他时间安排使用 `--once`、`--daily` 或 `--every`。用 `--tz` 指定时区。`sail event edit 6 --disable` 暂停该事件。 |
| **小组长** 或工人 | `sail memory list` 列出条目。`sail memory titles` 列出标题。`sail memory search "release checklist"` 返回最多 10 条匹配结果。`sail memory get 3` 读取条目。 |
| **小组长** 或工人 | `sail memory create "<title>" "<body>"` 记录事实，或用同一标题提交更正。`sail memory edit 3 "<body>"` 修改条目。`sail memory conflicts` 列出未解决的冲突。 |
| **小组长** | `sail memory resolve <id> --value "<correct text>"` 解决冲突，参数为冲突 ID。锁定条目需要你在 **团队记忆** 中作决定。 |
| **小组长** 或工人 | `sail memory list --tidy` 列出候选条目及其版本。`sail memory review 3 --rev <version>` 将条目标记为值得保留。`sail memory merge` 接受多组 `--entry <id>:<version>` 参数以及 `--title` 和 `--body`。工人的任务中，只有 `/memory-tidy` 可以删除条目。 |

如果命令报告有待决定的事项，请先核对回复中的当前值，再判断改动是否生效。

## 在本机或团队的另一台机器上运行命令

在本机运行时，`sail run git status` 会把输出发回终端。对于耗时较长、无需交互的命令，请在命令前加 `--fold`。你会得到结果、输出的最后几行和完整日志的路径。对于本机的 tmux 窗口，`sail tmux read <window>` 显示其文本。`sail tmux send <window> "<text>"` 填入内容。要提交输入时，再发送 `sail tmux send <window> --key Enter`。

要在同一团队中另一台你拥有的机器上执行命令，请从团队目录运行，并把 `build-machine` 换成目标机器的名字。例如，`sail exec build-machine git status --short` 会在目标机器上该团队的目录中执行。终端会收到退出码和合并输出的最后 40 行，输出最多 16 KiB。要得到单个 JSON 结果，请把 `--json` 放在机器名前。

默认时限为 5 分钟。要更改时限，请在机器名前加 `--timeout` 和正数秒数。一台发送机器最多可有 8 条命令等待结果。按 Ctrl-C 让终端停止等待。远端命令可能仍在运行。

## 遇到问题时

- 如果无法识别聊天命令，输入 `/` 并选择已启用的流程。如果旧确认卡指向已停用的流程，请在 **团队流程** 中启用它，或选用可用的流程重新发送请求。
- 如果找不到带编号的快捷命令所指的条目，请打开该团队的 **任务列表**、**定时事件** 或 **团队记忆**。核对编号，在聊天中带上 `#`。
- 如果 `sail exec` 无法识别团队，请切换到列出的任一团队目录。如果目标机器离线或已停止接活，等它上线并接活后再试。在线的目标机器有最多 10 分钟领取排队的命令。如果在领取前离线，命令会等 60 秒让它重新连接。如果开始执行后目标离线，请先核对命令已做的操作，再决定是否重试。
