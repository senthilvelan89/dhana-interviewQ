# Windows 10 / 11 administration (L1)

## What this means

**Windows 10 and Windows 11** are the operating systems on most office PCs. “Admin” at L1 does **not** mean you are a domain architect. It means you can help a user with the everyday Windows tasks: sign-in, settings, disk, updates, apps, and when to use **local administrator** rights.

A **standard user** cannot install most software. An **administrator** can. Company PCs should stay standard for safety. L1 may use a controlled **admin account** or a privileged access tool to install an approved app, then log off admin.

**UAC** (User Account Control) is the “Do you want to allow this?” prompt. That prompt is normal, not a virus by itself.

**Interview-ready definition:**

> L1 Windows work is helping users on Windows 10 or 11: logon problems, settings, printers, disk space, updates, and installing approved apps with admin rights only when policy allows. I would work as a standard user most of the time and not leave a user as a local admin. I would use Settings, Task Manager, and the company’s tools, restart when it is safe, and escalate OS corruption, domain join, or image issues to desktop engineering.

## What L1 actually does with this day to day

1. **Slow PC / app not responding**  
   User says: “Everything is frozen.”  
   L1: Task Manager to end the stuck app, check disk space and startup load, reboot if needed.  
   Done: usable PC, or performance ticket with what you saw.

2. **Windows updates and restart**  
   User says: “It must restart” or “update failed.”  
   L1: see Intune patching topic — save work, reboot, check compliance.  
   Done: updated or error logged.

3. **Install an approved app**  
   User says: “I need Zoom / a font / a viewer.”  
   L1: Company Portal or packaged installer with admin elevation. Do not use a random download.  
   Done: app installed, user still not a permanent local admin.

4. **Local admin request**  
   User says: “Make me admin so I can install things.”  
   L1: refuse as default. Explain risk. Raise a request if the role genuinely needs it (rare).  
   Done: policy followed.

5. **Sign-in, PIN, Hello, password**  
   User says: “PIN forgotten” or “Hello face not working.”  
   L1: sign in with password if possible, reset PIN from Settings or the company process, check account lockout in AD/Entra.  
   Done: user in.

6. **Settings the user cannot find (Win10 vs Win11)**  
   User says: “There is no Control Panel like my old PC.”  
   L1: Windows 11 Settings layout differs. Help them find printers, Wi-Fi, display. Stay patient.  
   Done: setting changed.

7. **Profile / desktop missing**  
   User says: “My files vanished after login.”  
   L1: check if they are on a temporary profile, OneDrive Known Folder Move, or the wrong account. Do not format first.  
   Done: files found or profile repair escalated.

**What L1 must not do**

- Do not leave the user in the local Administrators group “temporarily” and forget.
- Do not disable UAC, Defender, or BitLocker to make software install.
- Do not run unknown `.exe` from email as admin.
- Do not use Safe Mode as the first step for every ticket.

**When to escalate**

- Blue screens repeating, disk errors, bitlocker recovery that fails.
- Domain join / Azure AD join / Autopilot failures.
- Corrupt user profile that needs rebuild.
- Need for in-place upgrade 10 → 11.

## How I would say this in an interview

> On L1, Windows 10 and 11 admin means supporting the user’s PC: logon, settings, disk space, updates, and approved software. I would keep them as a standard user and only elevate with the company’s tool when an approved app needs it. I would not turn off security features. If the profile is corrupt or the device will not join the company, I would collect Event Viewer basics and escalate to the desktop team.

## Likely interview questions

**1. Why should users not be local admin?**

Malware and accidental changes have more power. Installing random software also creates unsupportable PCs. We use a portal or packaged apps instead.

**2. What is UAC?**

A prompt that asks permission before software makes a system change. I would not teach users to click Yes on every prompt. If an approved installer needs it, I would use the admin process.

**3. Windows 10 vs 11 for L1?**

Same job, different Settings screens and some features (like Widgets). The support steps — reboot, disk, updates, account — are the same. I would not refuse to help because the Start menu looks different.

**4. PC is very slow. First checks?**

Restart if they have not, free disk space, how many browsers are open, pending updates, and whether it started after a specific app. Then escalate hardware or image issues.

**5. How do you install software on a locked-down PC?**

Company Portal, Software Center, or a packaged request. If it is not in the catalogue, raise a request for packaging — I would not bypass AppLocker.

**6. User lost their Windows PIN.**

They can often still use the password. Then we reset Windows Hello PIN from Settings or an account tool. I would also check the cloud/AD account if password fails.

**7. What is an in-place upgrade?**

Installing Windows 11 over 10 while keeping files, when the PC is eligible. L1 might start it from a company instruction; failures go to desktop engineering.

## Words to use, and words to avoid

**Use**

- standard user, local admin (only when approved), UAC, Settings, Task Manager, Company Portal
- Windows 10 / 11, restart, escalate profile or join issues

**Avoid, or explain if you say them**

- “I’ll add everyone to Administrators”
- “Disable Defender / UAC / BitLocker”
- Registry hacking as a first-line habit

## Good to know (not L1 daily work)

- **Autopilot** and **Entra join** replace some old domain-join imaging.
- **AppLocker / WDAC** can block unofficial installers on purpose.
- Event Viewer is useful; L1 should copy the **error**, not spend hours hunting.
