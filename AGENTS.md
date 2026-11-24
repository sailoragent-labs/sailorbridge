[English](AGENTS.md) · [简体中文](docs/zh-CN/AGENTS.md) · [日本語](docs/ja/AGENTS.md) · [한국어](docs/ko/AGENTS.md) · [Deutsch](docs/de/AGENTS.md) · [Français](docs/fr/AGENTS.md) · [Español](docs/es/AGENTS.md) · [Português (BR)](docs/pt-BR/AGENTS.md) · [Bahasa Indonesia](docs/id/AGENTS.md) · [हिन्दी](docs/hi/AGENTS.md)

# SailorBridge setup guide

## 1. Prepare the machine

Use a machine you control running Linux x64 or macOS arm64/x64. Install Git and either Claude Code or Codex. Sign in to the engine with your own account. Choose the project directory you want the team to work in.

**Check** — `git --version` and either `claude --version` or `codex --version` print a version. If the engine is installed but signed out, run `claude login` or `codex login` on that machine. Pairing can proceed while the engine is signed out. Sign in before starting the chat or job.

## 2. Register in the browser

Open the [application](https://app.sailorbridge.com) and choose **Register**. For this walkthrough, enter an available numeric Captain ID marked as free, set a password, and complete the age and terms confirmations.

**Check** — The application opens and **Machines** is available.

## 3. Run the install command

Open **Machines** and the **Pair a New Machine** page. Copy the single install command shown there and run it on the machine from step 1. It installs `sail` and starts pairing automatically.

**Check** — The terminal shows an eight-character pairing code and its remaining time. If the code expires, run `sail login` for a new one.

- **Already paired to this address?** Run `sail host status`. If connected, go to step 5. To restore the service at the same address, run `sail login`. It restarts the service with the existing credentials.
- **Wrong address (`origin_mismatch`)?** To switch addresses, run `sail uninstall`, then copy and run the install command from the intended application’s Machines page. Uninstalling removes SailorBridge’s local data, including its working copies.

## 4. Approve the machine

Enter the pairing code on the browser’s pairing page and choose **Pair**. Match the machine name and **Key Code** with the terminal. Read and accept the first-pairing notice about the permissions of the user running `sail`, then choose **Approve Machine**.

**Check** — Wait for **Online** in **Machines**. The terminal also confirms that the machine is paired and online.

## 5. Create a team

Choose **Create a Team**. Name the team, select the online machine, and enter the absolute path on that machine under **Project Directory**. If the directory is missing, SailorBridge creates it on first use. Under **Destination**, keep **Auto-Merge** to merge changes into the remote main branch, or select **Branch** to push each job to its own branch for review. Create the team.

**Check** — Your new team lists the selected machine as **Online**.

## 6. Send the first message

Open **Chat** for the team and ask “What project directory are we working in?”

**Check** — The **Leader** replies in the same chat.

## 7. Finish the first job

Send `/agent Count the files at the top level of this project and report the count.` in team chat. Open **⋯ → Job List** to follow the job.

**Check** — The job shows **Done**. Open its **Delivery Report** and read the file count.
