# Remote Desktop and solving issues remotely

## What this means

**Remote Desktop** (RDP — Remote Desktop Protocol) is a Windows feature that shows you another PC’s screen and lets you use it as if you were there. In companies you often connect to a **PC name** or a **jump box** after **VPN**.

“Solving issues remotely” is the whole L1 idea: fix without a desk visit, using RDP, Quick Assist, AnyDesk, or the company’s support tool. You still need a **ticket**, **identity checks**, and **clear talking**.

RDP to a **user’s locked laptop at home** often fails unless they are on VPN and policy allows it. That is why Service Desks also use assisted tools where the user clicks Accept.

**Interview-ready definition:**

> Remote Desktop is Windows’ way to control another PC over the network. On L1 I would use the company’s remote method — RDP after VPN, or an assisted tool if the user must click Accept — to see the error myself. I would confirm who I am connecting to, explain what I am doing, fix the issue, sign out, and update the ticket. I would not expose RDP to the open internet or leave myself logged on as admin on their desktop.

## What L1 actually does with this day to day

1. **Choose the right remote method**  
   Office PC on the network: RDP or support agent may work. Home user not on VPN: assisted tool (Quick Assist / approved app).  
   Done: connected without fighting the wrong method.

2. **Connect with RDP (when allowed)**  
   User says: “You can jump on my desktop.”  
   L1: VPN if required, correct hostname, your **own** support account (not theirs), MFA.  
   Done: session open, user knows you are there.

3. **User already logged on**  
   RDP may kick them to the lock screen. Warn them first: “You might see a lock; I am still working.”  
   Done: no panic hang-up.

4. **Fix, then prove it**  
   Reproduce the issue, apply the standard fix, ask them to test after you disconnect if you took over the session.  
   Done: user confirms, not only you.

5. **Cannot connect**  
   User says: “RDP failed.”  
   L1: VPN, PC is on, hostname, firewall, they must allow Remote Desktop if policy uses it. Do not “open 3389 on the home router.”  
   Done: switch to assisted tool or escalate.

6. **Remote to a server**  
   Usually **not** L1. If a runbook says otherwise, use a jump host and your named admin, never a shared password.  
   Done: stayed in policy.

7. **End the session cleanly**  
   Sign out or disconnect per the instruction, remove shadow/admin if used, note the ticket.  
   Done: no leftover session.

**What L1 must not do**

- Do not enable RDP through a home public IP or a personal firewall hole.
- Do not use the user’s password to RDP “because it is easier.”
- Do not lock the user out and go to lunch.
- Do not remote in and read mail that is not the ticket.

**When to escalate**

- Need for console / iLO / out-of-band access.
- Entire RDP farm down.
- Security: unexpected RDP logons on a PC.
- Local visit required (broken screen, no network at all).

## How I would say this in an interview

> Solving issues remotely means I use the company’s approved connection — often Remote Desktop on the office network, or an assisted tool when the user is at home — so I can see the problem instead of guessing. I would verify the user, warn them if their session will lock, fix the issue, sign out, and write notes. I would not open Remote Desktop to the internet. If I cannot connect I would change method or arrange a visit, not weaken the firewall.

## Likely interview questions

**1. What is RDP?**

Remote Desktop Protocol: Microsoft’s remote screen and keyboard into a Windows PC or server, usually inside the company network or over VPN.

**2. User at home, RDP fails, websites work.**

They probably need VPN, or RDP is not offered on home laptops. I would use Quick Assist or the approved support tool instead of exposing RDP.

**3. Why not log in as the user?**

Audit and password policy. I should use my named support account. Using their password also means I might see things I should not, and I cannot prove who did what.

**4. Difference between disconnect and sign out?**

Disconnect leaves their apps running. Sign out closes the session. On a user’s PC I follow the runbook so I do not kill their unsaved work. I would ask them to save first.

**5. How do you keep the user comfortable?**

Tell them when you connect, narrate the clicks, agree before reboot, and stop if they take the mouse to show you something.

**6. NLA — have you heard of it?**

Network Level Authentication: Windows asks for credentials before a full desktop. If RDP fails with an NLA error, I would capture it for L2 rather than turning NLA off for the whole estate.

**7. When do you visit in person?**

No power, dead screen, no network at all, or hardware swap. Remote first when the device is reachable.

## Words to use, and words to avoid

**Use**

- Remote Desktop / RDP, VPN, hostname, assisted support, consent, sign out, ticket
- named admin account, do not open to the internet

**Avoid, or explain if you say them**

- “Port-forward 3389 on their home router”
- Shared “itadmin” passwords
- Shadowing a session without telling them (unless a legal, documented process exists)

## Good to know (not L1 daily work)

- **Quick Assist** and **Remote Help** (Intune) are Microsoft-assisted alternatives to RDP.
- **Jump servers** sit between you and production. L2/L3 use them; L1 usually does not.
- RDP logs are useful in security reviews — another reason to use your own ID.
