# IP addresses and types

## What this means

An **IP address** is a number that identifies a device on a network, like a phone number for the PC. Windows uses it to send and receive data.

**IPv4** is the common form, four numbers, for example `192.168.1.20`. **IPv6** is a newer, longer form. Offices still talk mostly IPv4 on L1 calls.

Useful L1 types:

- **Private IP** — used inside home or office (for example `10.x`, `192.168.x`, `172.16–31.x`). Not unique on the whole internet.
- **Public IP** — the address the internet sees (the office or home router’s outside address).
- **DHCP** — the network **hands** the PC an address automatically.
- **Static** — someone typed the address by hand. Rare on user laptops; more common on printers and servers.

The **default gateway** is usually the router/switch path out of the local network. **DNS** turns names like `outlook.office.com` into IPs. Users mix these up; L1 should not.

**Interview-ready definition:**

> An IP address is the number a device uses on the network. On L1 I would use `ipconfig` or Settings to see if the PC has an address, whether it is on the right network, and whether DHCP gave it one. If the address is missing or is an APIPA like `169.254.x.x`, the PC did not get a real lease — cable, Wi-Fi, or DHCP issue. I would not set random static IPs on a laptop. Printers with a booked static IP I would record on the ticket and escalate if they clash.

## What L1 actually does with this day to day

1. **No network / “unidentified network”**  
   User says: “No internet.”  
   L1: check `ipconfig` / Wi-Fi icon. If `169.254...`, DHCP failed. Cable, Wi-Fi password, VPN, then release/renew if allowed.  
   Done: a real IP, or escalation.

2. **ipconfig / renew**  
   User says: “It was working, then dropped.”  
   L1: reconnect Wi-Fi, `ipconfig /release` and `/renew` per work instruction, reboot the dock.  
   Done: new lease, browsing works.

3. **Ping / name vs number**  
   User says: “The server is down.”  
   L1: if you can ping an IP but not the name, think **DNS**. If neither, think network/VPN/firewall.  
   Done: better diagnosis on the ticket.

4. **Printer IP**  
   User says: “Printer offline.”  
   L1: confirm the printer’s IP on the glass/menu matches the queue. Do not pick a new IP yourself.  
   Done: match or escalate.

5. **Home vs office IP**  
   User says: “VPN connected but apps think I’m at home.”  
   L1: expected for some split-tunnel designs. Capture IP from `ipconfig` for L2.  
   Done: facts, not a random static.

6. **Two devices, same static IP**  
   User says: “Conflict” message.  
   L1: on a laptop, switch back to DHCP. On a printer, escalate — two devices must not share a static.  
   Done: conflict gone or network team engaged.

7. **Explain public vs private to a user who “needs their IP for a vendor”**  
   L1: help find **public** IP via the company’s allowed method if policy says so; do not expose internal IPs if the vendor should not have them.  
   Done: right type of address shared, ticket noted.

**What L1 must not do**

- Do not type a static IP you guessed.
- Do not scan the whole company network for fun.
- Do not change DNS to a public server “to make YouTube faster” against policy.
- Do not promise IPv6 training you do not have — say “we still use IPv4 on most user PCs.”

**When to escalate**

- DHCP scope exhausted (many `169.254` users).
- Duplicate IP on a printer/server.
- Need for a reservation or new subnet.
- Company-wide DNS failure.

## How I would say this in an interview

> An IP address is a device’s network number. L1 checks whether Windows received one from DHCP, whether it is private like `192.168` or an invalid `169.254`, and whether name lookup (DNS) works. I would renew a lease or fix Wi-Fi/cable before blaming the internet. I would not set a homemade static IP on a user’s laptop. Clashes and DHCP outages I would escalate with the `ipconfig` output on the ticket.

## Likely interview questions

**1. What is an IP address?**

A numeric identity for a device on a network so traffic can find it. IPv4 looks like four numbers with dots.

**2. What is DHCP vs static?**

DHCP assigns addresses automatically. Static is typed and stays the same. Laptops almost always use DHCP. Printers often have a reserved or static address.

**3. What does 169.254 mean?**

Windows gave itself a link-local address because DHCP did not answer. The PC is not really on the company network yet. I would check cable, Wi-Fi, and the DHCP service via L2 if many people fail.

**4. Private vs public IP?**

Private is inside the office or home. Public is what the internet sees, usually on the router. A vendor on the internet often needs the public IP, not `192.168.x.x`.

**5. Default gateway in one line?**

The next hop the PC uses to leave its local network, usually the router.

**6. Why is DNS not the same as IP?**

DNS is the phone book: name to number. You can have an IP and still fail if DNS is wrong — websites will not resolve.

**7. Would you set a static DNS of 8.8.8.8?**

Not on a work PC unless the work instruction says so. It can bypass company filtering and break internal names. I would escalate DNS issues.

## Words to use, and words to avoid

**Use**

- IPv4, DHCP, static, private / public, 169.254, ipconfig, DNS, gateway, escalate

**Avoid, or explain if you say them**

- “I’ll NAT it on the core”
- Subnetting math unless asked — then keep it to “the local range the PC should be in”
- Inventing IPv6 rules

## Good to know (not L1 daily work)

- **APIPA** is the name for `169.254.x.x`.
- **Reservation** in DHCP gives the same address without a manual static.
- **IPv6** exists; many L1 tickets still show IPv4. If only IPv6 is present, mention it to L2.
