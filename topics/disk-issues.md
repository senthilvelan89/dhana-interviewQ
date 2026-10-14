# Disk issues

## What this means

The **disk** (hard drive or **SSD**) is where Windows and files live. Users feel disk problems as: “disk full,” PC very slow, files will not save, unusual noises on old spinning drives, or Windows reporting errors.

**Disk full** is the most common L1 ticket. Windows needs free space for updates and temp files. **OneDrive Files On-Demand** can make folders look full of files while they are actually in the cloud.

L1 cleans space safely, checks whether the disk is failing, and does **not** run destructive disk tools as a first click.

**Interview-ready definition:**

> Disk issues are about space, speed, or a drive that may be failing. On L1 I would check free space, empty Recycle Bin and temp files with the company’s approved cleanup, look at OneDrive, and ask if errors started suddenly. I would not format the disk to “make space.” If Windows reports disk failure, or the PC bluescreens around storage, I would back up what we can and escalate for hardware replacement.

## What L1 actually does with this day to day

1. **Disk full**  
   User says: “Not enough space on C:.”  
   L1: check storage in Settings, Recycle Bin, Downloads, old Outlook OSTs, unused installers. Use Storage Sense or Disk Cleanup as approved.  
   Done: enough free space for Windows (often 10%+ as a rule of thumb), user can save.

2. **OneDrive filling the disk**  
   User says: “C: filled after I mirrored Desktop.”  
   L1: explain Files On-Demand, free up local copies of large folders they do not need offline. Do not delete the cloud copies.  
   Done: space back, files still in OneDrive.

3. **Cannot save a file**  
   User says: “Word cannot save.”  
   L1: disk full, permissions, or OneDrive pause. Check the path.  
   Done: save works.

4. **Slow PC, disk at 100%**  
   User says: “Disk 100% in Task Manager.”  
   L1: pending updates, indexing, failing HDD. Reboot, check for updates, note if it is an old spinning disk. Escalate if it stays at 100%.  
   Done: improved, or hardware ticket.

5. **Windows disk error message**  
   User says: “Windows detected a hard disk problem.”  
   L1: treat as urgent for data. Confirm backup/OneDrive, do not ignore. Escalate for disk replacement. **chkdsk** only if the work instruction says so, and warn it can take hours.  
   Done: data path confirmed, hardware logged.

6. **External / USB disk**  
   User says: “My USB stick not showing.”  
   L1: another port, Disk Management if trained, encryption (BitLocker To Go). Do not format if they need the data.  
   Done: visible, or recovery/escalation.

7. **Temp profile because disk is full**  
   User says: “My desktop reset.”  
   L1: classic symptom of a full disk. Free space, reboot, profile should load.  
   Done: normal profile, space remains.

**What L1 must not do**

- Do not delete Windows or `Program Files` to free space.
- Do not format C: or D: because it looks messy.
- Do not run random “registry cleaner / driver booster” disk tools.
- Do not ignore SMART / Windows failure warnings.

**When to escalate**

- Repeated disk warnings, clicking HDD, SSD not detected.
- Need for chkdsk / imaging / replacement.
- Possible ransomware encrypting files (security process).
- RAID / server disks — never L1 on a shared server.

## How I would say this in an interview

> Most disk tickets at L1 are a full C: drive. I would check space, clean safe items, and see if OneDrive has made lots of files local. If Windows says the disk is failing I would focus on backup and a hardware replacement, not more cleanup tricks. I would not format the drive or delete Windows folders. Slow “disk 100%” on an old laptop I would note and escalate if it does not improve after updates and a reboot.

## Likely interview questions

**1. How do you free space safely?**

Recycle Bin, Downloads, old installers, Storage Sense, empty Deleted mail if mailbox is on disk cache, OneDrive “Free up space.” Then check Storage settings to see what is using the disk.

**2. How much free space is enough?**

Enough for Windows updates — I would aim for several GB free, not 0 bytes. Exact policy varies. If we cannot get there, escalate.

**3. What is Files On-Demand?**

OneDrive can show files in Explorer without storing every byte on C:. “Free up space” keeps them in the cloud. “Always keep on this device” does the opposite.

**4. User asks you to format D: which has project files.**

I would refuse until we confirm backup. Format is permanent. I would involve them and a lead if they still insist.

**5. chkdsk — would you run it?**

Only with a work instruction, because it can lock the PC for a long time and is not a substitute for a dying disk. I would warn the user and book a window.

**6. SSD vs HDD in simple terms?**

SSD is faster and has no spinning platters. HDD can be slower and may click when dying. L1 still treats both as “the disk.”

**7. Ticket notes?**

Free space before/after, what you deleted (categories, not private file names), OneDrive status, any Windows disk warning, next step.

## Words to use, and words to avoid

**Use**

- free space, C: drive, Recycle Bin, OneDrive, Storage Sense, escalate hardware
- do not format, backup first

**Avoid, or explain if you say them**

- “I’ll wipe C:”
- Random `diskpart clean` on the wrong disk
- Defrag as a miracle on a failing SSD

## Good to know (not L1 daily work)

- **SMART** is the disk’s own health report; L2/vendor tools read it.
- **chkdsk** repairs file system errors; it does not replace a dying drive.
- Encryption (BitLocker) stays on during normal cleanup — that is good.
