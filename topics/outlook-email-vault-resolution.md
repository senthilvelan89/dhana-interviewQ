# Outlook — email vault and fault resolution

## What this means

**Outlook** is the email and calendar app most offices use, usually with **Microsoft 365** (Exchange Online). Users send mail, join meetings, and search old messages.

**Fault resolution** means fixing everyday email problems: cannot send or receive, stuck in Outbox, Outlook will not open, missing calendar, or “need password” loops.

**Email vault** (also called archive or Enterprise Vault in some companies) is extra storage for old mail. Mail moves from the live mailbox into an **Online Archive** or a vault add-in so the mailbox does not hit its size limit. Users often say “my old emails vanished” when they were **archived**, not deleted.

L1 fixes client and simple mailbox issues. L1 does not redesign mail flow or Exchange servers.

**Interview-ready definition:**

> Outlook is the user’s email app. On L1 I would treat most tickets as: can they sign in, can they send and receive, is the mailbox full, and are old items in the archive or vault rather than deleted. I would try web Outlook to see if the problem is the PC app or the mailbox itself, then repair the profile, clear a stuck Outbox, or show them the Online Archive. I would never read other people’s mail. Server-side mail flow I would escalate with headers or error text.

## What L1 actually does with this day to day

1. **Cannot open Outlook / keeps asking for password**  
   User says: “Outlook password loop.”  
   L1: confirm M365 account, licence, MFA. Try **Outlook on the web**. If web works, the mailbox is fine — repair the desktop app or Windows credentials.  
   Done: desktop or web access working, cause noted.

2. **Cannot send / stuck in Outbox**  
   User says: “They never got my mail.”  
   L1: check Outbox, attachment size, whether they are offline. Send a test to themselves. If web send works, repair the local profile.  
   Done: mail leaves, or error copied for L2.

3. **Mailbox full**  
   User says: “Cannot send, mailbox over quota.”  
   L1: show Deleted Items / Junk, empty Recoverable Items if allowed, explain archive. Do not delete their mail without consent.  
   Done: under quota, or archive / retention request.

4. **“My old emails are gone” (vault / archive)**  
   User says: “Last year’s mail disappeared.”  
   L1: look for **Online Archive** in the folder list, or the company vault add-in. Search there. Explain items may be in archive after a policy runs.  
   Done: user can open archived mail, or vault access escalated.

5. **Need a deleted email back**  
   User says: “I deleted an important mail.”  
   L1: Recover Deleted Items in Outlook / web, within the retention window. If not there, raise it to the mail / compliance team — L1 does not search another mailbox.  
   Done: item restored, or formal recovery request.

6. **Calendar / meeting missing**  
   User says: “The invite is not in my calendar.”  
   L1: check Deleted / Junk, calendar overlay, whether they are looking at a shared calendar. Test in web.  
   Done: meeting visible, or mailbox issue escalated.

7. **Shared mailbox**  
   User says: “I cannot see the team inbox.”  
   L1: confirm membership in M365 admin / Entra if allowed; Outlook restart; add shared mailbox.  
   Done: folder appears, or access requested.

**What L1 must not do**

- Do not open someone else’s mailbox because a manager asked on the phone without a process.
- Do not export a whole mailbox to USB “as backup” against policy.
- Do not disable vault / retention policies for convenience.
- Do not guess mail-flow connector fixes.

**When to escalate**

- Web and desktop both fail to send (Exchange / connector).
- Archive not provisioned and quota is blocking work.
- Legal hold / eDiscovery restore.
- Outlook crashes on many PCs after an update.

## How I would say this in an interview

> Most Outlook tickets are sign-in, send/receive, a full mailbox, or mail that looks missing. My first split is: does Outlook on the web work? If web works, I repair the desktop app. If old mail is missing I check the Online Archive or the company’s vault, because archive policies move mail rather than delete it. I would help recover deleted items within the allowed window, keep notes on the ticket, and escalate real mail-flow or compliance restores to L2.

## Likely interview questions

**1. Web Outlook works, desktop does not. What does that tell you?**

The mailbox in the cloud is probably healthy. The problem is the PC: profile, cached mode, credentials, or a bad add-in. I would repair or recreate the Outlook profile rather than blaming Exchange first.

**2. What is an email vault or archive?**

A store for older mail so the live mailbox stays smaller. In Microsoft 365 it is often the Online Archive. Some companies use a vault product. Users should look in that folder before we say mail is lost.

**3. Mailbox is full. What do you do?**

Explain the limit, help them empty Deleted Items, show archive, and not delete blindly. If they need more space, that is a request for a larger archive or a quota change, with approval.

**4. A director wants you to read an absent colleague’s inbox.**

I would follow the access process: ticket, approver, and a shared mailbox or conversion — not the colleague’s password. Password sharing is not acceptable.

**5. What is cached mode vs online mode? (simple)**

Cached mode keeps a local copy (OST file) for speed. It can be out of date or corrupt. Web Outlook or online mode helps you see the real mailbox.

**6. How do you recover a deleted email?**

Recover Deleted Items from Outlook or the web, if it is still in the retention period. After that, L2 / compliance. I would note the time and subject on the ticket.

**7. User says vault search is slow or missing.**

I would confirm they are signed into the vault add-in, try web archive, and escalate if the archive mailbox was never created.

## Words to use, and words to avoid

**Use**

- Outlook on the web, Outbox, mailbox quota, Online Archive / vault, Recover Deleted Items
- profile repair, shared mailbox, escalate mail flow

**Avoid, or explain if you say them**

- “I’ll turn off your legal hold”
- “Give me your password and I’ll log in as you”
- NDR / MX / connector detail unless you are quoting an error for L2

## Good to know (not L1 daily work)

- **OST** is the offline Outlook cache; rebuilding a profile rebuilds it.
- **Retention / litigation hold** can stop real deletion — that is compliance, not L1 cleanup.
- Veritas **Enterprise Vault** is a common older “vault” brand; Microsoft 365 often replaces it with Online Archive.
- A **Non-Delivery Report (NDR)** is the bounce message; attach it when escalating send failures.
