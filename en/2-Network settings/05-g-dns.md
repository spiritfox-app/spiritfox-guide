# Sites won't open: DNS hijacking, poisoning and clearing the cache

If just one site won't open, or the console or subscription updates fail on a particular Wi‑Fi, the address lookup (DNS) has most likely gone wrong. Start with "Do this first"; read on if you want to know why.

## Do this first
1. **Try mobile data.** If it works, the problem is that Wi‑Fi or router.
2. **Clear the wrong addresses your device remembered.**
   - iPhone, Android: turn on Airplane Mode, wait 5 seconds, turn it off.
   - Windows: open Command Prompt and run `ipconfig /flushdns`.
   - Mac: open Terminal and run `sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder`.
   - Chrome, Edge: go to `chrome://net-internals/#dns` and click **Clear host cache**.
3. **Check for settings that bypass the app.**
   - Only one browser fails: turn off its "secure DNS" and try again. Chrome: Settings › Privacy and security › Security › Use secure DNS. Firefox: Settings › Privacy & Security › DNS over HTTPS.
   - iPhone with iCloud Private Relay on: turn it off for this network under Settings › Wi‑Fi › ⓘ next to the network.
   - A DNS server typed in by hand on the device or router: if you don't know why it's there, remove it and set it back to automatic.
4. **Restart the app** and try again.

Step 3 is only for troubleshooting. Once you've found the cause, turn the "secure DNS" or iCloud Private Relay you switched off back on; they protect your privacy.
5. If the browser shows a certificate error or "Your connection is not private", **close the page at once and don't enter any password**.

## What DNS does
Before your device opens a web address, it asks a DNS server: "What address does this name point to?" Only then does it connect, like calling directory enquiries before a phone call. Normally your home router and your broadband carrier behind it answer.

These questions and answers are mostly **unencrypted**. The internet standard RFC 9076 notes that almost all DNS traffic is unencrypted, and a single query reveals both who is asking and what they're asking about. So with ordinary DNS, the network you're on can see which addresses you look up.

## Hijacking and poisoning: two ways to get a wrong answer

| | DNS hijacking | DNS poisoning |
|---|---|---|
| Who gives the wrong answer | The DNS server you're using, or settings that were changed | Something along the path answers before the real reply |
| How widespread | Often many sites on that network | Usually a few specific addresses |
| On another network | Mobile data usually fixes it | Not necessarily |

### Three common kinds of hijacking
1. **The resolver changes the answer.** A report (SAC 032) from the security committee of ICANN, which oversees global domain names, calls this "DNS response modification" and names carriers that resolve names for their users among those doing it. What you see: you type an address and land on an ad page, a portal or somewhere you didn't mean to go.
2. **The router's or device's DNS settings were changed.** A router with its default password, remote management left on, or unknown software or profiles installed can have its DNS pointed at someone else's server. What you see: lots of sites misbehave on that Wi‑Fi but work on mobile data.
3. **Public Wi‑Fi.** Hotel, café and library Wi‑Fi usually forces its own DNS, which you can't control.

### How poisoning happens
Ordinary DNS queries are unencrypted, so anything along the path can see them and answer first, and your device accepts the first reply. Some networks send forged replies for certain addresses; the forgery often arrives first and points nowhere useful. What you see: one site fails with "connection reset" or "took too long to respond"; it works for a few minutes, then stops again.

### Why wrong answers stick around
Devices, browsers and routers keep answers for a while to save time, forged ones included. So even after you connect, the wrong address can keep being used until the cache is cleared. That's why step 2 clears it.

## Once you're connected to our lines
- **Lookups that go through the app are encrypted** (exceptions in the last item of this section). Your subscription sets up encrypted DNS, so equipment along the path can't see the addresses you look up or slip in fake answers. It can still see that you're connecting to an encrypted DNS service, but not what's inside.
- **sing-box** takes over all traffic on the device, including all DNS queries. Lookups for overseas addresses go through our lines and are answered abroad; lookups for China addresses use a domestic encrypted DNS directly, without a detour.
- **Clash Verge Rev, FlClash:** lookups are encrypted too. For sites that go through our lines, the name is resolved at the far end, not on your device.
- **Exceptions:** with Clash Verge Rev on a computer and TUN (virtual network adapter) mode off, programs that don't use the system proxy use the computer's own DNS and can still be poisoned. If a particular app fails, turn on TUN mode. DNS you've set by hand and browsers' "secure DNS" can also bypass the subscription's settings.

So hijacking and poisoning mainly affect the steps **before you connect**: opening the website, signing in to the console and updating the subscription.

## If the console or subscription update won't open
1. Keep using lines that already work. Imported lines connect to server addresses, so the website failing usually doesn't affect them.
2. Connect in the app first, then update the subscription.
3. Still failing? Update on mobile data, or sign in to the console on mobile data and import again.
4. Only take your subscription link from the console. **Never import from a link or QR code someone sent you**; see 「Your subscription link is your key」.

## If you suspect the router was tampered with
1. Sign in to the router's admin page and look at the "DNS" field. Normally it says "automatic". If it has addresses you don't recognise, set it back to automatic, save and restart the router.
2. If you're not sure what was changed, reset the router to factory settings, re-enter your broadband account, set up Wi‑Fi again and choose a new admin password.
3. Compare on a computer: run `nslookup spiritfox.app` once on the Wi‑Fi and once on a phone hotspot. If the addresses differ greatly, one side's answer is wrong.

## Everyday prevention
- Change the router's default admin password, turn off remote management, and install firmware updates.
- Keep DNS on the router and devices set to automatic.
- Don't install software, certificates or profiles from unknown sources.
- Leave Android's "Private DNS" at its default.
- On public Wi‑Fi, sign in, pay and update subscriptions over mobile data where you can.
- Never click "Proceed anyway" on a certificate warning.

## Going further: validated DNS and encrypted DNS
- **DNSSEC (validated DNS):** RFC 4033 says it provides origin authentication and integrity for DNS data, but not confidentiality. It can catch altered answers, but others can still see what you looked up.
- **Encrypted DNS (DoH and similar):** RFC 8484 says one of its main uses is preventing on-path devices from interfering with DNS, mitigating passive surveillance and attacks that divert DNS traffic to malicious servers. That's the kind our subscription uses.

Both depend on what your device and network support. For most people, the everyday prevention above is enough.

Standards: `www.rfc-editor.org/rfc/rfc9076`, `rfc4033`, `rfc8484`; the ICANN SAC 032 report is in the Security and Stability Advisory Committee (SSAC) reports list at `icann.org`.
