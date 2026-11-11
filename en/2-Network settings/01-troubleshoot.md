# Can't connect or slow: check in this order

Most problems turn up if you go through the steps below in order. Each takes a minute or two; stop as soon as things work.

## Can't connect at all

1. **Check the device clock.** If the time is wrong, encrypted connections are refused and no server will work. Turn on automatic time; see 「Keep the device clock accurate」.
2. **Try another network.** Turn off Wi‑Fi and use mobile data, or the other way round. If that works, the problem is that network, not your account.
3. **Update the subscription.** Update the subscription in the app to get the latest server list. Servers we've replaced only show up in your app after an update.
4. **Check the console.** On Overview, see whether your plan has expired or your traffic is used up. On Servers, see whether any of our servers are temporarily offline.
5. **Still stuck? Import again.** Tap import once more on the console's Subscription link page.
6. **Contact support.** In the console's Tickets, tell us the device and app, your carrier, home broadband or mobile data, and when it happened.

> **On home Wi‑Fi, it takes a moment before anything works?** That Wi‑Fi probably has no IPv6. The app switches to the IPv4 backup line within about a minute. To stay on the more stable IPv6 lines, turn IPv6 on in your router; see 「How to turn on IPv6 on your home router」.

## Connected, but slow

1. **Test again.** Run a latency test in the app. With Auto select on, the app retests regularly and moves to a faster server.
2. **Switch connection type.** The TCP or UDP at the end of a server name is the connection type. If one is slow, pick the other type in the same region.
3. **Switch region.** Servers in different regions take different routes, and evening congestion differs.
4. **Switch network.** Home broadband and mobile data leave the country through different exits; one may be fine when the other is slow.
5. **Every server slow, on every network?** It's most likely the carrier's international exit being congested at peak time. It usually clears after the peak. Video apps lower the quality first to keep playing.

Once you pick a server by hand, the app keeps using it and stops switching automatically. When you're done troubleshooting, switch back to Auto select.

## Only one website won't open

If everything else works and one site doesn't, the address lookup (DNS) for that site has most likely gone wrong. See 「Sites won't open: DNS hijacking, poisoning and clearing the cache」.

If it's a streaming or AI service, first check the console's Test results to see whether your server shows "Unlocked" for that service. See 「Streaming and AI apps: choosing a server」.

## Want to know why

Why evenings get slow, how to read latency numbers and what packet loss is: see 「How your connection travels: latency, packet loss and peak hours」.
