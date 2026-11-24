[← SailorBridge](../README.md)

# Engine accounts and pacing

Your agents use engine accounts signed in on your machines. You can see which accounts a team can use, how much quota is left, and when work will resume. A SailorBridge plan sets how many agents can run at once. Model access and quota come from your engine provider.

## Find or add an account

1. Sign in to Claude Code or Codex on the machine where you want it to run. Run `sail account list`. A default login is detected automatically. Its name is normally the engine name followed by `@` and the machine name.
2. To add another login, sign in with the engine in a separate account directory. Run `sail account add <name> <directory>` with that directory and a name of 1–64 characters, unique on the machine, with no spaces or slashes. For example, if your second login is there, run `sail account add work "$HOME/codex-work"`. The next quota check picks it up without a restart.
3. Open **Resources**, then **Accounts**. Select the account to see its machines, quota, and available models. Accounts reported under the same name by the same engine on different machines appear in one row. The login directory, email, and credentials stay on the machine.

Codex takes a subscription login. Claude Code takes a subscription login or an API key. Gemini CLI, Copilot CLI, OpenCode, Qwen Code, and Pi have account registration and local checks only. For those five, separate named directories are recognized for Gemini CLI and OpenCode.

## Use a Claude-compatible endpoint

For a provider such as DeepSeek or GLM, configure a separate Claude Code account directory on your machine. In its `settings.json`, set the provider’s base URL under `env.ANTHROPIC_BASE_URL` and its credential under `env.ANTHROPIC_API_KEY` or `env.ANTHROPIC_AUTH_TOKEN`. Set `ANTHROPIC_MODEL` in the same `env` object to the provider’s model name. You can map the Opus, Sonnet, and Haiku families separately with `ANTHROPIC_DEFAULT_OPUS_MODEL`, `ANTHROPIC_DEFAULT_SONNET_MODEL`, and `ANTHROPIC_DEFAULT_HAIKU_MODEL`.

Run `sail account add <name> <directory>` there with the name and path you chose. The account runs through Claude Code. Open **Available Models** to see the model names read from the directory. Endpoint models use those mappings and have no effort setting. The job details show the model that actually ran.

## Set up a GLM, DeepSeek or Kimi account from a template

`sail account create` writes a local Claude Code settings file with the provider’s endpoint, proposed models for the high, middle, and low tiers, and a key placeholder, without asking for, reading, or sending your key or registering the account.

To set up GLM, run this on the machine where you want to use the account.

```sh
sail account create glm
```

The command prints three lines. Here `~` stands for your home directory.

```text
Proposed models (Opus/Fable, Sonnet, Haiku/subagent): glm-5.3, glm-5.2, glm-5.3-flash.
Three distinct model IDs. The Sonnet mapping is a proposed middle tier.
Edit ~/.sailorbridge/account-templates/glm/settings.json to replace the API key placeholder, then run sail account add <name> ~/.sailorbridge/account-templates/glm.
```

The generated `settings.json` contains this template.

```json
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "REPLACE_WITH_YOUR_API_KEY",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "ANTHROPIC_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-5.2",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-5.3-flash",
    "ANTHROPIC_DEFAULT_FABLE_MODEL": "glm-5.3",
    "CLAUDE_CODE_SUBAGENT_MODEL": "glm-5.3-flash"
  }
}
```

Open the file in a text editor such as `nano`.

```sh
nano ~/.sailorbridge/account-templates/glm/settings.json
```

Replace `REPLACE_WITH_YOUR_API_KEY` with your own GLM key, keep the quotation marks, and save the file. Register the directory under a name you choose. This example uses `glm`. The name must be unique on this machine, 1–64 characters long, with no whitespace or `/`.

```sh
sail account add glm ~/.sailorbridge/account-templates/glm
sail account list
```

Look for `glm` in the terminal list. Once the machine reports the account, open **Resources** and then **Accounts** in the application. Select `glm` to see its **Available Models**.

For DeepSeek or Kimi, start with the command for your provider. Open the `settings.json` path it prints and replace the placeholder with your provider key. Use the printed `sail account add` command with your chosen name, then check `sail account list`.

| Template command | Endpoint in the file | Proposed models printed |
| --- | --- | --- |
| `sail account create deepseek` | `https://api.deepseek.com/anthropic` | The high tier uses `deepseek-v4-pro`. The middle and low tiers share `deepseek-flash`. |
| `sail account create kimi` | `https://api.kimi.com/coding/` | Use a Kimi Coding Plan key. All three tiers use `k3.1-pro[1m]`. |

MiniMax requires `--region international` or `--region china`. GLM, DeepSeek, and Kimi refuse `--region`.

## Read the quota and keep some for yourself

