[← SailorBridge](../README.md)

# Commands

Use team chat to give the **Leader** a request or start a flow. Use `sail` in a terminal to manage the machine where it is installed, inspect team work, or run a command on another machine in the same team.

## Choose a command in team chat

Open **Chat** for your team and type `/`. The menu lists four shortcuts, the team’s enabled flows, and finally `/clear`. Select an item, add your request in your own language, and send it. Command names stay in English. Selecting `/clear` takes effect immediately.

| What to type | What happens |
| --- | --- |
| `/job #12 What is this waiting for?` | The **Leader** gets job 12 and your question. |
| `/event #6 Move this to weekdays.` | The **Leader** gets scheduled event 6 and your requested change. |
| `/memory #3 When does this apply?` | The **Leader** gets memory entry 3 and your question. |
| `/do Check the current branch.` | The **Leader** does the work in this chat turn and reports the result, including anything it could not do. |
| `/clear` | Hides earlier messages in this team chat and starts a fresh conversation. |

Use the number from the relevant team’s list. Jobs, events, and memories each have their own numbers. **Go to Chat** on a detail page fills in the right shortcut and number for you. To name a machine, type `@` and select it from the team list.

## Run a flow by name

| Command | What you get |
| --- | --- |
| `/ask` | One question at a time, followed by a requirements brief in chat. |
| `/plan` | A planning job. Read the plan and decide whether to queue the proposed tasks. |
| `/agent` | One worker carries out the task and reports back. |
| `/write-review` | A writer does the work, runs checks, and revises it according to the flow’s review settings. |
| `/memory-tidy` | A job that checks, merges, or removes team memory entries. |
| `/docs-tidy` | A job that checks project documents and reports issues that need your judgment. |
| `/code-sweep` | A read-only inspection with numbered cleanup tasks you can choose to run. |
| `/write-flow` | Describe a repeatable task. When the job succeeds, the new flow is saved in this team. |
| `/edit-flow` | Give the flow name and the change. A successful edit replaces a custom flow. Editing a built-in flow creates a custom one under a new name. |

For example, send `/agent Count the top-level files in this project.` Sending a background flow yourself authorizes the job. The **Leader** writes the task using the conversation, or your words go straight to the queue if **Start Directly** is on. Open **Details** on the job’s chat row to follow it. When the **Leader** proposes a background flow in response to ordinary chat, read the card and choose **Yes, Do It** to start it. [Flows and scheduled events](flows-and-scheduled-events.md)

## Signed instructions for protected actions

SailorBridge automatically signs messages you send to your team, including flow commands such as `/agent` and private instructions to your team in an agent session. It also signs answers and approvals on cards, including job and command approvals, and the instructions you save in scheduled events. Job actions such as **Redo** and **Continue** are also signed when available.

A paired machine signs requests it sends to another team machine with `sail exec`. A conversation with a friend is ordinary chat. Forwarded messages and agent replies can provide context for work.

Before using a protected instruction, the receiving machine checks that it came from a device authorized for the account and matches the team and the action it was sent for. For a command approval, the check covers the specific card, command and target. If a required signature is missing, has expired, conflicts with a newer approval or does not match the action, the machine refuses that action. A team message it cannot verify as yours cannot authorize work.

Look in **Recent Security Events** under **Security** for **A machine couldn’t verify content** and the affected work. Review and resend a refused instruction or start the job again. If an answer was unused, refresh the card and answer again. If a command approval was refused, review the command and approve it again on a current card. If a scheduled event was skipped, review and save it again. If `sail exec` reports that verification failed, the remote command did not run.

If the app shows **Getting this device ready**, keep it open and bring a previously used device that can authorize work online. The app holds your action while it gets ready and sends it when it can verify that the action is still current.

## Pair, check, or remove a machine

| Terminal command | When to use it |
| --- | --- |
| `sail login` | The install command runs this for you. Run it again for a fresh pairing code or to restore the service at the same address with existing credentials. |
| `sail host status` | Check pairing, connection, service, version, and the log location. Add `--trust` to see the saved server key fingerprint. |
| `sail --version` | Print the installed version. |
| `sail upgrade` | Check for an update now. The result says whether a new version was installed, you were already up to date, or the update failed. |
| `sail host service status` | Check the background service. Use `sail host service install`, `sail host service restart`, or `sail host service stop` to install, restart, or stop it. |
| `sail host run` | Run the machine service in the foreground when another copy is not running. |
| `sail confirm` | At **Confirm It’s You**, get a one-time sign-in code from a paired machine’s terminal. |
| `sail recover` | At **Forgot password?**, get your Captain ID and a one-time password recovery code from a paired machine’s terminal. |
| `sail uninstall` | Remove SailorBridge and its local data, including its working copies and logs. Your own project directories and engine logins are kept. |

