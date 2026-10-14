# Printers

## What this means

A **printer** is the device that puts a document on paper. In an office it is usually a **network printer** (shared, with its own name or IP address), not a USB printer on one desk.

Users print from Word, Outlook, or a browser. Windows uses a **print queue** (a waiting list of jobs) and a **driver** (software that knows how to talk to that printer model). The **default printer** is the one Windows picks when they click Print.

L1 spends a lot of time on “it will not print”: wrong printer selected, paused queue, printer offline, no permission, empty toner, or a bad driver. L1 does not usually redesign the print server.

**Interview-ready definition:**

> On the Service Desk, printer work is mostly helping a user get a document to the right device. I would check they are printing to the correct printer, that it is online, that Windows is not paused, and that they have access. I can add a mapped printer, clear a stuck job, and set the default. If the printer has a hardware fault, no IP, or a server-side queue problem, I would gather the printer name, error, and screenshot, then escalate to L2 or facilities.

## What L1 actually does with this day to day

1. **Wrong printer / default printer**  
   User says: “It went to the other floor” or “nothing came out.”  
   L1: open Printers & scanners, confirm the selected printer and default. Help them pick the right one.  
   Done: test page or their document prints.

2. **Printer offline / paused**  
   User says: “It says offline.”  
   L1: check the printer screen, paper, toner, and network lights if they are next to it (or ask them). In Windows, resume the queue if it is paused. Ask them to stay on the office network or VPN if that is required.  
   Done: status is Ready, job prints, or hardware ticket raised.

3. **Stuck print job**  
   User says: “Everyone is waiting; my job is stuck.”  
   L1: cancel the stuck job in the queue (if allowed). Do not cancel other people’s jobs unless policy says so.  
   Done: queue moving again.

4. **Add / map a network printer**  
   User says: “I need the 4th floor printer.”  
   L1: add it via the company method (print portal, `\\printserver\printer`, or Intune). Confirm they are in the right **AD group** if access is restricted.  
   Done: printer listed, test page OK.

5. **Access denied**  
   User says: “I am not allowed to print here.”  
   L1: check group membership / department printer rights. Do not share someone else’s printer credentials. Request access if needed.  
   Done: access granted or request with owner.

6. **Follow-me / secure print**  
   User says: “I printed but it is waiting for my badge.”  
   L1: explain they must tap their ID at the device, and check the print app (for example PaperCut or similar) is installed and they are signed in.  
   Done: job released at the printer.

7. **New PC has no printers**  
   User says: “After a laptop swap I cannot print.”  
   L1: remap printers, set default, test. Often forgotten during onboarding.  
   Done: same printers as before, as far as policy allows.

**What L1 must not do**

- Do not tell them to print someone else’s confidential document “to test.”
- Do not change print-server drivers or IP addresses on the printer unless that is your job.
- Do not keep reprinting a 200-page job into a jammed machine.
- Do not ignore a toner/paper issue by only restarting Windows.

**When to escalate**

- Printer has a hardware error, no power, or bad display.
- Whole floor cannot print (print server / network).
- Driver keeps crashing `spooler` after a normal retry.
- Need a new printer object or IP change.

## How I would say this in an interview

> Printer tickets are very common on L1. I would start with the basics: which printer they chose, whether it is the default, whether Windows shows online or paused, and whether they have permission. I can map a network printer, clear a stuck job, and help with badge release if the company uses secure print. I would not redesign the print server. If the device is in a hardware fault or the whole floor is down, I would log the printer name, location, and error and escalate.

## Likely interview questions

**1. A user says printing does not work. What is your first question?**

What exactly happens — error message, wrong printer, blank pages, or nothing? Which printer name, and did it ever work on this PC? That splits “user settings” from “broken device.”

**2. What is a print queue?**

It is the list of waiting jobs. If one job is stuck, it can block others. L1 can cancel that job if allowed, then ask the user to print again.

**3. What is a default printer?**

The printer Windows uses unless the user picks another. After a Windows update it sometimes jumps to “Microsoft Print to PDF.” I would set the work printer back as default.

**4. How do you add a network printer?**

Using the company’s method: search in Printers & scanners, a print portal, or a server share. I would confirm they are on the network or VPN, then print a test page. If access is group-based I would check the group rather than installing a random IP.

**5. The whole office cannot print. What do you do?**

Treat it as a possible major incident: confirm more than one user, note the printer names and locations, do not spend an hour on one PC. Escalate to L2 / network / print team and keep users updated on the ticket.

**6. Can you print a confidential HR file to test the printer?**

No. I would print a blank test page or a non-sensitive document the user chooses.

**7. USB printer vs network printer?**

USB is plugged into one PC. Network printers are shared. Most offices use network or follow-me printing so L1 maps a shared name, not a local USB.

## Words to use, and words to avoid

**Use**

- queue, default printer, offline / paused, map / add printer, test page, escalate
- toner, paper jam, access group, secure print / badge release

**Avoid, or explain if you say them**

- “I’ll change the printer’s IP on the device”
- “Stop the spooler on the server for everyone”
- PCL/PostScript unless you simply say “the driver type L2 would pick”

## Good to know (not L1 daily work)

- The **Print Spooler** is the Windows service that sends jobs. Restarting it on **one PC** can help; restarting it on the **print server** is L2.
- **Follow-me print** holds the job until the user badges in, which is better for privacy.
- Printers have an **IP address**; if DHCP changes it without a reservation, the queue can go offline.
