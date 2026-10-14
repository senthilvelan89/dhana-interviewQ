# Patching using Intune

## What this means

A **patch** (or update) is a Microsoft or vendor fix for Windows or an app. It closes security holes and fixes bugs. **Patching** is the job of getting those updates onto company devices.

**Intune** (Microsoft Intune, part of Microsoft 365 / Endpoint Manager) is the cloud tool that manages laptops and phones. The company can require a PIN, install apps, and **push Windows updates** without visiting each desk.

L1 does not design **update rings** (the schedule that says “pilot PCs first, then everyone”). L1 helps when a user is stuck: pending restart, update failed, or the device is **not compliant** (does not meet company rules, so email or VPN may be blocked).

**Interview-ready definition:**

> Intune is Microsoft’s cloud tool for managing company PCs and phones. Patching with Intune means Windows and app updates are sent to devices over the internet, on a schedule the company sets. On L1 I would not build that schedule. I would help users whose PC is waiting for a restart, whose update failed, or who cannot get into email because the device is marked non-compliant. I would check Intune or Company Portal if I have access, gather the device name and error, and escalate policy or ring issues to L2.

## What L1 actually does with this day to day

1. **Pending restart**  
   User says: “It keeps asking me to restart” or “I have not restarted in weeks.”  
   L1: explain that some patches only finish after a reboot. Agree a time, ask them to save work, restart, confirm Windows is up to date.  
   Done: restart completed, ticket noted.

2. **Cannot access email / VPN because device is non-compliant**  
   User says: “Outlook blocked” or “Company Portal says not compliant.”  
   L1: check compliance — often encryption, PIN, or missing updates. Guide them to install updates and reboot. Do not bypass compliance.  
   Done: device becomes compliant, or escalate if the policy looks wrong.

3. **Update stuck at 0% / failed**  
   User says: “Windows Update has been running all day.”  
   L1: check disk space, Wi-Fi vs office network, and whether they are on VPN. Retry after reboot. Capture the error code.  
   Done: update finishes, or ticket to endpoint / L2 with the code.

4. **Is the device in Intune?**  
   User says: “I never get company apps or updates.”  
   L1: confirm the PC is **enrolled** (joined to the company in Intune). If it is a home PC that was never enrolled, that is a request, not a patch failure.  
   Done: enrolment issue identified and routed.

5. **BitLocker / PIN after patch**  
   User says: “After the update it asked for a recovery key.”  
   L1: do **not** guess BitLocker keys from chat. Follow the company’s key recovery process after identity check.  
   Done: user in, or escalated securely.

6. **Explain why patching matters**  
   User says: “I always click Remind me later.”  
   L1: calmly explain security and that delaying too long can lock them out of company systems. Offer a restart window.  
   Done: user understands, restart booked, ticket updated.

7. **App updates via Company Portal**  
   User says: “Teams / Company Portal wants an update.”  
   L1: help them open Company Portal, install required apps, retry.  
   Done: required apps present.

**What L1 must not do**

- Do not turn off Windows Update or Intune to “make it faster.”
- Do not exclude a VIP from patching without the change process.
- Do not share BitLocker recovery keys without identity checks.
- Do not change update rings or compliance policies.

**When to escalate**

- Same error on many PCs (possible ring or server issue).
- Device will not enrol.
- Compliance looks wrong for a healthy PC.
- Update error codes you cannot clear with reboot, space, and retry.

## How I would say this in an interview

> Patching is installing security and quality updates on PCs. In many companies Intune does that from the cloud, so we do not walk around with a USB stick. As L1 I would help with restarts, failed updates, and devices marked non-compliant, which can block email or VPN. I would check disk space, network, and whether the device is enrolled, write the error on the ticket, and never switch updates off. Policy and update-ring changes I would leave to L2.

## Likely interview questions

**1. What is Intune?**

Intune is Microsoft’s cloud endpoint manager. It can enrol devices, push apps, set a PIN, and deliver Windows updates. L1 supports the user and the device; L2 designs the policies.

**2. What does “non-compliant” mean?**

The PC does not meet a company rule — for example it is missing patches, BitLocker is off, or there is no PIN. Access to mail or VPN can be blocked on purpose until it is fixed. L1 helps the user meet the rule rather than bypassing it.

**3. A user refuses to restart. What do you do?**

I would explain that some updates only finish after a reboot and that delay can be a security risk. I would offer a time that fits their work and set a reminder. I would not disable the update. If they still refuse and the device will be blocked, I would note that on the ticket and follow policy, including manager or L2 if needed.

**4. How do you treat a BitLocker screen after an update?**

As a security incident-style request: verify the user, recover the key only through the approved tool, never paste keys into open chat, and log who requested it. If I cannot find the key, I escalate. I do not tell them to “just format the disk” first.

**5. Why not delay all patches until the weekend?**

Some fixes are urgent. Intune rings already stagger updates so the whole company does not break at once. L1 follows that design. A user delay of a few hours is normal; weeks is not.

**6. What do you put on the ticket for a failed patch?**

Device name, Intune/compliance status if you can see it, Windows version, error code, free disk space, whether they rebooted, network (office / home / VPN), and next action.

**7. Is patching only Windows?**

No. Office, Teams, and other Company Portal apps also update. The user’s symptom might be an app, not the whole OS.

## Words to use, and words to avoid

**Use**

- patch / update, restart, enrolled, compliant / non-compliant, Company Portal, escalate
- error code, disk space, BitLocker recovery (with identity check)

**Avoid, or explain if you say them**

- “I’ll pause the update ring for the company”
- “We’ll skip this CU / disable Wuauserv”
- WSUS internals unless the company still uses it — say “our patching tool, often Intune”

## Good to know (not L1 daily work)

- **Update rings** control when a group of devices gets a Windows feature or quality update.
- **Autopatch** is a Microsoft service that can run those rings for you.
- Older companies used **WSUS** or SCCM/ConfigMgr on-site; Intune is the cloud version of that idea.
- Feature updates (21H2 → 24H2) are larger than monthly security patches.
