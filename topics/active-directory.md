# Active Directory

## What this means

Active Directory (AD) is Microsoft's directory — a big, organised list of **who** can use the company computers and **what** they are allowed to do.

Think of a company as a building with a reception desk and a staff list:

- Every employee has an **account** (name, email, password).
- Every laptop or PC can be a **computer object** in that list.
- People are put into **groups** (for example "Finance" or "Printer-4th-Floor") so access is given to a group, not one person at a time.
- The **domain** is the company space AD looks after, like `company.local`.

AD sits on special Windows servers called **domain controllers**. L1 does not build those servers. L1 uses AD tools (or a self-service / ticketing portal that talks to AD) to help users.

**Interview-ready definition:**

> Active Directory is Microsoft's system for managing users, computers, and permissions in a Windows workplace. It stores each person's account, their password, which groups they belong to, and whether the account is active. On the Service Desk I would use it every day for things like unlocking accounts, resetting passwords, checking if a new starter's account exists, and confirming a user is in the right group for a shared drive or printer. I would not change server settings. If something looks like a directory or permission design issue, I would log the ticket clearly and escalate to L2.

## What L1 actually does with this day to day

These are typical L1 tickets, not admin-engineer work.

1. **Unlock an account**  
   User says: "I cannot log in. It says my account is locked."  
   L1: confirm who they are using the company's ID check, find the user in AD (or the unlock tool), unlock the account, ask them to try again, note the ticket.  
   Done: user can log in, ticket updated.

2. **Reset a password**  
   User says: "I forgot my password" or "I need it reset after a lockout."  
   L1: verify identity first (never reset for someone you cannot identify), reset via the approved tool, set "must change password at next logon" if that is policy, tell them how to set a new password, never email the password in plain text if policy forbids it, never share someone else's password.  
   Done: user signs in with a new password.

3. **Check why login fails**  
   User says: "Wrong username or password" or "account disabled."  
   L1: check the username spelling, whether the account is **enabled**, whether it is **locked**, whether it is **expired**, and whether they are connecting to the right domain / VPN.  
   Done: either a simple fix, or a clear note and escalate if the account should not be disabled.

4. **New starter cannot log in**  
   User / manager says: "My first day, no account" or "account exists but no email / no groups."  
   L1: check if the AD account exists and is enabled. If it is missing, this is usually a **service request** for another team (HR / IAM / L2), not something L1 invents. Log what is missing.  
   Done: user unblocked if the account is there; otherwise ticket routed to the right team.

5. **Leaver / disabled account**  
   Request: disable an account because someone left, or a user reports they still have access they should not.  
   L1: follow the company's leaver process only. Do not disable accounts because a colleague asked informally on chat. Check identity and the ticket. If L1 is not allowed to disable, raise it to the identity team.  
   Done: process followed, ticket recorded.

6. **Group / access for a drive, printer, or app**  
   User says: "I cannot open the Finance folder" or "I cannot use that printer."  
   L1: check if they are in the group that should have access (if L1 has read access to groups). If they are missing from the group, add them **only if policy allows L1 to do it**. If not, log a request for the owner / L2.  
   Done: access granted through the proper group, or escalated.

7. **Computer name / domain join problems (basic)**  
   User says: "This laptop is not on the network the usual way" or "I cannot log in with my work account on a new PC."  
   L1: gather the computer name, user name, error message, and whether the device is in AD. L1 usually does **not** join PCs to the domain unless trained and allowed.  
   Done: basic checks done, then desktop / L2 if the PC must be joined or rebuilt.

8. **Ticket quality**  
   Every AD action: who called, how you verified them, what you checked (locked / disabled / expired), what you changed, and the result.  
   Done: another engineer could replay the story from the ticket.

**What L1 must not do**

- Do not reset a password without verifying the person.
- Do not tell a caller a colleague's password or account status beyond what policy allows.
- Do not create, delete, or redesign OUs, GPOs, or domain controllers.
- Do not guess. If you are unsure, say so, capture the error, and escalate.

**When to escalate**

- Account should exist but was never created.
- Account is disabled and you are not allowed to enable it.
- Group membership needs an owner approval you cannot get.
- Login fails after unlock + password reset (could be replication, domain, or device).
- Anything that needs a change on a domain controller.

