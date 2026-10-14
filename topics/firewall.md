# Firewall

## What this means

A **firewall** is a security filter. It allows or blocks network traffic using rules.

There are two places L1 meets it:

- **Windows Firewall** (or a company endpoint firewall) on the laptop — can block an app from using the network.
- The **company / perimeter firewall** — a shared device that protects the whole office and the VPN. L1 does **not** add rules there.

A firewall is not antivirus, but they work together. If a user says “the firewall is blocking me,” L1 must find **which** firewall and whether the block is **meant** to happen.

**Interview-ready definition:**

> A firewall is a set of allow and block rules for network traffic. On a PC that is Windows Firewall; at the edge of the company it is a dedicated firewall L2 or the network team own. On L1 I would check whether an app is blocked on the laptop, whether the user is on the right network or VPN, and whether the block is a security policy I must not switch off. I would never open ports on the company firewall myself. I would log the app, error, source and destination if I have them, and escalate a genuine rule request as a change.

## What L1 actually does with this day to day

1. **App cannot connect**  
   User says: “The app cannot reach the server.”  
   L1: confirm VPN/office network, try a known working user, read the exact error. Check if Windows Firewall notified them.  
   Done: allowed if policy says the app is standard, or request raised.

2. **Windows Firewall prompt**  
   User says: “Windows asked to allow an app.”  
   L1: only allow if it is a company-approved app. Do not allow unknown tools.  
   Done: approved app works; unknown app refused and noted.

3. **Website blocked**  
   User says: “This site is blocked.”  
   L1: many blocks are **web filter / proxy / firewall** policy (gambling, malware). If it is a business site, raise a request with the URL, do not teach them a bypass.  
   Done: explained, or exception requested through process.

4. **After a network change, something broke**  
   User says: “Finance app died after we moved floor.”  
   L1: gather floor, IP, whether others on that floor work. Could be firewall zone. Escalate, do not guess rules.  
   Done: facts with network team.

5. **Inbound Remote Desktop blocked**  
   User says: “IT cannot RDP to me.”  
   L1: use the **approved** remote tool. Do not turn off the firewall to “make RDP work” on a home PC.  
   Done: remote session via supported method.

6. **Explain a security block to a user**  
   Stay polite: the block may be protecting them. Offer the request path.  
   Done: user understands next step.

7. **Home vs work profile**  
   Windows Firewall has Domain / Private / Public profiles. A wrongly classified network can block things. L1 can check the network profile; L1 should not set the office LAN to Public as a “fix.”  
   Done: profile corrected only per work instruction.

**What L1 must not do**

- Do not disable Windows Firewall because it is inconvenient.
- Do not add any-any allow rules on a company firewall.
- Do not tell users to use a personal VPN to bypass the company filter.
- Do not open attacker-style port scans on the company network.

**When to escalate**

- Need for a new firewall rule (this is a **change**, with approval).
- Many users blocked from one system.
- Suspected malware generating firewall logs.
- You cannot tell endpoint firewall from perimeter firewall.

## How I would say this in an interview

> A firewall allows or blocks traffic using rules. L1 sees it as Windows Firewall on the PC and the company firewall we do not configure. I would check the app, the network, and whether the block is policy. I would never turn the firewall off to save time. If a business app needs a new rule, I would raise a change for the network or security team with the details, and keep the user informed.

## Likely interview questions

**1. What does a firewall do?**

It filters network traffic. Allowed traffic passes; the rest is blocked, based on rules the organisation sets.

**2. Would you turn Windows Firewall off to test?**

Not as a standard fix. It weakens the PC. I would check the app rule or escalate. Some work instructions allow a short test on a standard image — I would follow that, then turn it back, and still not leave it off.

**3. User wants YouTube unblocked.**

That is a policy request, not an incident I solve with a workaround. I would explain how to ask, with manager approval if required.

**4. Difference between firewall and antivirus?**

Firewall controls network connections. Antivirus looks for malicious files and behaviour. A PC needs both.

**5. What information does L2 need for a rule request?**

Who needs it, which application, source (user/PC) and destination (server or URL), port if known, and business reason. I would not invent port numbers.

**6. Home user, game firewall vs work PC.**

Work PCs stay locked down. I would not copy home gaming firewall habits onto a company laptop.

**7. What do you write on the ticket?**

App name, error, whether others are affected, network (office/VPN/home), any Windows Firewall message, and that I did not disable the firewall.

## Words to use, and words to avoid

**Use**

- allow / block, Windows Firewall, company firewall, policy, change request, escalate
- approved app, do not bypass

**Avoid, or explain if you say them**

- “Disable the firewall”
- “I’ll open port 3389 to the internet”
- NAT / ASA / Palo Alto rule syntax unless you are quoting L2’s question

## Good to know (not L1 daily work)

- Rules can be by **port**, **application**, **user**, or **URL category**.
- **Host-based** = on the PC. **Network / perimeter** = shared box.
- Security teams review firewall changes because a wrong allow can expose a system.
