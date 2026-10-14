# Time management in the organisation (L1)

## What this means

On a Service Desk, **time management** is how you handle many tickets, calls, and SLAs in one shift without dropping users. It is not a Windows setting. Interviewers ask this because L1 is interrupt-driven: the phone rings while you are mid-fix.

It also includes **organisation time**: working hours, time zones, and not booking a “quick restart” in a user’s only meeting. Separately, PCs can show the **wrong clock**, which breaks MFA and Teams — that is a technical cousin of the same word “time.”

This topic is mainly **how you work**: priority, communication, and honesty about what you can finish.

**Interview-ready definition:**

> Time management for L1 means working the queue by priority and SLA, not by whoever shouts loudest, while still being polite. I would take ownership, give a realistic time, update the ticket if I am waiting, and escalate before a clock breaches. I would not start five jobs and finish none. I would also respect the user’s time — agree a restart window — and check the PC clock if sign-in or meetings look “wrong.”

## What L1 actually does with this day to day

1. **Start-of-day queue**  
   Look at P1/P2 and SLA-risk tickets first, then oldest P3/P4, then new chats.  
   Done: nothing urgent is invisible.

2. **One ticket at a time, with notes**  
   If the phone rings, park the current ticket with a written “next step” so you can return.  
   Done: no lost work in your head.

3. **Set expectations**  
   User says: “I need it now.”  
   L1: give a real window (“I will call you in 20 minutes” / “L2 owns this, I will update by 3pm”). Under-promise, then deliver.  
   Done: user is not guessing.

4. **Waiting on the user or L2**  
   Set the ticket to the correct pending state with a reason and a follow-up time.  
   Done: SLA treated fairly, you are not fake-busy.

5. **Protect deep work vs the phone**  
   Follow the team model: some desks take calls, some work backlog. Do not hide from the queue.  
   Done: fair share.

6. **User’s calendar / restart window**  
   User says: “I have back-to-back meetings.”  
   L1: book a patch restart at lunch or end of day. Do not reboot them off a client call.  
   Done: fix scheduled, ticket dated.

7. **Wrong Windows clock / time zone**  
   User says: “Meetings are an hour out” or MFA codes fail.  
   L1: check time zone, “set time automatically,” and that the PC is on the network so time can sync.  
   Done: clock correct; if domain time is wrong for everyone, escalate.

**What L1 must not do**

- Do not ignore SLAs because a friendly user is chatting.
- Do not promise a 5-minute fix you cannot do.
- Do not vanish on a ticket for two days with no update.
- Do not change another region’s time zone “to match you” on a shared PC.

**When to escalate**

- You will breach SLA and are stuck — call a lead early.
- Volume spike / major incident (stop polishing a P4).
- Whole company clock/MFA failures (time server).

## How I would say this in an interview

> I would manage time by priority and SLA: safety and widespread outages first, then the oldest tickets, and I would keep notes so a call interruption does not wipe my progress. I would give users a real time, update them if it slips, and escalate before a breach. I would also plan restarts around their meetings. If one person’s MFA or calendar is wrong I would check the PC clock; if everyone’s is wrong I would raise it as a bigger incident.

## Likely interview questions

**1. You have ten tickets and a ringing phone. What do you do?**

Follow the operating model: answer the phone if you are on phones, park the ticket with a note, then return. If the call is a P1, the P4 wait. I would not let the queue be only whoever is loud.

**2. What is SLA in your own words?**

The promised response and resolve times. I watch the clock, but I still do quality work — a bad close that bounces wastes more time.

**3. A VIP wants you to drop a floor outage to map their printer.**

I would explain the outage is the priority, offer a time for the printer, and ask a lead if the VIP situation is a true exception. I would still log both tickets.

**4. How do you avoid burnout / rushing?**

Checklists for common fixes, good notes, asking for help, and not opening every chat at once. Interviewers like honesty plus a method.

**5. User in another country, meetings at the wrong hour.**

Check Windows time zone vs their location, and whether Outlook calendar is set to the right zone. Do not change a shared mailbox’s zone without asking.

**6. You will miss an SLA in 15 minutes.**

Update the ticket, ping L2 or the lead, keep the user informed. Silence is worse than an honest “we are still on it.”

**7. How do you end a shift?**

Handover notes on anything in progress: next step, user availability, passwords not included. Do not leave a live remote session open.

## Words to use, and words to avoid

**Use**

- priority, SLA, queue, update the user, handover, realistic time, escalate early
- restart window, time zone

**Avoid, or explain if you say them**

- “I just do whoever emails me”
- “I’ll stay on this P4 until I’m happy, even if P1s wait”
- Time-management buzzwords with no ticket example

## Good to know (not L1 daily work)

- **NTP** is how PCs sync the clock from a time server. Company-wide wrong time is a server issue.
- Some desks use **AHT** (average handle time). Fast and wrong is not the goal.
- Shift handover and follow-the-sun teams need written notes more than memory.
