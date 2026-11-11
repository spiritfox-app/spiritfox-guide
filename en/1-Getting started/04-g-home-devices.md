# Tips for home networks

Think about how many things are involved when you just want to look something up. Your home router. The fibre modem your ISP installed. The security apps on your phone. It's a whole committee, and every one of them sits on the path between you and the internet. This article covers what they can and can't see, and how to use the service with peace of mind.

## A few things to know

- **The fibre modem belongs to your ISP.** It lives in your home, it uses your electricity, but it's theirs. The ISP can manage it remotely and adjust its settings. That's standard industry practice. It's basically a houseguest that never leaves and also never pays rent.
- **Many routers have online security features** such as malicious-site blocking, browsing protection or parental controls. These compare the addresses you visit against a list. What data they send, and where, is usually not published.
- **Your phone's system and security apps** can see which apps are installed, what's on your clipboard, and the addresses you open in a browser. They work *before* anything gets encrypted, so no connection covers that part. You can't lock a door the phone is already standing behind.

We don't guess what any particular device does. We take the cautious approach instead: **assume anything they can see may be recorded.**

## What they can and cannot see

| Situation | Can see | Cannot see |
|---|---|---|
| App not connected | Every domain you visit (from DNS lookups and the domain in each address) | Page contents (most sites are encrypted) |
| App connected and taking over all traffic | Which server your device connects to, and how much data it uses | Which sites you visit or what's in them |

So the whole table comes down to one sentence: **let the app take over all traffic, and go online after connecting where you can.** That's it. That's the article. The rest is details.

## What to do

1. **Let the app take over all traffic.** sing-box, sing-box MT and FlClash on phones already do this. In Clash Verge Rev on a computer, turn on TUN (virtual network adapter) mode in settings, and install the service when it asks the first time.
2. **Connect first, then open other apps, sites and the console.** Anything opened before you connect uses your router's and ISP's DNS. Also, a browser's built-in "secure DNS" goes around the app's DNS settings and does its own thing. If a particular site won't open after connecting, try turning it off temporarily; see 「Sites won't open: DNS hijacking, poisoning and clearing the cache」.
3. **Keep your subscription address between the console and the app.** Tap Import in the console or scan the QR code in the app. Never pass it through WeChat, QQ or SMS, and don't open it in a domestic Chinese browser. Your phone's system can see browser and clipboard contents. The address should travel like a VIP: straight from the console to the app, no stops.
4. **One account per person. Don't share.** Every extra pair of hands your subscription address passes through is another chance for it to leak. Nobody's ever said "I'm so glad more people had my key."
5. **If you're unsure whether it leaked, reset your subscription address** and re-import; see 「Your subscription link is your key」. When in doubt, reset. It takes a minute.

## What you don't need to do

- **No need to replace your modem or router, or flash new firmware.** Once you're connected, they only see an encrypted connection. A shiny new box sees the exact same thing. It's not safer, it's just newer.
- **No need to turn off your phone's built-in security or uninstall security apps.** Turning them off doesn't help, and it makes the phone easier to infect or scam. Keep them on.
- **Don't trust claims that some setting makes you "completely invisible".** Network devices can always see which server you connect to and how much data you use. "Trust no one" is a bit much for a home network, but definitely don't trust that. Nobody is completely invisible on a network. What we guarantee is that the content is encrypted and they can't see what you visit.
