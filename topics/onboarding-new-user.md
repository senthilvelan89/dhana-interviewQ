# Onboarding a new user

## What this means

**Onboarding** is the process of getting a **new starter** ready for day one: account, laptop, email, access, and a welcome so they can do their job.

It is usually a **service request** (something we planned), not an **incident** (something broken). HR or the manager raises it before the start date. L1 often completes a checklist: account exists, licence on, laptop handed over, password set, MFA registered, printers and Teams working.

L1 does not invent access. Access should match the job role and manager approval.

**Interview-ready definition:**

> Onboarding is preparing a new employee’s IT: account, laptop, mailbox, groups, and first login. On L1 I would follow the company’s checklist rather than improvising. I would check the account is enabled, the Microsoft 365 licence is there, help them set a password and MFA, confirm Outlook and Teams open, and map standard printers or drives. If the account was never created, I would route it to identity / HR, not create a random user. I would treat it as a request with a due date, and keep the manager updated if something will miss day one.

## What L1 actually does with this day to day

1. **Check the request is complete**  
   Ticket says: “New starter Monday.”  
   L1: name, start date, manager, department, location, laptop required, extra systems. If details are missing, ask before the day.  
   Done: checklist can actually be finished.

2. **Account and mailbox**  
   User says: “I cannot log in on day one.”  
   L1: confirm AD / Entra account exists and is **enabled**, licence assigned, mailbox present. Unlock or password-reset after identity check (manager on site is a common check).  
   Done: they sign in.

3. **First login, password, MFA**  
   User says: “It wants a code I do not have.”  
   L1: walk through password change and MFA registration with the company authenticator. Do not skip MFA.  
   Done: they can sign in without the temporary password.

4. **Laptop handover**  
   User says: “Blank laptop” or “Autopilot sitting on a screen.”  
   L1: follow the imaging / Autopilot work instruction, connect to network, wait for Company Portal apps. Do not skip encryption.  
   Done: they reach the desktop with work apps, or desktop team engaged.

5. **Standard access**  
   User says: “No shared drive / no Finance app.”  
   L1: add **role groups** from the request only. Extra access needs manager approval.  
   Done: standard access in place; extras requested separately.

6. **Show the basics**  
   User says: “Where is email?”  
   L1: Outlook, Teams, VPN if remote, how to raise a ticket, password rules. Short and kind — they are new.  
   Done: they know how to get help again.

7. **Leaver vs starter mix-up**  
   Ticket is for a starter but the name matches a leaver.  
   L1: do not reuse an old account casually. Flag identity.  
   Done: correct unique account, or IAM team involved.

**What L1 must not do**

- Do not copy a colleague’s mailbox or files as a shortcut without process.
- Do not grant admin rights “so they can install apps.”
- Do not set a weak shared password like `Welcome123` and leave it.
- Do not onboard from a chat message with no ticket.

**When to escalate**

- Account not created and L1 cannot create users.
- Laptop not in stock / Autopilot fails.
- Access to a system L1 does not control (payroll, clinical, finance ERP).
- Start date is today and several steps are still red — tell the manager early.

## How I would say this in an interview

> Onboarding is making a new starter productive on day one: account, device, email, MFA, and standard access. As L1 I would work from a checklist and a ticket, not from a casual chat. I would verify the account and licence, help with first login and MFA, confirm Outlook and Teams, and only add groups that were requested. If something will miss the start date I would tell the manager early and escalate identity or equipment issues. I would not skip security steps to go faster.

## Likely interview questions

**1. Incident or request?**

Onboarding is a service request — planned work with a date. If their account is broken on day one, that part becomes an incident, but the overall process is still onboarding.

**2. The manager phones: “Just clone John’s access.”**

I would not clone blindly. I would use the role-based groups on the form, and ask the manager to approve extras on the ticket. Cloning often copies access the new person should not have.

**3. How do you prove who the new starter is?**

Follow company ID checks: photo ID, manager present, HR ticket. I would not reset a password for someone who only knows the name.

**4. What if the laptop is not ready and they start tomorrow?**

I would say so immediately, offer a loaner if policy has one, and keep the ticket and manager updated. Surprise on the morning is worse than an honest delay.

**5. Which apps do you check before closing?**

Sign-in, Outlook, Teams, OneDrive or home drive, VPN if they are remote, and Company Portal if used. I would ask the user to send a test email.

**6. Why MFA on day one?**

Because a new account with only a temporary password is easy to abuse. Registering MFA at handover is normal L1 work.

**7. What goes on the ticket when you close onboarding?**

What was completed, what is still pending (and who owns it), device asset number, and that the user could sign in. Pending extras stay as child tasks, not hidden.

## Words to use, and words to avoid

**Use**

- new starter, service request, checklist, licence, MFA, standard access, manager approval
- asset / laptop handover, escalate early

**Avoid, or explain if you say them**

- “I’ll clone John’s account”
- “We’ll skip MFA until next week”
- “I’ll make them a local admin”

## Good to know (not L1 daily work)

- **Joiner-Mover-Leaver (JML)** is the identity lifecycle. Onboarding is the joiner step.
- **Autopilot** can build a new laptop from the cloud during first login.
- Some firms use **IAM** (Identity and Access Management) tools; L1 still does the human checklist.