Open the account in **Accounts**. Check **Quota**, **Resets**, and **Read at** together. A subscription reading can show a five-hour window, a weekly window, or a weekly allowance for a particular model. Codex reports its standard weekly pool. Reading quota uses no model tokens. If a new reading fails, a successful reading up to an hour old can still appear, marked as old. A missing reading has a reason and can still leave the account eligible for work.

- **Enabled** controls new assignments to this account across all your teams. Turning it off lets work already running finish.
- **Reserve Threshold** leaves a percentage for your own use. Set it from 0% to 100% in steps of 5. If a window longer than one day has only that percentage left or less, both workers and the **Leader** stop using the account. Short windows use their full allowance.
- For an account measured by spending, set **Monthly Cap** to the most you want that machine to use in a calendar month. This applies to DeepSeek, for example. GLM provides its own quota reading. Once the cap is reached, new work waits until midnight UTC on the first of the next month unless you raise the cap. A step already in progress can finish above it. If you register the same account on several machines, each measures its own spending. If **Cost Unavailable** appears, you see the token count and the cap cannot take effect.
- **Reset Credits** appear when Claude or Codex reports them. Open a credit, check what it resets and when it expires, then choose **Redeem** and confirm. **Redeem Reset** from the account list uses the eligible credit that expires first. The machine holding the account performs the reset. Check the outcome before using another credit.

## Choose accounts and models for one team

Open **Account List** from the team chat menu. Accounts on the team’s machines are included by default. Set **Role** to **Both**, **Write Only**, or **Review Only** to control which worker steps can use an account. Use **Leader Only** to reserve it for chat in this team. **Remove from Team** and **Add Account to Team** change its availability for this team.

In **Team Details**, open the dispatch settings. Under **Leader Model**, choose an enabled account on a team machine, then one of its detected models and an effort level if offered. Choosing the account on another machine moves the **Leader** there for the next message. If the chosen account cannot run, the reply identifies the fallback engine and model.

For workers, set the preferred model and effort for each difficulty tier and engine in the team’s model settings. A flow’s writer and reviewer options choose the engine. With automatic review, the reviewer avoids the writer’s actual model family when possible. If a flow asks for an engine the team has no account for in that role, the job can use automatic selection for that run. The job details explain the change.

A job needs one machine that can do all its steps. On that machine, each step uses an enabled account allowed for its engine and role. Among eligible accounts, a login awaiting renewal goes first. Accounts resetting within a day are next, earliest reset first. For later resets, selection weighs usable quota, plan capacity, and time to reset. Accounts without readings come last. An incremental review, or a first review of at most 120 changed lines, prefers a smaller plan with room.

## Set the pace of new work

Open **Resources** and then **Pacing Mode**. The default, **Quota Paced**, spreads work over the quota window. An account is ahead of pace when the percentage used is more than 100/7 percentage points (about 14.3) ahead of the percentage of time elapsed, and more than one seventh of the window remains. If all eligible accounts are ahead of pace, the machine waits before taking a new job. A job already running can continue. Chat with the **Leader** can continue too.

Choose **Unlimited** to let all your teams take new jobs without waiting for that pacing line. Account reserves and exhausted windows still apply. If an account is selected for the **Leader** in any of your teams and has less than 10% left in an account-wide window, workers leave it for chat. You can switch back to **Quota Paced** on the same page.

## When it does not work

- If the template file already exists, the command refuses to overwrite it and prints its path. Edit that file and register its directory.
- If the command refuses a directory, check the path it prints. The directory must belong to your user and have mode `0700` so only you can access it. Once the owner and permissions are correct, run the template command again.
- `sail uninstall` removes `~/.sailorbridge/`, including these settings files, so keep a copy of your key somewhere else too.
- If registration fails, follow the terminal’s sign-in command for the directory you supplied. It must identify one engine. Use `sail account list` to check the name. To remove a registration or ignore a default login, run `sail account remove <name>`. The local credentials are kept. To recognize a default login again, run `sail account restore claude` or `sail account restore codex`, or open the machine’s **Ignored Logins** and choose **Restore**.
- For **Login Expired**, sign in again on the named machine. For **Login Renewal Needed**, the machine attempts renewal. For **Network Unavailable**, check that machine’s connection. A rate-limited or unavailable provider is retried after a delay. If the account shows **Models Not Read Yet** in the model picker, wait for a reading or choose an account with a detected model.
- If a team refuses to remove its **Leader**’s account, select a different account under **Leader Model** first. If a job lacks a writer or reviewer, choose **Go to Accounts** from its details and enable the missing role on a machine that can do the whole job.
- Open **Job List** and read **Why It Isn't Running**. A pacing wait gives an estimated time. You can wait or confirm **Switch to Unlimited** for all teams. A job that has exhausted its usable accounts waits on the same machine and checks again at the time shown. Signing in or regaining quota lets it resume automatically.
