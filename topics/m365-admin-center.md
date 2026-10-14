# Microsoft 365 admin centre

## What this means

The **Microsoft 365 admin centre** is the web page where a company looks after its Microsoft cloud services: email (Exchange), Teams, OneDrive, SharePoint, and user licences.

A **licence** is a paid seat that turns features on for a person (for example Exchange email, or an E3 pack). Without a licence, the mailbox or Teams account may be missing.

Think of it as the reception desk for Microsoft 365:

- Users and their email addresses live here (often linked to **Entra ID**, Microsoft’s cloud identity).
- You can see whether someone has a mailbox, a licence, and whether they can sign in.
- Admins can reset cloud passwords, check sign-in problems, and see which apps are included.

L1 does **not** usually get full “Global Admin” rights. Many Service Desks have a limited admin role, or they use a separate portal / ticketing form that does the same checks. Say “if my role has access” in an interview.

**Interview-ready definition:**

> The Microsoft 365 admin centre is the web console for the company’s Microsoft cloud: users, licences, mailboxes, and apps like Outlook and Teams. On L1 I would use it, or a tool that reads the same data, to check whether a user exists, whether they have the right licence, whether the mailbox is there, and why they cannot sign in. I would not change tenant-wide settings or buy licences on my own. If a licence is missing or an admin role is needed, I would log the ticket and escalate.

## What L1 actually does with this day to day

1. **User cannot sign in to Outlook / Teams / Office**  
   User says: “Microsoft 365 keeps asking for a password” or “no licence.”  
   L1: verify identity, search the user in the admin centre, check **sign-in allowed**, licence, and last sign-in if you can see it.  
   Done: simple sign-in/licence fix, or escalated with what you already checked.

2. **Mailbox missing for a new starter**  
   User says: “I have a laptop but no email.”  
   L1: confirm the account exists and has an **Exchange** licence. If there is no licence, raise a request (this is a **service request**, not a break-fix guess).  
   Done: mailbox appears after licence, or ticket with the identity / M365 team.

3. **Licence check**  
   User says: “Word is unlicensed” or “OneDrive will not start.”  
   L1: open the user → Licences, see which products are on. Do not remove someone else’s licence to free a seat unless process says so.  
   Done: correct licence assigned if L1 is allowed, otherwise request logged.

4. **Password / MFA prompt loop**  
   User says: “It keeps sending me to Microsoft login” or “I lost my phone for MFA.”  
   L1: confirm it is a cloud account, reset password via the approved tool, and follow the company’s **MFA** (extra sign-in check) reset process. Never turn MFA off “just to get them in” unless policy allows a controlled exception.  
   Done: user signs in, MFA working or reset ticket done.

5. **Shared mailbox / distribution list access**  
   User says: “I cannot see the team inbox” or “I am not getting group mail.”  
   L1: check whether they are a member of that mailbox or list. Add them only if L1 is allowed.  
   Done: access granted through the proper membership, or owner approval requested.

6. **Which admin centre?**  
   User issue might belong in **Exchange admin** (mail flow), **Teams admin** (meetings), or **Entra** (identity). L1 opens the right place or describes the symptom so L2 can.  
   Done: you did not hunt in the wrong portal for 20 minutes without notes.

7. **Ticket notes from the portal**  
   Record: username / UPN (the sign-in email), licence names, errors, and what you changed. Do not copy other users’ personal data into a ticket the caller should not see.  
   Done: the next engineer can continue without repeating every click.

**What L1 must not do**

- Do not use Global Admin “because it is quicker.”
- Do not delete users, domains, or tenant security settings.
- Do not buy or cancel company subscriptions without the process.
- Do not read another person’s mailbox unless a documented eDiscovery / access process exists.

**When to escalate**

- No licences left in the tenant.
- Mail flow / connector / domain issues.
- Role or Conditional Access changes.
- You can see the user but still cannot explain the sign-in failure.

## How I would say this in an interview

> The Microsoft 365 admin centre is where we manage cloud users, licences, and apps like Outlook and Teams. As L1 I would not run the whole tenant. I would look up a user, check they can sign in, check they have the right licence, and see if a mailbox exists. Typical tickets are new starters with no email, Office saying unlicensed, and MFA or password loops. I would verify the caller first, write clear ticket notes, and escalate licence shortages, mail-flow problems, or any tenant-wide change to L2.

## Likely interview questions

**1. What is the Microsoft 365 admin centre?**

It is the web console for the company’s Microsoft 365 tenant — the cloud workspace. You can see users, licences, and which services they have. L1 uses it for checks and simple user fixes, not to design the whole environment.

**2. A new starter has an account but no email. What do you check?**

I would confirm the account exists, that sign-in is allowed, and that they have an Exchange or Microsoft 365 licence that includes a mailbox. If the licence is missing I would raise a request rather than inventing a mailbox. I would tell the user what is happening and log the username and licence status on the ticket.

**3. What is a licence, and why does L1 care?**

A licence is the product seat that turns on email, Teams, or Office. If it is missing, the app looks broken even though the PC is fine. L1 checks licences before rebuilding a laptop.

**4. Would you turn off MFA for a user who is stuck?**

Not as a shortcut. MFA protects the account. I would follow the company’s MFA reset: verify identity, reset the method, and help them register the new phone. If policy has a break-glass step, only a named team would do that, and I would escalate.

**5. Difference between admin centre and Outlook?**

Outlook is the user’s mail app. The admin centre is the back office. The user never needs the admin centre to read mail. L1 uses the admin centre to see why Outlook has nothing to connect to.

**6. What would you write on the ticket?**

The sign-in name, what the user saw, licence list, whether the mailbox existed, what I changed, and the result. No other users’ mailbox contents.

**7. You do not have admin centre access at this company. What then?**

I would still gather the same facts: exact error, username, device, and whether it is web Outlook or the desktop app. I would use whatever portal or form L1 is given, or escalate with those notes. The skill is the checks, not only the console name.

## Words to use, and words to avoid

**Use**

- tenant, user, licence, mailbox, sign-in, MFA, escalate
- “I would check in the admin centre if my role has access”

**Avoid, or explain if you say them**

- “I’m a Global Admin” — that is not a normal L1 claim
- “I’ll delete the tenant / domain”
- PowerShell tenant scripts unless you can say “L2 would run that”

## Good to know (not L1 daily work)

- **Entra ID** is the identity behind M365 sign-in. Admin centre and Entra admin centre overlap.
- **Conditional Access** is extra sign-in rules (for example “must use MFA on a new device”). L1 does not write those policies.
- Separate portals exist: Exchange, Teams, Intune, SharePoint. Pick the one that matches the symptom.
- A **UPN** is usually the sign-in address, like `jane@company.com`.