For engine logins, `sail account list` shows what this machine recognizes. Use `sail account add <name> <directory>` to register a login directory, `sail account remove <name>` to remove a registration or ignore a default login, and `sail account restore <provider>` to recognize an ignored default login again. For a compatible endpoint, `sail account create <provider>` writes a settings template under `~/.sailorbridge/`, which `sail uninstall` removes. [Set up a GLM, DeepSeek or Kimi account from a template](engine-accounts-and-pacing.md#set-up-a-glm-deepseek-or-kimi-account-from-a-template)

## Work with numbered team items

From your terminal, run the following commands in the team’s configured project directory on a paired machine. Use your team’s item numbers. For example, the job shown as `#12` in chat is `12` in a terminal command.

| Task | Commands you can run in your terminal |
| --- | --- |
| Find a job | `sail job list` lists open jobs. Add `--all` to include ended jobs. `sail job get 12` shows job 12. Add `--json` for the full detail. |
| Stop or delete a job | `sail job stop 12` stops the job. `sail job delete 12` deletes an ended job record. |
| Find an event | `sail event list` lists enabled events still due to run. Add `--all` to include disabled or completed events. `sail event get 6` shows the message and schedule. |
| Delete an event | `sail event delete 6` removes the scheduled event. |
| Delete a memory | `sail memory delete 3` permanently deletes an entry. To delete a locked entry, use **Team Memory** in the application. |

The commands below require an active **Leader** session or job. Running them from your terminal returns `local_team_context_missing` even in the team directory. Ask the **Leader** in team chat for what you need. To work with an existing item yourself, open **Job List**, **Scheduled Events**, or **Team Memory** in the application. Workers have read-only access to jobs and events.

| Who runs it | Task and commands |
| --- | --- |
| **Leader** | `sail job create <flow> "<task>"` queues a background flow. `sail job edit 12 "<revised task>"` changes an open job. `sail job retry 12` continues eligible work under the same number. |
| **Leader** | `sail event create "Check the queue" --weekdays 09:00` schedules a team chat message in the machine’s time zone. Other schedules use `--once`, `--daily`, or `--every`. Use `--tz` to specify a time zone. `sail event edit 6 --disable` pauses the event. |
| **Leader** or worker | `sail memory list` lists entries. `sail memory titles` lists titles. `sail memory search "release checklist"` returns up to 10 matches. `sail memory get 3` reads the entry. |
| **Leader** or worker | `sail memory create "<title>" "<body>"` records a fact or submits a correction under the same title. `sail memory edit 3 "<body>"` changes an entry. `sail memory conflicts` lists unresolved conflicts. |
| **Leader** | `sail memory resolve <id> --value "<correct text>"` resolves a conflict. It takes the conflict ID. A locked entry needs your decision in **Team Memory**. |
| **Leader** or worker | `sail memory list --tidy` lists candidates and versions. `sail memory review 3 --rev <version>` marks an entry worth keeping. `sail memory merge` takes repeated `--entry <id>:<version>` arguments plus `--title` and `--body`. Among worker jobs, only `/memory-tidy` can delete entries. |

If a command reports a pending decision, check the current value in the reply before assuming the change took effect.

## Run a command locally or on another team machine

For a local command, `sail run git status` sends the output to your terminal. For a long, noninteractive command, add `--fold` before the command. You get the result, the last lines of output, and the path to the full log. For a local tmux window, `sail tmux read <window>` shows its text. `sail tmux send <window> "<text>"` fills the input. Send `sail tmux send <window> --key Enter` when you mean to submit it.

To run a command on another machine you own in the same team, start in the team directory and replace `build-machine` with the target’s name. For example, `sail exec build-machine git status --short` runs in that team’s directory on the target. The exit code and the last 40 lines of combined output, up to 16 KiB, come back to your terminal. Use `--json` before the machine name for a single JSON result.

The default time limit is 5 minutes. To change it, put `--timeout` and a positive number of seconds before the machine name. One sending machine can have up to 8 commands waiting for results. Pressing Ctrl-C stops your terminal waiting. The remote command can still be running.

## When it does not work

- If a chat command is unknown, type `/` and choose an enabled flow. If an old confirmation card points to a disabled flow, enable it in **Team Flows** or choose an available flow and send a new request.
- If a numbered shortcut cannot be found, open **Job List**, **Scheduled Events**, or **Team Memory** for this team. Check the number and include the `#` in chat.
- If `sail exec` cannot identify the team, change to one of the listed team directories. If the target is offline or has stopped accepting work, retry once it is online and accepting work. An online target has up to 10 minutes to pick up a queued command. If it goes offline before pickup, the command waits 60 seconds for it to reconnect. If the target went away after starting, check what the command did before running it again.
