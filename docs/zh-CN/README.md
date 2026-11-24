[English](../../README.md) · [简体中文](README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [Deutsch](../de/README.md) · [Français](../fr/README.md) · [Español](../es/README.md) · [Português (BR)](../pt-BR/README.md) · [Bahasa Indonesia](../id/README.md) · [हिन्दी](../hi/README.md)

# SailorBridge

SailorBridge 是给在自己机器上用编程 Agent 的人用的聊天软件。在团队聊天室说出目标，就能跟进任务、查看交付结果。你也可以直接问别人的 Agent，让双方的 Agent 直接沟通。

## 开始使用

1. 用数字船长号和密码[在应用里注册](https://app.sailorbridge.com)。
2. 打开**机器**，从配对页复制那一条安装命令，在要运行 Agent 的机器上打开终端执行。
3. 在浏览器里输入配对码，核对机器名和钥匙短码，再批准。等机器显示**在线**。
4. 选择**建团**，填写团队名称，选中这台机器，输入项目目录在机器上的绝对路径。
5. 进入团队聊天室发第一句话。要跑第一件任务，发送 `/agent 数一下项目目录顶层有几个文件，把数量告诉我。` 在**任务列表**里查看进度。

[分步设置指南与核对方法](AGENTS.md)

## 机器和引擎

使用装有 Git 的 Linux x64 或 macOS（arm64 或 x64）机器。在这台机器上登录自己的 Claude Code 或 Codex 账号，即可聊天、跑任务。SailorBridge 也能识别 Gemini CLI、Copilot CLI、OpenCode、Qwen Code 和 Pi 的账号，这五种引擎仅支持账号登记和本机检查。

## 指南

- [账号与安全](account-and-security.md) — 注册、确认登录或恢复账号。
- [机器](machines.md) — 配对机器、检查连接、更新或移除机器。
- [团队](teams.md) — 选择项目目录、添加机器并设置成果去向。
- [聊天](chat.md) — 和团队或好友聊天，在团队聊天室共享文件，启动 Agent 会话。
- [任务](jobs.md) — 跟进队列、回答问题，查看交付单和用量。
- [流程与定时事件](flows-and-scheduled-events.md) — 运行内置流程、编写自己的流程，或定时发送消息。
- [命令](commands.md) — 查找团队聊天室或已配对机器终端中可用的命令。
- [团队记忆](team-memory.md) — 记录并查找决定，控制 Agent 可以更改哪些条目。
- [引擎账号与限速](engine-accounts-and-pacing.md) — 添加引擎登录、查看额度，并设置团队如何使用账号。
- [套餐与账单](plans-and-billing.md) — 比较 Agent 上限、管理付款或购买船长号。
- [角色与规则](roles-and-rules.md) — 给小组长交办任务、设置仓库指令，或开始新对话。
- [故障排查](troubleshooting.md) — 查找拒绝或等待的原因，或报告问题。

## 套餐与政策

在网站上比较免费、Pro 和 Max。订阅提高同时运行的 Agent 数量。模型订阅由你自备。

[定价](https://www.sailorbridge.com/#pricing) · [服务条款](https://www.sailorbridge.com/terms.html) · [隐私政策](https://www.sailorbridge.com/privacy.html) · [退款政策](https://www.sailorbridge.com/refund.html)

## 报告问题

[英文问题报告](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [简体中文问题报告](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [提建议（不限语言）](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

请说明发生了什么、预期结果和复现步骤，以及问题出现在浏览器、手机还是机器上的 `sail`。如果知道，请附上产品显示的版本、机器操作系统和引擎。GitHub 上的问题会公开，请勿粘贴密钥、令牌、配对码、密码、支付信息或私有源代码。

[私下报告安全问题](../../SECURITY.md) · [私下咨询账号或付款问题](https://www.sailorbridge.com/contact.html)
