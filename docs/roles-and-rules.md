[← SailorBridge](../README.md)

# Roles and rules

Each team has a **Leader**. You talk to it in team chat. It answers questions, runs short commands, and hands longer work to a flow. A worker runs a step of that flow on a team machine. You give the engine standing instructions in the project repository. A role editor and rules library are not available.

## Give the right work to the team

Open **Chat** for your team. Ask “Which branch are we on?” The **Leader** can check the team directory and reply in the conversation. For a quick check on another machine in the team, type `@`, select the machine, and say what to check. You get a summary of the result.

For work you want delivered and reviewed, send a request such as “Update the setup instructions and have them reviewed.” When the **Leader** proposes a background flow, read the task on the card. Choose **Yes, Do It** to queue it or **Not Like That** to explain what should change. Open **Job List** to follow the workers’ steps. If a worker needs a decision, the **Leader** checks what the team already knows and asks you in chat when it needs your answer.

## Give the engine a standing instruction

Put project-wide instructions in the repository’s `AGENTS.md` for Codex or `CLAUDE.md` for Claude Code. For example, write down which command to run before handing over a change. The engine reads its instruction file when it works in that repository. For a fact the team should remember across jobs, you can also ask it to remember the fact in chat. [Team memory](team-memory.md)

## Continue a conversation after a break

Send your next message in the same team chat. The **Leader** can start a fresh engine session after a long pause, an engine change, or a move to another machine. It picks up the team’s saved summary, recent messages, team memory, and unfinished jobs. If you see **Tidying up the conversation…**, you can still send your message. The **Leader** answers after it finishes summarizing.

## When it does not work

- If an old detail is missing, give the job number, the decision, or the relevant file in your next message. A fresh session gets the most recent 20 messages and a summary when one is available.
- If a mistaken instruction from an earlier conversation keeps carrying over, choose **Clear Chat**, check the team name, and confirm. Your earlier messages leave the chat view and the next session starts without the old summary. If the instruction came from a repository file or team memory, correct it there.
- If the **Leader** runs out of time, ask again in smaller steps or send the longer task as a job. [Commands](commands.md)
