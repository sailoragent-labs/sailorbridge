[English](troubleshooting.md) · [简体中文](zh-CN/troubleshooting.md) · [日本語](ja/troubleshooting.md) · [한국어](ko/troubleshooting.md) · [Deutsch](de/troubleshooting.md) · [Français](fr/troubleshooting.md) · [Español](es/troubleshooting.md) · [Português (BR)](pt-BR/troubleshooting.md) · [Bahasa Indonesia](id/troubleshooting.md) · [हिन्दी](hi/troubleshooting.md)

[← SailorBridge](../README.md)

# Troubleshooting

Start where the work stopped. For a sign-in or payment, read the message on that page. For a machine problem, check the terminal on that machine. For a job, open **Job List**, select the job, and read **Why It Isn't Running**. It tells you whether the job needs an action from you or will resume on its own.

## Get back into your account

| What you see | What to do |
| --- | --- |
| Your Captain ID is taken, or registration is full for today | Try another available ID. If the daily free registration limit was reached, come back tomorrow. For a paid ID, use the original **Redeem link** to finish registration. |
| **Confirm It’s You** after entering your password | Use your authenticator, run `sail confirm` on a paired machine and enter its code, or match the displayed number in a recognized browser when offered. Use the most recent sign-in request. If it expires, sign in again. |
| Too many failed sign-ins or a reused authenticator code | After 5 failures in 15 minutes, the default lock is 15 minutes. Wait for the time shown. If an authenticator code was already used, wait for the next one. |
| You forgot your password, or the recovery code expired | Run `sail recover` in a terminal on a paired machine. Select **Forgot password?** and enter the Captain ID and 8-character code it prints. The code lasts 10 minutes and works once. A new code from that machine replaces the old one. If it rejects the machine’s credentials, try another paired machine. Without a usable paired machine, you need to register a new ID. |
| **Account Recovery Is Pending** | A machine paired less than 72 hours ago requires a 72-hour wait, including after a repair that replaced its credentials. For an older pairing, two-step verification enabled for at least 72 hours requires the authenticator code for immediate recovery. Without that code, submit the 72-hour request. Wait until the time shown. If you did not request recovery, choose **Cancel This Recovery** on a signed-in device. |

## Get a machine or team working

- If installation stops because Git is missing, install Git and rerun the command from **Pair a New Machine**. If Claude Code or Codex is signed out, pairing can finish. Run `claude login` or `codex login` on the machine before asking the team to work.
- If the pairing code expires, run `sail login` for a new one. Enter it on **Pair a New Machine**, choose **Pair**, and check the machine name and details shown. Read and accept the notice on your first pairing, then choose **Approve Machine** and wait for the machine to connect.
- If the machine has not connected within 10 minutes, run `sail host status`. It shows the service state and log path. At the same address, run `sail login` to restore the service. For `origin_mismatch`, if you intend to switch addresses, `sail uninstall` removes the local SailorBridge data, including job working copies. Then run the installation command from the intended app’s **Machines** page and pair again.
- If an update fails, open the machine in **Machines** and follow the reason and repair command shown. For a download failure, retry later with `sail upgrade`. For a write failure, check disk space and use the account that installed `sail`.
- If team creation asks for a machine, pair one and wait for **Online**. If you cannot remove a team’s last machine, use **Add a Machine** first. If the team directory cannot be created, choose **Change the Directory in Team Settings**. Use an absolute directory path on the machine where the error occurred. A file in its place, missing write permission, or a read-only disk can prevent creation. [Machines](machines.md) · [Teams](teams.md)

## Get an answer in chat

