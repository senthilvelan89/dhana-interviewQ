# Windows drivers

## What this means

A **driver** is a small piece of software that lets Windows talk to a piece of hardware: printer, laptop dock, webcam, headset, graphics, Wi-Fi, mouse.

Without the right driver, the device is missing, shows a warning in **Device Manager**, or works badly (no sound, tiny screen, printer error). Windows Update and Intune often install drivers. Sometimes a vendor package is needed (Dell, HP, Lenovo, Logitech).

L1 does simple driver work: identify the device, update or reinstall through Windows, try another USB port, roll back a driver that broke after an update. L1 does not hunt random drivers on unsafe websites.

**Interview-ready definition:**

> A driver is the software Windows needs to use hardware like printers, docks, cameras, and Wi-Fi. On L1 I would check Device Manager, see if the device is unknown or has a warning, and use Windows Update or the company’s approved package to repair it. I would not download drivers from random websites. If a dock or GPU driver needs a vendor tool or a packaged Intune app, I would follow the work instruction or escalate to L2.

## What L1 actually does with this day to day

1. **Webcam / headset not working on Teams**  
   User says: “They cannot see or hear me.”  
   L1: check Teams/Windows privacy settings, correct device selected, then Device Manager for a warning. Try another USB port or a reboot.  
   Done: test call works, or hardware swap.

2. **Yellow warning in Device Manager**  
   User says: “A USB device is unknown.”  
   L1: identify the hardware (dock, dongle). Use “Update driver” from Windows, or the company’s driver app. Note the device name.  
   Done: warning gone, or escalated with the hardware ID.

3. **Printer driver**  
   User says: “Printer added but jobs fail.”  
   L1: remove and re-add via the company method rather than a random driver pack. See also the printers topic.  
   Done: test page prints.

4. **After a Windows update, screen or Wi-Fi broke**  
   User says: “Wi-Fi disappeared after last night’s update.”  
   L1: check Device Manager, try **Roll Back driver** if that button is there and policy allows, or reinstall from the vendor support page **the company uses**.  
   Done: network back, ticket notes the update.

5. **Laptop dock**  
   User says: “Monitors work at home but not on the office dock.”  
   L1: correct USB-C/Thunderbolt port, dock powered, approved dock driver / firmware note from the KB.  
   Done: displays work, or dock/laptop swap.

6. **Audio after docking**  
   User says: “Sound is going to the dock, not my headset.”  
   L1: this is often the **default playback device**, not a missing driver. Switch the output, then check drivers if the device is missing.  
   Done: sound where they expect it.

7. **Device disabled**  
   User says: “Camera vanished.”  
   L1: Device Manager → enable the device if it was disabled. Some companies disable cameras by policy — do not override a security policy.  
   Done: enabled if allowed, otherwise explain policy.

**What L1 must not do**

- Do not download drivers from ads, “driver booster” junk, or unknown blogs.
- Do not disable Driver Signature Enforcement to force a driver.
- Do not install a desktop GPU package on a random laptop “to fix Teams.”
- Do not ignore a possible hardware fault (broken port) by only reinstalling drivers.

**When to escalate**

- Driver needed is not in the catalogue and needs packaging.
- Roll-back is greyed out and the PC cannot stay on the network.
- Many PCs failed after the same update (packaging / Intune issue).
- Firmware for dock/BIOS is required.

## How I would say this in an interview

> Drivers are how Windows talks to hardware. Most L1 tickets are cameras, headsets, docks, Wi-Fi, and printers. I would check Device Manager, privacy settings, the right device in Teams, and then update or reinstall using Windows Update or the company’s approved package. I would not use random driver websites. If an update broke Wi-Fi I would try a rollback if allowed, capture the device name, and escalate to desktop engineering if we need a packaged vendor driver.

## Likely interview questions

**1. What is a driver?**

Software that lets Windows use a hardware device. Each model of printer or dock needs a matching driver. If it is missing, Windows may show an unknown device.

**2. Where do you look first?**

Device Manager, the app’s own device list (Teams camera/mic), and a reboot. Then Windows Update or the company portal. I would also ask: did this start after an update or a new dock?

**3. Why not Google the first driver download?**

Unsafe sites bundle malware. Wrong drivers can blue-screen a PC. Companies keep a tested catalogue. I would use that, or ask L2 for the vendor package.

**4. What is a driver rollback?**

Windows can go back to the previous driver if a new one broke the device. I would use it when the problem started right after an update, then log it so L2 can block that driver if needed.

**5. Headset works in Windows test, not in Teams. Is that a driver?**

Maybe not. It can be Teams using the wrong device or a privacy toggle. I would check those before replacing drivers.

**6. What do you write on the ticket?**

Device (webcam, dock model), Device Manager status, when it broke, what you installed or rolled back, and whether a test worked.

**7. User wants “the latest NVIDIA driver from the internet” on a work laptop.**

I would not. I would explain we only use approved drivers and offer the company package or an escalation. Gaming driver sites are not an L1 fix.

## Words to use, and words to avoid

**Use**

- Device Manager, update / reinstall / roll back driver, approved package, dock, escalate
- unknown device, hardware vs settings

**Avoid, or explain if you say them**

- “Disable driver signing”
- “Download DriverPack from this link”
- INF / hardware ID dumps unless L2 asked for them — then attach, don’t guess

## Good to know (not L1 daily work)

- **PnP** (Plug and Play) is Windows trying to match a driver automatically.
- **WHQL** means Microsoft tested a driver; companies prefer those.
- Docks often need a **firmware** update as well as a Windows driver — usually L2 or vendor tools.
