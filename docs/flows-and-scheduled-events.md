[← SailorBridge](../README.md)

# Flows and scheduled events

A flow gives your team a repeatable way to do a task. It has a name you can type in chat, steps and options saved for that team. A scheduled event sends a message to team chat at a time you choose. That message can ask the leader a question or start a flow.

## Find and run a flow

In team chat, type `/` to see the enabled flows and their descriptions. Choose a flow, add what you want it to do, then send. For example, `/ask What should the export include?` starts a conversation about that requirement. An interactive flow asks in chat. A background flow enters **Job List**.

When you send a background flow command, the **Leader** normally uses the conversation to write a task brief and queues the job. If **Start Directly** is on for that flow, your words become the brief and the job queues immediately. This option defaults to off for built-in background flows. When the leader proposes a job on its own, choose **Yes, Do It** to start it.

| Built-in flow | When to use it and what you get |
| --- | --- |
| `/ask` | Clarify a decision. Answer one question at a time to get a requirements brief. |
| `/plan` | Plan work that needs several tasks. Read the plan and proposed batch, then choose **Queue All Tasks**, **Revise Plan** or **Not Now**. The plan is itself a job you can follow. |
| `/agent` | Give a worker a mechanical or time-consuming task. One worker carries it out and reports the result without a review round. |
| `/write-review` | Give the team an implementation task and say how to check it. A writer does the work, checks run, and the writer and reviewer examine the result. |
| `/memory-tidy` | Review team memories, remove entries that have lost their value and combine duplicates. The delivery lists actions and suggestions that need your decision. The team can also run this automatically when entries need attention, at most once in 24 hours. |
| `/docs-tidy` | Recheck documentation affected by changes and spot-check the rest in rotation. The delivery separates mechanical fixes from questions for you. |
| `/code-sweep` | Inspect code for cleanup opportunities. Read the numbered proposals in the delivery and tell the leader which ones to carry out. The scan itself is read-only. |
| `/write-flow` and `/edit-flow` | Describe a repeatable task to create a flow, or describe how an existing flow should change. The result is saved for your team. |

## Choose who writes and reviews

Open ⋯ in team chat, choose **Team Flows** and open `/write-review`. The page shows the steps and the options used for future jobs in this team.

| Option | How to use it |
| --- | --- |
| **Who Writes** | Keep **Automatic** to select a provider by task difficulty, or select an engine for the writing steps. |
| **Who Reviews** | Keep **Automatic** to look for an independent reviewer from a different model family, or select an engine for review. The writer handles its own self-review. The team’s model settings determine the actual models. |
| **Self-Review Passes** | Choose 0–10, default 3. Each round, the writer checks its work, fixes findings and checks again until a pass finds nothing or reaches this limit. Set 0 to skip self-review. |
| **Maximum Rounds** | Choose 0–10, default 6. Set 0 for Solo, which skips independent review and keeps your self-review setting. |

A P1 finding calls for another review of the full change. Lesser findings call for review of the fixes. From round three, if there is no P1, the writer can finish the remaining fixes and deliver without another review. If P1 findings remain at the round limit, open **Delivery Report** for the findings that stopped the job.

For code to merge, the complete applicable check must pass on the final commit. If a documentation-only change has no applicable check, an independent reviewer must accept the reason. In Solo, a change with no check to run stays **Incomplete**. [Read a job’s checks and delivery](jobs.md)

## Write or edit a team flow

1. In team chat, send `/write-flow` followed by the steps, what counts as done, what to do if a step fails and what to deliver. For example, `/write-flow List Markdown files changed since the last commit. Report their paths. If none changed, say so.`
2. If the writer needs a decision, answer the question in chat. Once the flow has been written and checked, chat shows the name it was saved under. Choose **View flow** to read its description, steps and options. Its name is now available in the `/` menu.
3. To revise the flow, choose **Edit in Chat** or send `/edit-flow <name> <change>`. Say what should change and what should stay. Editing a custom flow replaces that team’s version. Editing a built-in produces a custom flow with a different name. Read the delivery for the effective option values and any step rules the edit dropped.

You can also edit a flow’s options on its detail page. For a flow that follows a saved set of instructions, you can edit those instructions there for its next run. Turn **Enabled** off to remove a flow from the team’s menu for new runs. Queued and running jobs can finish. The two flow-writing commands stay available.

## Schedule a message

1. In the team’s ⋯ menu, open **Scheduled Events** and use the plus button to **Add Event**. Under **What to Say**, enter the message you want sent, up to 16 KiB. For example, `/docs-tidy Check the project documentation.`
2. Select **Frequency**. Choose **One-Time** for a future local date and time, **Daily** for a time each day, or **Weekdays** for Monday through Friday. With **Every Few Minutes**, set **Interval (Minutes)** from 5 to 720. Use **From** and **To** to limit it to part of the day.
3. Check **Time Zone**, which starts with your browser’s zone, and save. The list shows the first line of your message and the next time it will run. Creating the event authorizes the message. At the appointed time it appears under your name in chat, marked **Scheduled**. Each trigger uses a full leader turn.

Times follow the selected zone. If a daylight-saving change skips a scheduled time, the event uses the next valid time. If the clock repeats that time, it uses the first occurrence. An interval event with a time window skips occurrences outside that window.

Open the event to edit its message or timing. Saving recalculates the next run. Disable the event to stop future messages, then enable it when you want it to resume. Re-enabling starts from that point. After an interruption to the scheduling service, only the most recent missed occurrence is sent. Search for an event by text or by its exact number, such as `#6`. Use **Completed** to find a finished one-time event.

## When it does not work

- If chat does not recognize a flow, type `/` to see the names enabled for this team. Re-enable the flow in **Team Flows** if needed. If a plan cannot queue its batch because `/write-review` is disabled, enable it before submitting the work again.
- A team can have 30 custom flows. At the limit, delete a custom flow you no longer need before creating another. For a name already in use, edit that flow or choose a new name. If an edit reports that a dropped step rule is too long to include in the delivery, shorten or move the rule on the flow page and try the edit again.
- A team can have up to 20 scheduled events. At the limit, delete an event before adding one. If a one-time event has already run, create a new one to repeat it. Use a future time and an interval within the range above.
- If a scheduled message names a missing or disabled flow or a missing numbered item, that occurrence is spent. Correct the message or enable the flow before the next occurrence. If a scheduled interactive flow reports that another is busy, it waits for a later trigger.