## How I would say this in an interview

> Active Directory is the system most Windows workplaces use to store staff accounts, computers, and permissions in one place. As L1 I would not design AD. I would use it, or the tools on top of it, to help users every day. Typical tickets are account lockouts, password resets, checking if an account is enabled or expired, and seeing whether someone is in the right group for a shared drive or printer. I would always verify the caller's identity before resetting a password, write clear notes on the ticket, and follow the company's process. If the account is missing, or the fix needs server or permission design work, I would escalate to L2 with what I already checked.

## Likely interview questions

**1. What is Active Directory, in simple terms?**

Active Directory is Microsoft's directory service. It is the central list of users, computers, and groups for a Windows company network. It controls who can log in and which resources they can use. L1 uses it to support logins and access. We do not build the AD servers ourselves.

**2. What AD tasks would you do on a normal L1 day?**

Unlock locked accounts, reset passwords after checking identity, check whether an account is enabled or expired, look up a user to confirm they exist, and check group membership for access issues like a shared folder or printer. I would log every step on the ticket. Bigger changes I would send to L2.

**3. A user says they are locked out. What do you do?**

I would open or take the ticket, verify who they are, find the account, confirm it is locked, unlock it, and ask them to try again. If they also forgot the password, I would reset it using the approved process, usually with a change-at-next-logon flag. I would note the time, the error, and the result. If it locks again immediately, I would ask what they are typing, check for a stale password on a phone or mapped drive, and escalate if it keeps happening.

**4. How do you verify a user before a password reset?**

I would follow the company's identity check — for example employee ID, manager, registered phone, or an approved self-service tool. I would not reset a password just because someone sounded confident on the phone. If I cannot verify them, I would refuse the reset, explain why, and offer a safe path such as calling back on the number on file or asking their manager to raise a ticket.

**5. What is the difference between a locked account and a disabled account?**

Locked usually means too many wrong passwords. L1 can often unlock it. Disabled means someone turned the account off on purpose, often a leaver or a security step. I would not enable a disabled account without the right process, because that can give access back to someone who should not have it.

**6. A new starter cannot log in. How do you handle it?**

I would check whether the AD account exists and is enabled, and whether they are using the correct username. If the account is there but locked, I would unlock and help them set a password. If the account does not exist, I would not create a random account myself unless that is my job. I would log a request for the identity / onboarding team with the user's name, start date, and manager, and explain the delay to the user.

**7. What is a group in AD, and why does L1 care?**

A group is a collection of users used to give the same access to many people. For example, a "Finance-Share" group can open a Finance folder. If one person cannot open that folder, L1 checks whether they are in the group. Access should be given through groups, not by sharing a password or copying files to a USB stick.

**8. What would you write on the ticket after an AD fix?**

Who contacted us, how I verified them, the username, what I found (locked, disabled, wrong password, missing group), what I did, whether the user confirmed it worked, and if I escalated, why and to whom. That protects the user and the next engineer.

## Words to use, and words to avoid

**Use**

- account, username, lockout, unlock, password reset, enabled, disabled, expired
- group / access group, ticket, verify identity, escalate to L2
- domain (the company's AD space)

**Avoid, or explain if you say them**

- "I would configure the domain controller" — that is not L1
- "I would write a GPO" — Group Policy is usually L2; say "I would not change Group Policy, I would escalate"
- "LDAP bind / Kerberos ticket" unless you can explain it simply; for L1 say "the login check against AD failed"
- "I'll just give them admin rights" — never casual admin access

## Good to know (not L1 daily work)

- AD runs on **domain controllers**. More than one exists so login still works if one server is down.
- **OU** (Organisational Unit) is a folder in AD for organising users and computers, often by department or location.
- **Group Policy (GPO)** pushes settings to PCs (screen lock, password rules). L1 does not design GPOs.
- **Azure AD / Entra ID** is Microsoft's cloud identity. Many companies now use both on-prem AD and Entra ID. If the job uses Microsoft 365, some password and MFA tasks happen in the cloud portal instead of the old AD console.
- Replication means AD copies changes between domain controllers. A reset might take a short time to show everywhere — if a user still fails after a reset, mention this and escalate rather than repeating random changes.
