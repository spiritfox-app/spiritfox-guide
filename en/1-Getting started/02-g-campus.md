# Tips for campus networks

## How campus networks differ

Campus Wi‑Fi is a strange thing. It's free, it's everywhere, and it has opinions. Home broadband just carries your data. Mobile data just carries your data. Campus networks carry your data *and* look at it on the way through.

They usually run their own gateway devices and their own DNS (the service that turns a web address into a server address, the phone book of the internet. A famous physicist once said that if you think you understand quantum mechanics, you don't. DNS is a bit like that, minus the Nobel Prize). And they filter some sites and connections. When an address gets filtered, it doesn't stop working for one dorm. It stops working for the whole campus. One block, thousands of people. Very efficient.

So on campus, if our subscription server's domain gets filtered, importing and updating will fail. If a server gets filtered, it may stop working for everyone on that campus at once. The steps below keep you on the steady side of all that.

One more thing worth knowing: the campus network can't see what you send. It *can* see which server your device connects to and how much data it uses. It's the envelope, not the letter.

## First import: use mobile data

Do your very first import over mobile data. It's like getting into the building before anyone checks the door.

1. **Turn Wi‑Fi off** and use 4G/5G only. "Mobile data on, Wi‑Fi also on" doesn't count. Your phone sees Wi‑Fi and goes running to it every single time, like it's been away for years. Wi‑Fi off. Actually off.
2. Download the app over mobile data; see 「Get set up in three steps」.
3. Sign in to the console, open the Subscription page, and tap Import (or scan the QR code from another device). Do not pass the address through WeChat, QQ or SMS; see 「Your subscription link is your key」.
4. **On a computer too:** turn on your phone's hotspot, connect the computer to it, and import there. Once you're imported and connected, you can go back to the campus network. You're in now. Act natural.

## Build these habits

How steady things are on campus mostly comes down to habits. Not luck. Not which building you're in. Habits. Ten of them, and none involve a gym.

**Importing and updating**
1. **Download the app, import, and update the subscription by hand over mobile data.** The app also updates the subscription on its own now and then, and on campus that update may fail. That's fine. The servers you already have keep working. When you actually need an update, switch to mobile data and do it then.
2. **Connect first, then open other apps and sites.** Anything you open before connecting asks the campus network's DNS for directions. Once you're connected with the app handling all traffic, those lookups go through the encrypted connection, and the campus network stops getting a copy. Order matters. You put on socks, then shoes. Not the other way around.
3. **Open the console and our website only after connecting.** Once connected, those visits are inside the encrypted connection too.

**Connection settings**
4. **Let the app take over all traffic.** sing-box, sing-box MT and FlClash on phones already do this. Leave them alone; they know what they're doing. Clash Verge Rev on a computer only turns on the system proxy by default, so go into its settings, turn on TUN (virtual network adapter) mode, and install the service when it asks the first time. With only the system proxy, any program that ignores it still uses the campus network's DNS. And some programs ignore it. Some programs ignore everything.
5. **Keep 「Auto select」 on.** If a server stops working on campus, the app quietly switches to one that works. No drama. If you pick a server by hand, switch back afterwards.
6. **On campus, prefer servers with "TCP" in the name.** Names look like "Region 01 · TCP" or "· UDP". The ones ending in "IPv4" are backup lines; all the others use IPv6. Lots of campus networks restrict UDP, so UDP servers there tend to fail or crawl. To see whether your campus network has IPv6, open `test-ipv6.com` in a browser. If there's no IPv6, the app switches on its own to the backup lines named "UDP · IPv4". If the campus network also restricts UDP, use mobile data and open a ticket to let us know. We genuinely want to hear about that one.

**Your subscription address**
7. **One account per person. Don't share with classmates.** It sounds generous. It isn't. The more people on one address, the more traffic piles onto one server, the shakier it gets, and now everyone's having a bad time together. That's not sharing. That's a group project.
8. **Never post the address in a group chat, screenshot it, forward it via WeChat or QQ, or open it in a domestic Chinese browser.** See 「Your subscription link is your key」. You wouldn't photocopy your house key and pin it to a noticeboard.
9. **Check the Usage page now and then.** If the numbers are growing and you can't explain why, or you're just not sure whether the address leaked, reset it on the Subscription page and re-import over mobile data. Mystery usage is never a good mystery.
10. **You don't need to turn off your phone's built-in security features or root/flash it.** It doesn't help, and it makes the phone less safe. Leave the phone's security alone. It's on your side.

## When it won't connect on campus

1. **If the campus network needs a sign-in, disconnect the app first.** Lots of campus Wi‑Fi and wired networks make you sign in on a web page first. While the app is connected, that page often just won't load, and you'll stare at a blank screen wondering what you did. You did nothing. Disconnect in the app, sign in to the campus network, then connect again.
2. **Try mobile data.** If that works, the problem is the campus network, not your account. Once you've ruled out the impossible, whatever remains, however annoying, is the Wi‑Fi. Elementary.
3. **Switch servers.** First another TCP server in the same region, then another region. Pivot. *Pivot.*
4. **Update the subscription once over mobile data.** When we replace a server that stopped working, you only get the new one after updating. We can't hand it to you if you don't pick it up.
5. **Still stuck? Open a ticket.** Mention "campus network", wired or Wi‑Fi, whether `test-ipv6.com` shows IPv6, whether mobile data works, and when it happened. You don't need to name your school. This is not a "say my name" situation. We don't need to know. We just want you connected. A beloved children's TV host used to say: when things go wrong, look for the helpers. Hi. We're the helpers.
