# Entra ID

## What this means

**Entra ID** (formerly **Azure Active Directory** or Azure AD) is Microsoft’s **cloud** identity system. It stores who can sign in to Microsoft 365: Outlook, Teams, Copilot, and many company apps that use “Sign in with Microsoft.”

It is the cloud cousin of **Active Directory** (the on-site Windows directory). Many companies use **both**: the PC still logs into AD, and Microsoft 365 uses Entra ID. Accounts are often **synchronised** (copied) from AD to Entra.

L1 uses Entra (or the M365 admin centre) to check if a cloud user exists, if sign-in is blocked, if **MFA** is registered, and sometimes to reset a cloud password. L1 does not design **Conditional Access** (the rules that say “you must use MFA on a new laptop”).

**Interview-ready definition:**

> Entra ID is Microsoft’s cloud directory for user sign-in to Microsoft 365 and other cloud apps. On L1 I would look up a user, see whether they are allowed to sign in, help with MFA, and reset a password after I verify who they are. If the company still has on-site Active Directory, I would check both if needed, because a disabled AD account can sync and block cloud mail too. I would not write Conditional Access policies. Sign-in log puzzles and tenant-wide changes I would escalate to L2.

## What L1 actually does with this day to day

1. **Cloud sign-in failed**  
   User says: “Microsoft 365 says this account doesn’t exist.”  
   L1: search Entra / M365 for the **UPN** (sign-in email). Check if the account is cloud-only or synced.  
   Done: correct username given, or identity team if missing.

2. **Sign-in blocked / disabled**  
   User says: “Your account is disabled.”  
   L1: confirm they should have access (not a leaver). Do not enable a leaver. If it is a mistake, follow enable process or escalate.  
   Done: enabled with approval, or explained.

3. **MFA registration / lost phone**  
   User says: “New phone, cannot get the code.”  
   L1: identity check, then **Require re-register MFA** if L1 is allowed, and stay with them while they set it up.  
   Done: MFA works on the new device.

4. **Password reset (cloud)**  
   User says: “Forgot Microsoft password.”  
   L1: verify identity, reset via Entra / self-service, set change-at-next-sign-in if policy says so. If the account is **synced from AD**, the reset may need to be done in AD instead.  
   Done: user in; you noted which directory you used.

5. **Guest user / external collaborator**  
   User says: “A supplier cannot open our SharePoint.”  
   L1: check if a **guest** invite exists and is accepted. Do not invite guests unless the request process allows it.  
   Done: guest invited via process, or owner request.

6. **“It works on my phone, not my PC”**  
   User says: Conditional Access style block.  
   L1: read the error (“you must use a compliant device”), check Intune compliance, do not disable CA.  
   Done: device made compliant, or L2 if the policy looks wrong.

7. **Sync delay**  
   User says: “HR created me an hour ago, still no M365.”  
   L1: explain sync can take a little time; check AD first, then Entra. Do not create a duplicate cloud account.  
   Done: wait / sync ticket, no duplicate users.

**What L1 must not do**

- Do not turn off MFA or Conditional Access for the whole company.
- Do not create a cloud account that duplicates a synced user.
- Do not approve guest access into confidential sites without an owner.
- Do not share another user’s sign-in logs in an open ticket copied to the wrong people.

**When to escalate**

- Synced account will not appear in Entra.
- Impossible token / Conditional Access errors after a healthy device.
- Identity protection “risky user” lock that L1 cannot clear.
- Need for admin roles.

## How I would say this in an interview

> Entra ID is the cloud identity behind Microsoft 365. L1 work is looking up the user, checking they can sign in, resetting passwords the right way, and helping with MFA. If the company syncs from Active Directory I would check the on-site account too, so I do not fight a disable that was meant to be there. I would never switch off MFA to save time. Policy and sync engine problems I would pass to L2 with the username, error, and what I already checked.

## Likely interview questions

**1. Entra ID vs Active Directory?**

AD is usually the on-site Windows directory for PCs and file shares. Entra ID is the cloud directory for Microsoft 365. Many firms use both, with sync between them. L1 should know which login they are fixing.

**2. What is MFA?**

Multi-factor authentication: password plus another proof, like a phone app. It stops a stolen password being enough. L1 helps users register or reset it after proving who they are.

**3. User lost their authenticator phone.**

Verify identity, reset MFA methods using the approved admin action, and walk them through setup. I would not email backup codes in an insecure way.

**4. Why might a password reset in M365 not work?**

If the user is **synced from AD**, the password is often mastered on-premises. I would reset in AD (or the company tool that writes to AD), then wait for sync.

**5. What is a guest user?**

Someone outside the company invited into a Team or SharePoint. They sign in with their own email. L1 should not invite guests into sensitive areas without a request.

**6. Sign-in error: device not compliant.**

That is usually Intune + Conditional Access. I would fix compliance (PIN, encryption, updates) rather than asking L2 to exclude the user on day one.

**7. What belongs on the ticket?**

UPN, whether the account is synced or cloud-only, enabled/disabled, MFA status, the exact error, and any admin action. No extra personal data.

## Words to use, and words to avoid

**Use**

- Entra ID, cloud identity, synced from AD, MFA, sign-in allowed, guest, escalate
- Conditional Access (as “extra sign-in rules,” not as something I write)

**Avoid, or explain if you say them**

- “I’ll exclude them from CA”
- “Azure AD B2C custom policy”
- Using only the old name “Azure AD” without also saying Entra — both are OK if you know they are the same product

## Good to know (not L1 daily work)

- Microsoft renamed Azure AD to **Microsoft Entra ID**.
- **Connect / Cloud Sync** is the tool that copies AD users to Entra.
- **SSO** (single sign-on) means one identity opens many apps.
- **Privileged Identity Management** is for admin roles — not L1 daily work.
