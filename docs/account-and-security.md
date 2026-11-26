[← SailorBridge](../README.md)

# Account and security

Your numeric **Captain ID** is your sign-in name. It stays with your account when you change your nickname, password or browser. Pair a machine you control while you can still sign in. You will need a paired machine if you forget your password.

## Create your account

1. Open the [application](https://app.sailorbridge.com) and choose **Register**. Enter the number you want, from 3 to 11 digits. If you see **Already claimed**, edit the number and check another.
2. Check what the page shows for that number. Ordinary 6–8 digit IDs and all 9–11 digit IDs are free. Shorter IDs and special patterns of up to 8 digits carry a one-time charge. For a paid number, save the **Redeem link** at checkout so you can finish registering on another device. [Pricing](https://www.sailorbridge.com/#pricing)
3. Set and confirm your password. You can pick a preset avatar or keep your initial. Complete the age confirmation and accept the **Terms of Service**, then choose **Register**. The application signs you in. [Pair your first machine](machines.md)

## Sign in and confirm a new browser

Enter your **Captain ID**, choose **Next**, then enter your **Password** and choose **Sign In**. If you have a paired machine, SailorBridge automatically asks for confirmation on a new browser. With two-step verification off, your password is enough in a recognized browser. Without a paired machine or two-step verification, a new browser can also sign in with just the password. Optional **Two-Step Verification** requires confirmation every time you sign in, even from a familiar browser.

On **Confirm It’s You**, use one of the methods offered.

- For **Authenticator Code**, enter the current code from your authenticator app.
- For **Machine Code**, run `sail confirm` in a terminal on a paired machine. Enter the eight-character code on the sign-in page.
- For **Browser Approval**, open a familiar browser where you’re already signed in. In the approval prompt, tap the two-digit number shown on the sign-in page. Approve only a sign-in you started. If someone else started it, choose **Not Me**.

## Set your profile and protect your sign-in

Open **Me**. You can set a **Nickname** and choose an **Avatar** from the gallery. **Language** sets the display language and the language of replies, starting with the next chat turn or job. Under **Response Style**, choose **Novice** for more explanation or **Expert** for shorter replies.

Open **Security**, then **Two-Step Verification**. Choose **Enable**, verify your password and scan the QR code with your authenticator app. Enter its current code and choose **Confirm and Enable**. To turn this off, choose **Disable Two-Step Verification** and provide your password and a fresh code.

To change your password, enter **Current Password**, **New Password** and **Confirm New Password** under **Security**. Enter an authenticator code if two-step verification is on. After the change, this browser is signed in and other sessions are signed out.

<a name="check-activity-and-device-keys"></a>

## Check activity and devices

Open **Me**, then **Security** and **Recent Security Events**. The list covers the last 90 days. A successful sign-in on a new browser asks whether it was yours. Choose **It Was Me** or **Not Me**. Each browser tracks its own acknowledgments. Unsuccessful sign-ins appear in the list without an approval prompt.

If you see a sign-in you did not make, change your password. **Sign Out Other Sessions** signs out your other browsers and apps while keeping this session open. If you only need to disconnect one machine, retire it from **Machines**. **Revoke All Machines** disconnects every paired machine. You will need to pair each one again before it can work or provide a recovery code. You can also delete a single security record after confirmation. Other browsers still receive their own alerts until they acknowledge the event.

In **Security**, open **Devices** to see your apps and paired machines. Select a device and choose **Remove** to stop it from authorizing new work. This signs that app out or disconnects that machine. For a missing device, choose **Lost or Stolen**. SailorBridge will also stop accepting content that device previously authorized.

## Recover a forgotten password

1. In a terminal on a paired machine, run `sail recover`. It prints your Captain ID and an eight-character, single-use recovery code valid for 10 minutes. Getting another code on the same machine replaces the first.
2. On the sign-in page choose **Forgot password?**. Enter the ID and **Recovery Code** from the terminal. Check the machine name and pairing date on the page before entering your new password.
3. Follow the recovery path shown. The machine’s age is measured from its most recent pairing or credential repair.

| Machine used to recover | Two-step verification | What happens |
| --- | --- | --- |
| Paired less than 72 hours ago | Any setting | Submit a 72-hour recovery request, even if you have an authenticator code. |
| Paired at least 72 hours ago | Off, or enabled less than 72 hours ago | Reset immediately using the recovery code. Recovery turns off any recently enabled two-step verification. |
| Paired at least 72 hours ago | Enabled for at least 72 hours | Enter an authenticator code to reset immediately and keep two-step verification. Without it, submit a 72-hour recovery request. |

If you need to wait, choose **Submit a 72-Hour Recovery Request** and follow the time shown on the recovery page. Signed-in devices are notified. You can choose **Cancel This Recovery** on one of them. A successful sign-in also cancels the request. When the reset takes effect, use your new password to sign in. Waiting recovery resets two-step verification.

After recovery, check **Paired on** in **Machines** and retire any machine you do not recognize. You can enable two-step verification again in **Security**.

## Sign out or delete your account

Use **Sign Out** in **Me** to end this browser’s session. To close the account, choose **Delete Account**, review the affected teams and machines, and confirm with your password and an authenticator code if enabled. Deletion signs out your devices, revokes your machines and cancels your subscription. Sign in within seven days to undo the request. Password recovery is unavailable during that period because the machines have been revoked. After the deadline the account is deleted and its number stays retired.

## When it does not work

- After five failed sign-in attempts within 15 minutes, the default lock lasts 15 minutes. Wait for the time shown. An authenticator code can be used once. If you just used it, wait for the next one.
- If browser confirmation expired or you tapped the wrong number, start the sign-in again. You can also use an offered code method. Run `sail confirm` for a fresh sign-in code and `sail recover` for a fresh password recovery code.
- If a machine cannot issue a recovery code, try another paired machine on your account. If none has valid credentials, the account cannot be recovered. Register a new ID.
