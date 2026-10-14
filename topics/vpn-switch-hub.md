# VPN, switch, and hub

## What this means

These are three different networking ideas. Interviewers mix them to see if you know the basics without pretending to be a network engineer.

- A **hub** is an old, simple box that repeats traffic to every port. Offices almost never use hubs now. If you hear “hub,” people often just mean “the network box,” but the real office box is usually a **switch**.
- A **switch** is the box in the cupboard or under a desk that network cables plug into. It sends traffic to the **right** device, not to everyone. Your wall socket usually goes to a switch.
- A **VPN** (Virtual Private Network) is a **secure tunnel** from a laptop (often at home) into the company network, so the PC can use internal email, file shares, or apps as if it were in the office.

L1 helps users **connect to VPN**, checks a cable and link light, and gathers facts when the floor has no network. L1 does not reconfigure core switches or firewall VPN concentrators.

**Interview-ready definition:**

> A switch is what office PCs plug into with a network cable. A hub is an older, dumber version of that idea. A VPN is the encrypted connection a remote user starts so their laptop can reach company systems safely. On L1 I would help install or sign in to the VPN client, check the user account is allowed, and for a desk issue I would check cable, Wi-Fi vs wired, and whether the whole area is down. I would not change switch VLANs or VPN server settings. Those I would escalate with the PC name, IP if they have one, and the VPN error.

## What L1 actually does with this day to day

1. **VPN will not connect**  
   User says: “VPN error at home.”  
   L1: confirm internet works (can they browse), correct VPN app, username, MFA, and that the account is enabled. Try disconnect/reconnect. Capture the error.  
   Done: VPN connected, or ticket to network team.

2. **VPN connected but no file share / slow**  
   User says: “I’m on VPN but the drive failed.”  
   L1: check they really are connected, remap the drive, try web versions of the app if the company has them. Some apps need the office network and a split-tunnelling design L1 cannot change.  
   Done: access works, or escalated as app-via-VPN.

3. **Must use VPN for email vs not**  
   User says: “Do I need VPN for Outlook?”  
   L1: for Microsoft 365, often **no** — mail is on the internet. Internal servers often **yes**. Answer from the company standard, not a guess.  
   Done: user knows when to use VPN.

4. **Desk has no network**  
   User says: “Cable in, no internet.”  
   L1: try another cable, another wall port, check the docking station. See if neighbours work. If the whole row is down, do not spend an hour on one PC.  
   Done: local fix, or network / facilities ticket for the switch.

5. **Wi-Fi vs cable**  
   User says: “Office Wi-Fi is fine, socket is dead.”  
   L1: that points to the port/switch/cable, not their Windows profile. Log the port/room.  
   Done: correctly routed.

6. **Explain hub vs switch if asked**  
   Keep it simple (see questions). Do not start configuring.

7. **VPN after password change**  
   User says: “VPN died after I changed my password.”  
   L1: update saved VPN credentials, reconnect, check MFA.  
   Done: tunnel up.

**What L1 must not do**

- Do not give a user a personal “free VPN” app for work data.
- Do not plug a random home switch/hub into the office network without process (can loop the network).
- Do not change switch config, VLANs, or VPN gateway settings.
- Do not keep a VPN session logged in as you on a user’s PC after the call.

**When to escalate**

- Many VPN users failing (concentrator / internet / cert).
- Whole floor or switch down.
- Need for a new VPN profile or certificate.
- Loop or “network storm” suspicion after someone plugged in a device.

## How I would say this in an interview

> A switch connects office cables; a hub is the old version of that box. A VPN is how a remote laptop gets a secure path into the company. L1 work is mostly the VPN client: credentials, MFA, and reading the error, plus simple cable and “is the whole area down?” checks. I would not configure switches. If internet works but VPN fails, I treat it as VPN. If nothing on the floor works, I escalate to the network team quickly.

## Likely interview questions

**1. What is a VPN, in one sentence?**

A secure tunnel from the user’s device to the company network over the internet.

**2. Hub vs switch?**

A hub repeats traffic to every port. A switch sends traffic mainly to the port that needs it. Offices use switches. I would not buy a hub for a company network.

**3. User at home, VPN fails, websites work.**

Internet is fine, so I focus on the VPN app, account, MFA, certificate, and the exact error. I would not reinstall Windows first.

**4. User in the office, no network, neighbours are down too.**

Possible switch, uplink, or building issue. I would raise it as a wider incident, not a single PC rebuild.

**5. Do I need VPN for Microsoft 365?**

Often not, because Outlook and Teams are on the internet. Internal file servers and some line-of-business apps still need VPN. I would follow the company’s access list.

**6. What is split tunnelling? (simple)**

The VPN can send only company traffic through the tunnel, and let YouTube use the home internet. L1 does not design that. If “only some sites fail,” I mention it when escalating.

**7. Why not allow any USB “network gadget” at a desk?**

An unmanaged switch or hub can disrupt the office network. I would follow the company device policy and escalate.

## Words to use, and words to avoid

**Use**

- VPN client, tunnel, MFA, cable, wall port, switch, escalate to network team
- “hub is the old simple box; we use switches”

**Avoid, or explain if you say them**

- “I’ll add a VLAN on the core”
- “Open IPsec on the firewall”
- Calling every plastic box a hub

## Good to know (not L1 daily work)

- **VLAN** is a logical slice of a switch network (voice vs data). L2/network owns it.
- VPN types you may hear: **SSL VPN** in a client, or **IPsec**. L1 only needs the company client name (GlobalProtect, AnyConnect, FortiClient, etc.).
- A **loop** can happen if two cables connect switches badly; that is an urgent network incident.
