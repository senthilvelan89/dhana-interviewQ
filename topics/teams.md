# Microsoft Teams

## What this means

**Microsoft Teams** is the company’s chat, meetings, and (often) phone app. People send messages, join video calls, share screens, and open files from SharePoint without leaving Teams.

It signs in with the same **Microsoft 365** account as Outlook. Meetings in the Outlook calendar usually open in Teams.

L1 tickets are mostly: cannot sign in, no audio or video, cannot join a meeting, Teams is a blank window, or chat is missing. L1 does not design Teams policies or call queues.

**Interview-ready definition:**

> Teams is Microsoft’s chat and meeting app. On L1 I would help with sign-in, audio and camera, joining meetings, and a stuck or blank app. I would check the Microsoft 365 account and licence, try Teams on the web to see if the account is healthy, and then clear the Teams cache or reinstall if the desktop app is the problem. I would not change tenant-wide meeting policies. If the whole company cannot join meetings, I would escalate quickly as a possible service issue.

## What L1 actually does with this day to day

1. **Cannot sign in**  
   User says: “Teams is stuck on login.”  
   L1: confirm account, licence (Teams is part of most M365 packs), MFA, date/time on the PC. Try [teams.microsoft.com](https://teams.microsoft.com).  
   Done: signed in, or licence/account escalated.

2. **No microphone / camera / sound**  
   User says: “They cannot hear me.”  
   L1: check Teams device settings, Windows sound output, privacy toggles, and whether a headset is selected. See also drivers.  
   Done: test call works.

3. **Cannot join a meeting**  
   User says: “Waiting in lobby” or “meeting link fails.”  
   L1: confirm they used the right link, are signed into the work account (not a personal Microsoft account), and try the browser. Lobby usually means the host must admit them.  
   Done: in the meeting, or host/policy issue noted.

4. **Blank Teams / app frozen**  
   User says: “White screen, always loading.”  
   L1: fully quit Teams, clear the **cache** using the company work instruction, restart, or reinstall from Company Portal.  
   Done: app loads, chat visible.

5. **Screen share / permissions**  
   User says: “Share is greyed out.”  
   L1: check they are in the meeting as a presenter if required, Windows graphics, and browser permissions for web Teams.  
   Done: share works, or policy escalation.

6. **Missing chat / team**  
   User says: “I left a Team by accident” or “I cannot see the project.”  
   L1: they may need an owner to re-add them. L1 does not add people to random Teams without a request.  
   Done: access requested from owner, or restored if L1 is allowed.

7. **Teams Phone / dial pad**  
   User says: “I cannot make a phone call in Teams.”  
   L1: check if they have a **Phone System / calling** licence and a number assigned. If not, it is a request, not a broken headset.  
   Done: calling works, or licence/number request.

**What L1 must not do**

- Do not post in someone else’s private chat to “test.”
- Do not make a user an owner of a company-wide Team without process.
- Do not tell them to use a personal Gmail Teams account for work meetings.
- Do not record a meeting secretly as a test.

**When to escalate**

- Many users cannot join (service or network).
- Calling, auto attendants, or Direct Routing.
- Guest access / external meeting policy.
- Cache clear does not fix a crash after an update.

## How I would say this in an interview

> Teams is where staff chat and meet. L1 work is sign-in, audio and camera, joining meetings, and repairing a stuck desktop app. I always compare with Teams on the web: if web works, I fix the PC app. If web fails too, I check the account and licence. I would not change meeting policies. A company-wide outage I would escalate as a priority and keep users updated on the ticket.

## Likely interview questions

**1. Why try Teams on the web first?**

It splits “account/service problem” from “broken desktop app.” Same idea as Outlook on the web.

**2. User is stuck in the lobby.**

They may be signed in with the wrong account, or the host has not admitted them, or guests are not allowed. I would check which account they used and contact the organiser if needed.

**3. How do you clear the Teams cache? (interview level)**

I would follow the company’s instruction: fully exit Teams, delete the cache folders it names, then restart. I would not delete their whole profile documents. If I am unsure, I use the KB article rather than guessing folders.

**4. Camera works in Camera app, not in Teams.**

Then it is likely Teams settings or privacy for that app, not a dead webcam. I would pick the correct device in Teams and check Windows camera permission.

**5. Someone wants to be added to a confidential Team.**

I would ask the Team owner to add them via a ticket, not add them myself because they sounded important.

**6. What is a Teams licence vs a calling licence?**

Chat and meetings are on a normal M365 licence. Dialling real phone numbers usually needs an extra calling add-on and a phone number. L1 checks that before replacing a headset.

**7. Whole office: “Teams is down.”**

Check Microsoft 365 service health if L1 can see it, confirm more than one user, treat as a possible major incident, escalate, and stop changing random PCs.

## Words to use, and words to avoid

**Use**

- sign-in, Teams on the web, cache, lobby, host / organiser, licence, escalate
- microphone, camera, privacy settings

**Avoid, or explain if you say them**

- “I’ll set up Direct Routing”
- “I’ll change the org-wide meeting policy”
- “Use your personal Teams, it’s easier”

## Good to know (not L1 daily work)

- Teams files live in **SharePoint / OneDrive**.
- **New Teams** vs classic Teams can both appear during a company upgrade.
- **Guest access** lets people outside the company join; that is a policy L2 owns.
