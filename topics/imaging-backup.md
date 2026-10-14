# Imaging and backup

## What this means

**Imaging** (or **reimaging**) means putting a fresh company **Windows image** on a PC — a ready-made copy of Windows with company settings and apps. We do this for a new laptop, a broken profile, bad malware, or a PC that will not boot cleanly.

**Backup** means a copy of the user’s files so they are not lost. In modern offices that is often **OneDrive**, a home drive on a server, or Microsoft 365 — not a dusty USB. L1 must ask “where are your files?” **before** wiping a device.

L1 may start a reimage using a playbook (USB, PXE, Autopilot). L1 does not build the master image.

**Interview-ready definition:**

> Imaging is reinstalling the company’s standard Windows onto a PC. Backup is making sure the user’s files exist somewhere else first — usually OneDrive or a home drive. On L1 I would never wipe a laptop until I know where documents, browser bookmarks, and PSTs live, and I would warn the user what will be lost. I would then follow the reimage or Autopilot steps, enrol the device, and help them sign in. Building the gold image is L2 work.

## What L1 actually does with this day to day

1. **Before any wipe**  
   User says: “Just rebuild it.”  
   L1: check OneDrive sync status, Desktop/Documents redirection, browser profiles, Outlook PST/OST (OST is usually rebuilt), and saved passwords policy. Get user confirmation on the ticket.  
   Done: user knows what will survive.

2. **New PC / replacement**  
   User says: “My laptop died.”  
   L1: issue a stock device, start Autopilot or image, move licences if needed, remap printers.  
   Done: they can work on the new asset.

3. **Reimage a sick PC**  
   User says: “It is unusable, keep failing.”  
   L1: confirm backup, follow the wipe work instruction, BitLocker key if the disk is encrypted, enrol in Intune/AD.  
   Done: standard desktop, user signed in.

4. **OneDrive “files missing”**  
   User says: “Desktop is empty after rebuild.”  
   L1: sign into OneDrive, wait for sync, check Recycle Bin / restore.  
   Done: files back or restore escalated.

5. **User has data only on the old disk**  
   User says: “I never used OneDrive.”  
   L1: do not format yet. Ask desktop / backup team about disk recovery if policy allows. Be honest that local-only files are at risk.  
   Done: recovery attempted or user accepted loss in writing on the ticket.

6. **Backup of mail**  
   Mail in Microsoft 365 is already on the server. Extra PST on the desktop is a risk. L1 points them to cloud mail, not a USB dump against policy.  
   Done: explained.

7. **Failed Autopilot / image**  
   User says: stuck on setup screens.  
   L1: retry with wired network, capture error code, escalate to endpoint.  
   Done: error with L2, user on a loaner if possible.

**What L1 must not do**

- Do not reimage as the first step for a printer problem.
- Do not copy a user’s Personal Drive onto an unencrypted USB “as a favour.”
- Do not skip BitLocker / enrolment so the image “finishes faster.”
- Do not rebuild a shared kiosk without checking whose data is on it.

**When to escalate**

- Disk may be dying (backup first, then hardware).
- Autopilot/hash not registered.
- Need to restore from a backup product L1 cannot access.
- Suspected ransomware — follow security process before any wipe.

## How I would say this in an interview

> Imaging puts a clean company Windows install on a PC. Backup is making sure files are in OneDrive or another approved store first. On L1 I would confirm data location with the user, record it on the ticket, then follow the reimage or Autopilot process and enrol the device. I would not wipe first and ask later. If files were only on the local disk I would stop and escalate recovery rather than pretend they will come back.

## Likely interview questions

**1. What do you ask before a reimage?**

Where are Desktop, Documents, and Downloads stored? Is OneDrive showing “up to date”? Any local-only project files, Outlook PSTs, or browser exports? I need the user’s OK on the ticket.

**2. OneDrive was syncing. Will they lose mail?**

Microsoft 365 mail lives in the cloud. Outlook will reload. Local-only files that never synced can still be lost. I would separate mail from documents when I explain.

**3. What is Autopilot?**

A way to set up a new PC from the cloud when the user signs in, instead of a technician installing from USB every time. L1 still watches the process and handles errors.

**4. User wants everything copied to their personal Google Drive.**

That may break data-protection rules. I would use company OneDrive or the approved backup path only.

**5. When is reimage the wrong fix?**

When the issue is a password, printer, or one app. Reimage is costly in time and risk. I would exhaust standard fixes first unless the PC is clearly corrupt or infected per policy.

**6. BitLocker and imaging?**

The disk is encrypted. We need the recovery process or a supported wipe method. I would not “just format from a public USB” against the runbook.

**7. How do you close the ticket after a rebuild?**

Asset number, that the user signed in, OneDrive is syncing, Outlook/Teams open, remaining issues listed. Confirmation from the user.

## Words to use, and words to avoid

**Use**

- image / reimage, Autopilot, OneDrive sync, confirm data first, enrol, escalate recovery
- BitLocker, loaner laptop

**Avoid, or explain if you say them**

- “I’ll just format it”
- Ghost/MDT internals unless the company uses that name in the runbook
- Personal USB as the backup plan

## Good to know (not L1 daily work)

- **PXE** boot can load an image from the network in the office.
- **Gold image** is the master copy desktop engineering maintains.
- Some firms use **Windows Backup** or a third-party tool as well as OneDrive.
