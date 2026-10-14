# AnyDesk

## What this means

**AnyDesk** is a **remote support** app. It lets you see and control another PC over the internet after the user agrees, using an ID and a one-time code or an approved always-on setup.

Service Desks also use **TeamViewer**, **Quick Assist**, **BeyondTrust**, or **ScreenConnect**. The L1 rules are the same: **permission**, **identity**, **privacy**, and **the company’s approved tool only**.

AnyDesk is useful when the user is at home and you cannot use office **Remote Desktop**. It is also a favourite of **scammers**. L1 must never tell a user to install AnyDesk because a stranger on the phone asked.

**Interview-ready definition:**

> AnyDesk is a remote-control tool so I can fix a PC without sitting at the desk. On L1 I would only use the remote tool the company approves, get the user to confirm they can see my actions, and never ask them to install extra remote software from an email. I would verify who they are first, not leave the session unattended, and disconnect when finished. If the company does not use AnyDesk, I would say so and use the official tool instead.

## What L1 actually does with this day to day

1. **Start a support session**  
   User says: “Can you just jump on my PC?”  
   L1: use the approved client, share the ID the **user** sees, wait for them to accept. Explain you can see their screen.  
   Done: session connected with consent.

2. **Identity first**  
   Same as a password reset. A remote session is full control.  
   Done: you are sure who is at the keyboard.

3. **Fix inside the session**  
   Typical: Outlook, printers, drivers. Talk as you click so they are not scared.  
   Done: issue fixed or escalated, session ended.

4. **User was told to install AnyDesk by a “Microsoft caller”**  
   User says: “They said I have a virus, give them the code.”  
   L1: this is a **scam**. Tell them to hang up, do not give codes, run the company’s security steps, raise a security ticket.  
   Done: user safe, incident logged.

5. **Unapproved AnyDesk on a work PC**  
   User says: “My cousin uses it to help me.”  
   L1: follow policy — unofficial remote tools are a risk. Remove if required, explain the official path.  
   Done: only approved remote access remains.

6. **Session dropped**  
   User says: “You vanished.”  
   L1: call back, reconnect, do not assume the fix finished.  
   Done: outcome confirmed.

7. **After the call**  
   Close AnyDesk if it should not stay running, remove temporary admin if you used it, write the ticket.  
   Done: no forgotten remote access.

**What L1 must not do**

- Do not connect without the user knowing.
- Do not ask for AnyDesk from a personal email.
- Do not disable antivirus in the session to “make AnyDesk smoother.”
- Do not access HR/payroll files they did not ask you to fix.
- Do not keep a unattended access password on a user’s home PC unless that is a managed company device and policy allows it.

**When to escalate**

- Confirmed or suspected remote-access scam.
- Need for a tool you do not have (for example to a server).
- Policy question about installing AnyDesk at all.

## How I would say this in an interview

> AnyDesk is one brand of remote support. I would only use whatever remote tool the employer names, with the user’s consent, after I verify them. I would talk through what I am clicking, disconnect at the end, and write the ticket. If a user was asked by a stranger to install AnyDesk and read a code, I would treat that as a scam and follow the security process. I would not leave unofficial remote software on a work PC.

## Likely interview questions

**1. Why remote tools at L1?**

Many staff are at home. Remote view is faster than guessing over the phone, and you can see the real error.

**2. What is consent?**

The user accepts the prompt. I do not hide on their desktop. If they ask me to stop, I stop.

**3. Scam call: “Install AnyDesk, I’m from IT.”**

Real IT uses known numbers, tickets, and the official tool. I would tell friends and users: never give a remote code to someone you did not contact. At work I would log a security incident.

**4. AnyDesk vs Remote Desktop?**

AnyDesk (and similar) often works over the internet with a code. Company RDP usually needs VPN and is aimed at a PC name. L1 uses what the runbook says.

**5. Can you keep AnyDesk installed for next time?**

Only if the company packages it. Personal unattended access to a work laptop is a security problem.

**6. You see personal email on the screen.**

Look away from private content, ask them to close it, and only open what the ticket needs. Do not copy their files off the PC.

**7. Ticket notes after a remote session?**

Tool used, that consent was given, what you changed, session ended, user confirmed. No passwords.

## Words to use, and words to avoid

**Use**

- remote support, consent, approved tool, verify identity, disconnect, scam / social engineering
- ticket, security incident

**Avoid, or explain if you say them**

- “Install this random AnyDesk from a Google ad”
- Unattended access on unmanaged home PCs
- “I’ll stay logged in after you go to lunch”

## Good to know (not L1 daily work)

- AnyDesk, TeamViewer, and similar have had stolen-licence / fake-site problems — another reason to use the company source.
- **Quick Assist** is built into Windows and is common on Microsoft-heavy desks.
- Privileged remote to servers is a different, audited tool (PAM), not AnyDesk from L1.
