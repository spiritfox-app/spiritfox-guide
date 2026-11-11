# IPv6 first: why our lines are designed this way

Our main lines run on IPv6, with IPv4 as a backup. If your network has IPv6, you use the main lines; if not, the app switches to the backup on its own. That's why we recommend turning IPv6 on in your home router.

## What IPv4 and IPv6 are
Every device on the internet needs an address to reach others. There are two formats: the older IPv4 and the newer IPv6. Both can exist side by side. Whether your device has IPv6 depends on the network it's on: whether the carrier provides it and whether the router has it turned on.

## Why IPv6 first
1. **IPv4 addresses are more likely to be blocked lately.** Public user reports and our own tests show that overseas servers' IPv4 addresses get blocked from China noticeably more often than their IPv6 addresses. In November 2026 we tested a newly opened server: its IPv4 address connected 0 times out of 30 probes from China, while the same server's IPv6 address connected on all 29 probes.
2. **Blocks usually target single addresses.** When one address is blocked, a new one restores service. IPv6 addresses are plentiful and easy to change, so we recover faster.
3. **So every line's default entry is on IPv6**, and IPv4 is kept as a backup.

Network conditions keep changing. The above reflects what we see and measure now; we'll update this page if that changes.

## What the app does (already set up in your subscription; nothing to change)
- **Auto select uses IPv6 first** and picks the fastest IPv6 server right now.
- **If IPv6 doesn't work, it switches to the IPv4 backup within about a minute.** For example, on Wi‑Fi without IPv6, wait a moment and it works, no manual switching needed.
- **When you're back on a network with IPv6:**
  - Clash Verge Rev and FlClash switch back to IPv6 on their own.
  - sing-box needs you to disconnect and reconnect once to return to IPv6.
- **A server you picked by hand is remembered.** The app keeps using it and won't switch automatically. To go back to automatic, choose Auto select again.

**How to tell which one you're on:** if the current server's name contains "IPv4", you're on the backup line; if not, you're on IPv6.

## About the IPv4 backup line
- It works, but it's more likely to be blocked and may be slower or less stable. It's meant for temporary use.
- The backup line currently uses UDP. Some networks throttle UDP, in which case the backup may not connect either; switch to mobile data.

## How to stay on IPv6
Just turn IPv6 on. **Don't turn IPv4 off.** Both addresses work side by side, and the way you're online now doesn't change.

| Where | What to do |
|---|---|
| Home router | Turn on IPv6 in its admin page; step by step in 「How to turn on IPv6 on your home router」 |
| Fibre modem (ONT) | If the modem does the dial-up, it needs IPv6 too. Its settings usually need the carrier's admin account, so call your broadband support and ask them to turn it on |
| Mobile 4G/5G | Most already have IPv6. On Android, check the Access Point Name (APN) in mobile network settings and set the protocol to IPv4/IPv6 |
| Computer | IPv6 is on by default; don't turn it off |
| Public Wi‑Fi | You can't change it; the backup line or mobile data will do |
