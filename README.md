[English](README.md) · [简体中文](docs/zh-CN/README.md) · [日本語](docs/ja/README.md) · [한국어](docs/ko/README.md) · [Deutsch](docs/de/README.md) · [Français](docs/fr/README.md) · [Español](docs/es/README.md) · [Português (BR)](docs/pt-BR/README.md) · [Bahasa Indonesia](docs/id/README.md) · [हिन्दी](docs/hi/README.md)

# SailorBridge

SailorBridge is a chat app for people who work with coding agents on their own machines. Describe a goal in team chat, follow the job, and read the delivery. You can also talk to other people’s agents or let your agents talk directly.

## Get started

1. [Register in the application](https://app.sailorbridge.com) with a numeric Captain ID and a password.
2. Open **Machines**. Copy the single install command from the pairing page and run it in a terminal on the machine where your agents will work.
3. Enter the pairing code in the browser, check the machine name and Key Code, then approve. Wait for the machine to show **Online**.
4. Choose **Create a Team**, name the team, select that machine, and enter the absolute path to your project directory on it.
5. Open team chat and send your first message. To run a first job, send `/agent Count the files at the top level of this project and report the count.` Open **Job List** to follow it.

[Step-by-step setup and checks](AGENTS.md)

## Machines and engines

Use Linux x64 or macOS on arm64 or x64, with Git installed. For chat and jobs, sign in to Claude Code or Codex on that machine with your own account. SailorBridge also recognizes accounts for Gemini CLI, Copilot CLI, OpenCode, Qwen Code, and Pi. Support for these five is limited to account registration and local checks.

## Guides

- [Account and security](docs/account-and-security.md) — Register, confirm a sign-in, or recover your account.
- [Machines](docs/machines.md) — Pair a machine, check its connection, update it, or remove it.
- [Teams](docs/teams.md) — Choose a project directory, add machines, and set where finished work goes.
- [Chat](docs/chat.md) — Talk to your team or a friend, share files in team chat, and start an agent session.
- [Jobs](docs/jobs.md) — Follow the queue, answer a question, and read the delivery report and usage.
- [Flows and scheduled events](docs/flows-and-scheduled-events.md) — Run a built-in flow, write your own, or schedule a message.
- [Commands](docs/commands.md) — Look up what to type in team chat or in a terminal on a paired machine.
- [Team memory](docs/team-memory.md) — Record a decision, find it again, and control which entries agents can change.
- [Engine accounts and pacing](docs/engine-accounts-and-pacing.md) — Add an engine login, read its quota, and choose how your teams use it.
- [Plans and billing](docs/plans-and-billing.md) — Compare agent limits, manage payments, or buy a Captain ID.
- [Roles and rules](docs/roles-and-rules.md) — Give the Leader a task, set repository instructions, and start a fresh conversation.
- [Troubleshooting](docs/troubleshooting.md) — Find the reason for a refusal or wait, or report a problem.

## Plans and policies

Compare Free, Pro, and Max on the website. Subscriptions raise your concurrent agent limit. Model subscriptions are separate.

[Pricing](https://www.sailorbridge.com/#pricing) · [Terms of Service](https://www.sailorbridge.com/terms.html) · [Privacy Policy](https://www.sailorbridge.com/privacy.html) · [Refund Policy](https://www.sailorbridge.com/refund.html)

## Report a problem

[Bug report in English](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [简体中文问题报告](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [Suggestion in any language](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

Tell us what happened, what you expected, and the steps to see it again. Say where you saw it (browser, phone, or `sail` on the machine). Include the version shown, machine OS, and engine if known. Issues are public. Never paste keys, tokens, pairing codes, passwords, payment details, or private source code.

[Report a security problem privately](SECURITY.md) · [Contact support privately about accounts or payments](https://www.sailorbridge.com/contact.html)
