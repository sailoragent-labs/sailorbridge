[← SailorBridge](../README.md)

# Teams

A team gives one project its own chat with the **Leader**, job queue, team memory and one or more machines. You can own several teams and use the same machine in more than one. Only you can view and change your team’s settings.

## Create a team for your project

1. Pair the machine that will run the leader. When it shows **Online**, choose **Create a Team** on the pairing page. You can also start from **Teams** by choosing **Create Team**. [Pair a machine](machines.md)
2. Enter a **Team Name** and select that machine. You can choose an **Avatar** and a leader account, model and effort from the options available on that machine, or use the defaults.
3. Under **Project Directory**, enter the absolute path on the selected machine, starting with `/`. If you already work in a repository, use its local directory. If you want to work in an existing remote repository, clone it on that machine first and set up its Git credentials there. SailorBridge detects the repository’s main branch.
4. Choose a **Destination** and select **Create Team**. The team now lists the machine. Open **Chat** to speak to the leader. [Use team chat](chat.md)

The first time the team uses the path, it opens the existing folder or creates it. For a plain folder with files, it initializes Git and takes an initial snapshot. If the folder contains several Git repositories directly beneath it, tell the leader which repository you mean. Each job works in one repository. Work across repositories is split into separate jobs.

## Choose where changes go

Open your team in **Teams** to reach **Team Details**. Change **Project Directory** or **Destination** there. Changes apply from the next job a machine takes.

| Destination | Where to find a job’s commits |
| --- | --- |
| **Auto-Merge** (default) | The machine tries to push to the remote main branch, then fast-forwards its local main branch. Check the delivery if main advanced or the remote requires review. If it lists a job branch, merge that branch on the remote. |
| **Branch** | Each job pushes its own `sb/<job>` branch for you to review and merge. Other jobs start from the project’s main branch. |

Each machine uses the repository’s own Git remote and credentials. It fetches the remote main branch before starting a job and fast-forwards its local copy when possible. If a push fails, open the job’s **Delivery Report** for the reason, local branch, commit and push command. [Find a job’s delivery](jobs.md)

## Add, move or remove a machine

In **Team Details**, open **Machine List** and choose the plus button to **Add a Machine**. Select a paired machine and choose **Same As Team Folder** or enter its own absolute path under **Project Folder**. You can edit that path later. An eligible machine with room for work can now pick up a job from the same queue.

To remove a machine from this team, select it and confirm **Remove From Team**. It stops taking new jobs from this queue. If you remove or retire the machine marked **Leader Runs Here**, the earliest remaining machine to join the team takes over as leader. Removing the last machine from a team is blocked. Add its replacement first.

## Set how the team takes jobs

Return to **Team Details** to change how this team runs work.

- In **Job Settings**, **Dispatch** controls new work. Choose **Paused** to hold queued jobs while running jobs continue. Choose **Normal** to let machines take queued jobs again.
- **Concurrent Jobs** defaults to **Unlimited**, so your account’s concurrency limit applies. Choose **Set a Number** to cap this team’s running jobs. Lowering the number takes effect as running jobs finish.
- Under **Leader Model**, select the account, then the model and the effort level if offered. Accounts are listed with their machine. Selecting an account on another team machine moves the leader there for the next message. It uses the same conversation summary and team memory. Running jobs stay on their machines.
- For workers, choose a preferred model and, where offered, effort for each difficulty level and provider. **Restore Default** returns a choice to the team’s default. In **Account List** you can restrict an account to writing, reviewing or the leader. [Engine accounts and pacing](engine-accounts-and-pacing.md)

## Dissolve a team

Open **Team Details**, choose **Dissolve Team**, check how many agent sessions will end, then type the team name to confirm. Dissolving is permanent. It cancels open jobs, deletes scheduled events and removes the team from your list and chat entry points. Its pending agent session requests and active sessions end. Each participant keeps their session history. The machines stay paired to your account.

## When it does not work

- If there is no machine to select, choose **Pair a Machine** when creating a team, or **Pair a New Machine** when adding one. If the machine was retired, pair it again before adding it.
- If a job or chat reports that the directory cannot be created, check the path on the machine that tried to use it. A file at that path, missing write permission or a read-only disk can prevent creation. Choose **Change the Directory in Team Settings** and enter a writable directory for that machine.
- If your leader account or model is no longer available during creation, choose again from the refreshed list. If queued work is waiting after creation, read **Why It Isn't Running** in the job details to see whether dispatch, a limit or an account is holding it up.
