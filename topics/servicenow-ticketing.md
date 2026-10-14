# ServiceNow / ticketing tools

## What this means

A **ticketing tool** is the system that records every user issue and request. **ServiceNow** is a very common one. Others include Jira Service Management, Freshservice, or a Microsoft tool. The ideas are the same.

A **ticket** (often an **incident** if something is broken, or a **request** if the user wants something new) is the record: who, what, when, priority, notes, and who owns it.

**SLA** (Service Level Agreement) is the promised time to respond or resolve, based on **priority**. A whole-site outage is not treated like a single forgotten password.

L1 lives in the queue: take the ticket, talk to the user, fix or escalate, write notes so the next person is not blind.

**Interview-ready definition:**

> ServiceNow is a ticketing system. It holds incidents and requests so nothing is only in someone’s inbox. On L1 I would work the queue, pick the next ticket by priority and SLA, contact the user, try the standard fix, and write down what I did. If I cannot resolve it, I would assign it to the right team with clear notes, not bounce it empty. I would never close a ticket without saying what happened to the user.

## What L1 actually does with this day to day

1. **Log a ticket from a call / chat / email**  
   User says: “Help, Outlook is down.”  
   L1: capture name, contact, asset/PC, error, business impact, screenshots. Categorise as incident vs request.  
   Done: ticket exists with enough detail.

2. **Prioritise**  
   One user vs whole floor; VIP vs standard — follow **the company’s matrix**, not your mood.  
   Done: P1 not sitting under a P4 printer.

3. **Work the queue**  
   L1: take ownership, set state to In Progress, call the user if needed, keep SLA in mind.  
   Done: no silent tickets.

4. **Update notes**  
   Every action: what you asked, what you saw, what you changed. Another L1 should be able to continue.  
   Done: notes a stranger can read.

5. **Resolve vs close vs escalate**  
   Fix done: confirm with the user, resolve with a cause. Cannot fix: assign to L2 with facts. Do not resolve “user not responding” on a P1 without following abandoned-ticket rules.  
   Done: correct state, correct team.

6. **Requests (access, laptop, software)**  
   These have approvals and catalogues. L1 does not skip the approver.  
   Done: request in the right catalogue item.

7. **Major incident**  
   Many tickets for the same outage. L1: stop duplicating 40 investigations; link to the parent, use the agreed comms.  
   Done: users updated, specialists own the root cause.

**What L1 must not do**

- Do not work only in private chat with no ticket (the work will vanish).
- Do not copy passwords into the ticket.
- Do not escalate with “please fix” and zero notes.
- Do not reopen or close other teams’ tickets to make your numbers look good.

**When to escalate**

- Past your skill or access.
- SLA about to breach and you are stuck.
- Security / data-loss incidents (follow the security path immediately).
- Major incident process.

## How I would say this in an interview

> ServiceNow, or any ticketing tool, is how the Service Desk tracks work. I would log every call, set the right priority, keep notes a colleague can follow, and confirm with the user before I resolve. Incidents are broken things; requests are “please give me.” If I cannot fix it I would escalate with what I already checked, not throw the ticket over the wall. I would never put passwords in the ticket.

## Likely interview questions

**1. Incident vs service request?**

Incident: something that was working is now broken (Outlook down). Request: a new thing (laptop, extra software, access). Wrong type delays the wrong team.

**2. How do you set priority?**

By impact and urgency using the company grid. A CEO unable to print a boarding pass may be urgent for them, but a hospital clinical system down is a true P1. I would follow the documented matrix and ask a lead if unsure.

**3. What is an SLA?**

The clock we agreed with the business for response and fix. L1 watches it, updates the user, and escalates before it breaches rather than after.

**4. User has no ticket and wants a “quick favour.”**

I would still log it. Quick favours become lost work and unfair queues. I can still be fast — the ticket can be short.

**5. How do you escalate well?**

Assign the right assignment group, summarise: symptom, what I checked, what I changed, screenshots, user availability. Ask for the next action. Poor escalations bounce.

**6. User is rude or panicked.**

Stay calm, stick to the process, do not argue. If there is abuse, follow the policy and involve a lead. Still log the facts.

**7. When is a ticket resolved?**

When the user can do the job again, or they agreed a workaround, and notes explain the cause. Not when I am only “waiting for L2” unless the state is correctly pending.

## Words to use, and words to avoid

**Use**

- incident, request, priority, SLA, assignment group, notes, resolve, escalate
- impact, urgency, major incident

**Avoid, or explain if you say them**

- “I’ll just do it off ticket”
- “Not my problem” as the entire update
- CMDB jargon unless asked — then: “the list of our assets and services”

## Good to know (not L1 daily work)

- **ITIL** is the framework behind incident / request / change / problem.
- A **problem** ticket is for the root cause of repeating incidents — usually L2.
- **CMDB** is the asset/service database ServiceNow can link to the ticket.
