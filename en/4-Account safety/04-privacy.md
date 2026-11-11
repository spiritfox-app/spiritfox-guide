# Privacy: what we keep and what we don't

In one line: **where you come from and which sites you visit is never written down by our line servers.** The account system keeps a few things to run your account, each with how long it's kept. The full legal text is in the [Privacy Policy](https://my.spiritfox.app/en/privacy-policy.html).

## Line servers keep no connection logs
Servers log by default: the forwarding program writes each connection as a line (your IP, the site you visit, the time), and the system saves it to disk. Unless you change that on purpose, records pile up day after day and can be leaked, stolen or demanded.

We don't write them in the first place:
- **The forwarding program's output is discarded.** To forward traffic the server must know which site to send your request to, but it uses that only at that moment and never writes it to any log or file.
- **System logs hold no user information.** Only operations records such as admin sign-ins, system updates and service starts and stops. We checked every server: no user IPs or browsing records.
- **Firewalls allow or block, but don't log.**
- **On two-hop lines, the exit server can't see you.** On two-hop lines (such as US West), the exit server only sees the entry server, not your IP.
- **Billing counts bytes only.** Servers report just an account number and bytes uploaded and downloaded.
- **Web content is encrypted.** Almost all sites use HTTPS, so their content passes through our lines encrypted and we can't see it.

These settings took effect on all line servers on 4 November 2026, and we verified each server. System logs written before then were not deleted by hand; they roll off automatically under a 7-day retention period and will all be gone before 11 November.

## What the account system keeps
| Item | Purpose | Kept for |
|---|---|---|
| Email, hashed password | Sign-in | As long as the account exists |
| Traffic used | Plan usage | 90 days |
| Orders (number, amount, time, plan) | Billing and accounting | 3 years |
| Last sign-in, last online and last traffic time; current online device count | Account security; spotting shared accounts | As long as the account exists |
| IP addresses of online devices | Counting devices online at once | About 5 minutes, in memory only |
| Per-IP counters (sign-up, sign-in, subscription updates) | Rate limiting, abuse prevention | 1 hour |
| IP and device identifier when redeeming a code | Preventing code abuse | 14 days |
| Account-system server logs (error records may contain IPs; separate from line servers) | Troubleshooting | 7-day retention, deleted daily on a rolling basis, so at most about 8 days |

**Passwords are stored only as hashes.** A hash is a one-way fingerprint; you can't work back to the password. We add a random value ("salt") per account and use a deliberately slow algorithm, so even a stolen database makes bulk password guessing very hard. We can't see your password either.

## Who else can see what
- **Upstream providers:** can see which address talked to our servers, when, and how much data moved. That's true of every internet connection.
- **Sites you visit:** see the server's address, not your IP; but if you sign in there, they know it's you.
- **Human-verification provider:** the human check on sign-up and sign-in pages (Cloudflare) receives your IP to tell whether you're a bot.

Once we're large enough, we plan to have an independent firm audit these practices and publish the report. That's a plan; it hasn't happened yet.

## A few habits that keep your account safer
1. **Use a separate password for SpiritFox.** Reused passwords leak when other sites leak.
2. **Guard your subscription link**; see 「Your subscription link is your key」.
3. **Turn on automatic updates** for your system and apps, and use a screen lock on your phone and computer.
4. **Review app permissions:** location, contacts, camera, microphone; turn off what isn't needed.
5. **Block third-party cookies in your browser** to cut cross-site tracking.