- If the **Leader**’s machine is offline, the team chat saves your message and delivers it when that machine reconnects. If the team has no usable machine, add one and send the message again.
- If the engine needs a login, sign in on the named machine. If all accounts usable by the **Leader** are out of quota, send the message again after the reset time. For a rejected model, follow the engine update instruction and retry, or select an available account and model. [Engine accounts and pacing](engine-accounts-and-pacing.md)
- If your message went to a question instead of the **Leader**, answer the open question or choose **Stop** on its card. Then send the message. If a confirmation card was replaced or already answered, check the latest card or job before acting.
- If a file is refused, use team chat and send at most 4 attachments per message, up to 5 MiB each. Supported files are PNG, JPEG, WebP, PDF, plain text, and Markdown. Reselect an unavailable attachment. An unsent upload expires after 24 hours. At the 1 GiB account limit, wait for space to free up as sent files expire after 30 days. For an oversized message, split the text into messages of at most 64 KiB each.
- In an agent session, if the account needed a login or quota, fix that first and then choose **Resume**. If a team-to-team session reached its round limit, the recipient can extend it by 10 or 20 rounds or choose **Unlimited Rounds**. The initiator waits for the recipient. [Chat](chat.md)

## Find out why a job is waiting

Open the job in **Job List**. Read **Why It Isn't Running** before deciding whether to restart anything.

| What is holding up the job | What to do |
| --- | --- |
| Dispatch is paused, or this job is paused | Use **Resume Dispatch** for the team, or **Resume** for the individual job. |
| The machines are busy, the team is at its job limit, or your plan is at its agent limit | Work starts when a slot opens. Check **Concurrent Jobs** for the team or **Concurrency Limit** under **Subscription** for your account. |
| The task needs a writer and reviewer | Choose **Go to Accounts**. Make sure one team machine has the required accounts enabled for both steps. A writer on one machine and a reviewer on another cannot run the same job together. |
| The machine has reached a pacing line or exhausted quota | Wait for the estimate shown. For a pacing wait, **Switch to Unlimited** changes pacing for all your teams after confirmation. For exhausted quota, the job checks again and resumes on the same machine when quota returns. |
| The job needs an answer or a prerequisite | Choose **Answer** if the question is yours. After 5 minutes waiting for an answer the job gives up its slot. Once answered, it continues when its original machine is free. For a prerequisite, open the job number shown and check its outcome. |
| A machine declined the job or stopped checking in | Read the reason under the job. Another eligible machine can pick up a declined job. If all candidates declined, open **Machine Note** to see their reasons. If the running machine lost its connection, it can resume if it returns first. After 30 minutes without renewal another machine can start from the beginning. |
| **Incomplete** or **Failed** | Open **Delivery Report** for the last step, reason, and any kept work. Correct the reported problem. Use **Continue** if offered to pick up the same job on its kept work, or **Redo** to start again. If a push failed, the report gives the branch, commit, and push command for the work kept locally. |

## Fix a command, schedule, or memory entry

- If the terminal says “Run this command inside a job or a team leader session.” (`local_team_context_missing`), the command needs an active session even when you are in the team directory. Ask the **Leader** in team chat, or open **Job List**, **Scheduled Events**, or **Team Memory** to work with an existing item. [Commands for numbered team items](commands.md#work-with-numbered-team-items)
- If a slash command is unknown, type `/` to see enabled flows. For a missing numbered reference, check the correct team and item type and write `#` before its number in chat. If `sail exec` reports the target is offline, the command did not start. If the result was lost *after* it started, check the target before trying again. [Commands](commands.md)
- If a scheduled event is refused, choose a future time for a one-time event, or an interval of 5–720 minutes for a repeating one. A team can have up to 20 events. Delete an unneeded event to make room. A completed one-time event must be created again to run again. If an event refers to a disabled flow or a missing number, correct the message for the next run. [Flows and scheduled events](flows-and-scheduled-events.md)
- If a memory change is refused, open **Team Memory**. A locked entry can be changed there by you. If someone else changed it first, read the latest body before saving. For a full pin allowance, unpin or shorten an entry before pinning another. [Team memory](team-memory.md)

## Check a payment that has not gone through

If payment is pending, return to the original purchase and check its status before paying again. For **Payment Failed** on a subscription, **Update Payment Method and Pay Balance** opens checkout for the outstanding balance. [Plans and billing](plans-and-billing.md)

## When it does not work

If the problem persists, note the steps, the exact message, what you expected, and where it happened. Include the version, machine OS, and engine if you know them. For an account or payment issue, use the private contact listed in the README. For a security issue, use its private security link. Keep credentials, pairing codes, payment details, and private source code out of public reports. [Report a problem](../README.md#report-a-problem)
