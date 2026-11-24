[← SailorBridge](../README.md)

# Jobs

A job is one run of a flow. Each team has one queue shared by its machines. You can give the team a job in chat, look up its progress by number and open its delivery to see what it produced and what still needs your attention.

## Put work in the queue

In team chat, send a flow name and a task, for example `/agent Count the files at the top level of this project and report the count.` The job enters the queue and an eligible machine takes it when it has room. That machine runs the job in its own working copy.

If the **Leader** proposes work in conversation, read the proposal and choose **Yes, Do It** to queue it. For a plan with several tasks, read the list before choosing **Queue All Tasks**. **Revise Plan** lets you describe a change. **Not Now** leaves the batch out of the queue. Once accepted, each task has its own job number. [Choose a flow](flows-and-scheduled-events.md)

## Find a job and read its status

Open the ⋯ menu in team chat and choose **Job List**, or choose **Details** on the job in chat. The list initially shows **Running** and then remembers your last filter in this browser. Choose **All** to include ended jobs. Search by task text or flow name, or enter the full number with its hash, such as `#6`, to find it across filters.

| What you see | What it means |
| --- | --- |
| **Queued** | The job is waiting to be taken. The line below it gives the reason. A referenced job number identifies a prerequisite it is waiting for. |
| **Running** | A machine has taken the job. Open it for the current stage and machine. |
| **Waiting for the leader** or **Waiting on you** | The leader handles questions it can answer. If it needs your decision, choose **Answer** and reply in chat. The **Yours** filter finds jobs waiting for you. |
| **Done** | The flow delivered its result. **Done, Checks Failed** means there is a delivery with a failed check. Read the check before using the result. |
| **Incomplete** | The flow stopped before delivering everything requested. Read where it stopped and what is missing. Work already produced is kept. |
| **Failed** | An error ended the run. Open the report and **Machine Note** for the reason. |
| **Cancelled** | The job was stopped. Its entry remains available in the list. |

**Paused** and **Quota** can also explain why a job is idle. Open **Why It Isn't Running** to see what it is waiting for and which action, if any, you can take.

## Read the job, delivery and usage

Select the numbered row. **Job Details** shows the status, **Run Time** and **Rounds**. **Task Information** includes the machine, who started the job and **Time in Queue**. Expand **Steps** to see which stage ran, how long it took and the engine and model used. **Quality Issues**, when present, shows findings from self-review, peer review and the last peer-review round.

When the job ends, open **Delivery Report**. Read **Changes**, **Checks**, **Review Findings**, **Unchecked** and **Needs Your Call**. Failed checks appear first when a completed job has one. For a job that produced commits, read where they landed. If the machine could not push them, the report gives the local branch, commit, reason and a command you can run. A report-only job can deliver its answer without a commit.

Open **Usage** and expand **By Round** for the token counts and actual models used. Usage is recorded by provider, account and model. The delivery totals cover the last time a machine took the job. Queue time is recorded separately from run time.

## Pause, change, stop or continue a job

- On a queued job, choose **Pause** to keep machines from taking it, then **Resume** when it can run again. Choose **Start Now** to move a queued job to the front. If a slot is occupied, you can keep waiting or explicitly stop a running job to free it.
- To revise an open job, choose **Go to Chat** from the job. This fills in its number. Add your new requirements and send the message. If the leader proposes a change, choose **Yes, Change It**. A queued job gets the revised brief in place. A running attempt stops and the job requeues with the same number.
- To end a job, choose **Stop** and confirm. A job you explicitly stop needs your instruction to continue. For an ended job with a saved point to resume from and usable work, open ⋯ and choose **Continue**. It uses the same job number and the retained working copy or pushed branch. If you change its requirements before continuing, it starts from the beginning.
- Choose **Redo** to queue a new job with the original flow, brief, repository and options. It gets a new number, and you can still read the earlier job. Use this when **Continue** is unavailable. **Delete** permanently removes an ended job’s record after confirmation.

## When it does not work

- If dispatch is paused for the whole team, choose **Resume Dispatch** when you want machines to take new jobs. If the team or your account has reached its concurrency limit, the job starts when a slot opens. [Team dispatch settings](teams.md)
- If a job is waiting for your answer, you can reply even after the first five minutes. After five minutes the machine releases the slot. Once you answer, the same machine resumes as soon as it is free.
- If a job needs a writer or reviewer, choose **Go to Accounts**. One machine must have the accounts needed for the whole job. If every candidate machine declined, the job fails and its notes give each machine’s reason. If the wait is for quota or pacing, check the estimated time. Work resumes as quota or capacity becomes available. [Engine accounts and pacing](engine-accounts-and-pacing.md)
- If a machine loses contact, it can resume when it reconnects. After 30 minutes without renewing its claim, another team machine can take the job and start from the beginning. Three losses of contact on the same job end it as **Failed**. Check the machine before continuing or redoing the job. [Check the machine](machines.md)
- A recoverable system failure can be continued automatically up to 10 times over the life of a job. If the job stays ended, read its last report, address the cause and use **Continue** if it is offered.
