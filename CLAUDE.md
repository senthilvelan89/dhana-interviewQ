# Interview prep — IT Service Desk L1

This repo is interview preparation for **IT Service Desk L1**.

The learner is **new to IT**. Write so they can understand the topic, then say it out loud in an interview. Do not assume prior IT knowledge.

## Role this content is for

- Job: **IT Service Desk L1** (first-line IT support)
- Level: beginner / career-changer into IT
- Goal: answer "what is this?" and "what would you actually do with it at work?"

L1 is the first person a user talks to when something is broken. Typical work: take the call or ticket, ask the right questions, fix common issues, reset passwords, unlock accounts, check basic network/email/VPN problems, and escalate what they cannot fix.

Do **not** write L2/L3 engineer content as if it were L1 work (server builds, Group Policy design, firewall rule changes, scripting whole systems). A short "good to know" note is fine. Keep the main answer at L1.

## How to generate a topic

When the user names a topic or tool, create **one markdown file** in `topics/` and follow the template below exactly, in this order.

File name: `topics/<kebab-case-topic-name>.md`  
Example: `topics/active-directory.md`

If a file for that topic already exists, update it. Do not invent extra topics unless asked.

## Required sections (use these headings)

```markdown
# [Topic name]

## What this means
## What L1 actually does with this day to day
## How I would say this in an interview
## Likely interview questions
## Words to use, and words to avoid
```

Optional last section, only if it helps a beginner:

```markdown
## Good to know (not L1 daily work)
```

### What each section must contain

**What this means**

- Explain the topic in plain English, as if teaching someone on day one.
- Then give a short spoken definition (4–8 sentences) they can use in an interview.
- If the topic is a tool, say what problem it solves and who uses it.
- Define every technical word the first time it appears. Example: "Active Directory (AD) is Microsoft's system for storing users, computers, and permissions in one place."

**What L1 actually does with this day to day**

- This is the most important section. Interviewers hire L1 for daily work, not theory.
- Write 6–10 concrete tasks an L1 engineer would do with this topic/tool.
- Each task: what the user reports, what L1 does, what "done" looks like.
- Use real Service Desk language: ticket, caller, unlock account, reset password, map a drive, check if the account is disabled, escalate to L2.
- Include what L1 must **not** do (no guessing, no sharing passwords, no changing production servers).
- Mention when to escalate.

**How I would say this in an interview**

- One spoken answer, 45–90 seconds if read aloud.
- Cover: what it is + 3–5 daily L1 tasks + when they would escalate.
- First person is OK ("In an L1 role I would...").
- Keep it natural. No buzzword stuffing.

**Likely interview questions**

- 5–8 questions an L1 interviewer might ask about this topic.
- Give a short model answer under each question (4–8 sentences max).
- Mix: meaning, daily work, a simple scenario, and a safety/process question (password, privacy, ticket notes).

**Words to use, and words to avoid**

- Simple words the learner should say.
- Jargon to avoid, or to replace with a plain phrase.

**Good to know (not L1 daily work)** — optional

- 3–5 bullets of extra context so they are not lost if the interviewer goes deeper.
- Label it clearly as beyond daily L1 work.

## Writing rules

- Simple English. Short sentences. No corporate filler.
- Teach, then give an interview-ready version. Do not only dump theory.
- Always tie the topic back to **helping a user** and **logging the ticket**.
- Prefer examples from a normal office: laptop, email, VPN, printer, password, account lockout, Microsoft 365, Wi-Fi.
- If a process name is used (Incident, Request, Change), explain it in one line.
- Do not write exploit steps, hacking, or how to bypass security. For security topics, stay with L1-safe actions: verify identity, reset via the approved tool, escalate.
- Do not invent company-specific tools unless the user names them. If a tool family is needed, use common L1 names (ServiceNow or similar ticketing tool, Active Directory, Microsoft 365, Teams, Outlook, VPN client) and say "or whatever tool the company uses".
- One topic per file. Keep each file focused.
- After generating, tell the user the file path and that they can list the next topics the same way.

## Workflow with the learner

1. First request: generate **one** topic so they can check the format.
2. Later requests: they will list topics they need for daily L1 work. Generate each one with this same template.
3. If they ask to change the format, update this file first, then regenerate topics to match.

## Sample topic

The first sample is `topics/active-directory.md`. Match its structure, tone, and depth for every later topic.
