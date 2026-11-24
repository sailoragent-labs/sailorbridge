[← SailorBridge](../README.md)

# Machines

A machine is a computer you connect to your account to run a team leader or take jobs. You install `sail` on each machine and approve it in the browser. Its background service keeps it connected after you close the terminal.

## Install and pair a machine

1. Use a machine you control running Linux x64 or macOS arm64 or x64. Install Git. For chat and jobs, install Claude Code or Codex and sign in on that machine with your own engine account. You can finish pairing before signing in to the engine.
2. In the application, open **Machines**, then **Pair a New Machine**. Copy the install command shown there into a terminal on the machine you want to connect. You can run it from any directory. It installs `sail`, starts pairing and prints an eight-character code valid for 10 minutes.
3. Enter that code under **Pairing Code** in the browser and choose **Pair**. Check the machine name and **Key Code** against the terminal. On your first pairing, read the notice before accepting it. Agents can read, change and delete files, use credentials and connect to the network with the permissions of the operating-system user running `sail`. Use a dedicated machine or container if you need isolation.
4. Choose **Approve Machine**. Keep the machine connected while it collects its credentials and starts the service. When **Machines** shows **Online** and the terminal confirms the connection, you can choose **Set Up Accounts** or **Create a Team**. [Create a team](teams.md)

## Check a connection or pair more machines

Open a machine in **Machines** to see its name, platform, **Last Online**, **Paired on** and **Client Version**. You can edit the name here to make machines easier to tell apart. On the machine itself, run `sail host status` to check pairing, connection and service status and find the local log.

To use another computer, open **Pair a New Machine** again and run the displayed command on that computer. Once it is online, add it to the team and set its project folder there. A machine can serve several teams. Each job runs on one eligible machine in its team. [Manage a team’s machines](teams.md)

## Update or repair an installation

Automatic updates are on by default. After verifying an update, the service restarts and picks up local work again. Completed steps are kept. An interrupted local step may run again. To update manually, run `sail upgrade` on the machine. It tells you whether it installed an update, was already current or encountered an error. Run `sail --version` to check the installed version.

If the service needs restoring, run `sail login`. At the same address, it reinstalls and restarts the service with its existing credentials. If those credentials are rejected and the machine is still registered, it starts a repair pairing. The browser shows **Pair an Existing Machine Again** and identifies the machine being replaced. Verify the details and approve the new code. The machine keeps its teams. Its pairing date for password recovery starts again when it receives new credentials.

## Retire or uninstall a machine

To stop using a machine across your account, open the machine row’s menu in **Machines**, choose **Delete** and confirm. Its credentials are revoked. It leaves its teams and stops work when it receives the notice, immediately if connected or on its next connection. Its local working copies are kept. To use it again, run `sail login` on it, approve the new pairing and add it to the teams that need it.

To remove the installation from the computer, first save any work you need from its SailorBridge working copies. Run `sail uninstall` on that machine. It stops the service and removes `sail`, its service definition, the installer’s shell path entry and the entire `~/.sailorbridge/` directory. This includes credentials, account registrations, logs, local chat records, working copies and the backup copy of `sail`. Your own project directories and engine login directories are kept. To install again, use the command on **Pair a New Machine**.

## When it does not work

- If pairing reports missing Git, install Git and run `sail login` to continue. A missing engine login can be fixed separately with `claude login` or `codex login` before you start chat or a job.
- If the code expires, run `sail login` for a new one. If the machine name or **Key Code** differs, choose **Cancel Pairing** and check the terminal on the intended machine. If approval went through but the machine has not connected within 10 minutes, run `sail host status`, then `sail login` to reconnect.
- If a machine goes offline unexpectedly, check its network and service with `sail host status`. The default offline window is 90 seconds. The offline notification appears only after the machine has stayed offline for 10 minutes and clears when it returns.
- If an update fails, open the machine to read the reason and run the repair command shown as the user who installed `sail`. If the local backup cannot be used, use the install command from the pairing page.
- If the machine reports that the server identity has changed, it refuses the connection. Use `sail host status --trust` to inspect the saved fingerprint on the machine. For an expected identity change, run `sail login`, check the new fingerprint in the terminal and approve a new pairing.
- If `sail login` reports `origin_mismatch`, use the uninstall procedure above before switching addresses. Then copy the install command from the intended application’s **Machines** page. Unreadable local pairing credentials also require uninstalling and pairing again.
- If `sail uninstall` reports that the service could not confirm retirement, the local files have been removed. Open **Machines** and retire the entry there.
