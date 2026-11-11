# How your connection travels: latency, packet loss and peak hours

This article explains the principles: how data gets abroad, why evenings get slow, and how to read the latency numbers in your app. If you just want to fix a problem, see 「Can't connect or slow: check in this order」.

## The legs of a connection

When you open a video, the data travels out leg by leg and comes back the same way.

| Leg | From → to | At peak time | Who handles it |
|---|---|---|---|
| 1 | Your device → home router or cell tower | Rarely the cause; weak Wi‑Fi makes it worse | You |
| 2 | Home → carrier network → international exit | **The most congested point of the day**: a whole region shares the exit, so queuing and loss are worst here | Your carrier |
| 3 | International exit → our entry server | Servers in different regions take different routes with different congestion | We choose data centres and routes |
| 4 | Entry server → exit server (some lines only) | Both are run and monitored by us | Us |
| 5 | Server → the site you're visiting | Servers are in data centres abroad; this leg is usually smooth | Us |

Legs 1 and 2 are outside our control. What we can do is have the app test every server from your own network, so you avoid the most congested route right now. Legs 3 to 5 are ours: choosing data centres and routes, monitoring every server, and improving or replacing servers that underperform at peak time.

**If every server slows down at once**, the most common cause is congestion on leg 2; if only servers in some regions are slow, it's more likely those routes on leg 3.

### Some lines go through two servers
The entry server is also abroad, placed where it's easier to reach from China, then forwards to the region you want. The extra leg is there to avoid congested stretches; the cost is that latency in the app may read slightly higher.

## Different carriers, different routes

China Telecom, China Unicom and China Mobile each have their own international routes, with different congestion in the evening. The same server can be fast on one carrier and slow on another.

### What "backbone" and "CN2" mean
- **Backbone:** each carrier runs its own international backbone. Any traffic leaving the country goes over some carrier's backbone; the only question is which one.
- **Standard vs premium networks:** carriers usually split their international networks in two. Most home broadband uses the standard network. Premium networks have fewer users and cost more, and are generally regarded as more stable at peak time.

| Carrier | Standard network | Premium network |
|---|---|---|
| China Telecom | ChinaNet, often called "163" (AS4134) | CN2 (AS4809) |
| China Unicom | Standard international network | China Unicom Industrial Internet Backbone, often called "9929" (AS9929) |
| China Mobile | Standard international network | China Mobile International, also called CMIN2 (AS58807) |

Source: the global network directory PeeringDB, `peeringdb.com/asn/4134`, `/4809`, `/9929`, `/58807`.

**Which network you use is decided at both ends.** On your end, by your carrier and broadband plan; on ours, by which networks the server's data centre connects with. So the same server can feel completely different to a China Telecom user and a China Mobile user.

We don't make promises using names like "CN2" or "backbone", because a name doesn't tell you whether your video will stutter at 9 pm at home. We go by peak-time measurements, shown on the console's Test results page. The most accurate test is still your own network at the times you usually use it.

## How to read the latency number in your app

Many people are used to "over 200 ms is slow", but in the apps we recommend, a few hundred milliseconds is normal. **The number isn't a single round trip. It's the whole process from starting the connection to loading a test page and getting a reply.**

Take sing-box 1.14.4 as an example (we've read its source code). Each test is timed like this:
1. Start the clock and connect to the server over an encrypted connection.
2. Through the server, open a test address (by default Google's connectivity check `www.gstatic.com/generate_204`).
3. Set up an HTTPS connection with the test address, which itself takes several round trips.
4. Send a request and stop the clock when the reply arrives.

That's several round trips added together into the one number you see.

**How to use it:**
- **Compare; don't read it as an absolute.** At the same time in the same app, a smaller number means a faster server for you right now.
- **"Timeout" or no number** means the server can't be reached from your network right now; Auto select skips it.
- **Don't compare numbers across apps.** Each app measures slightly differently.
- **For video, go by how it actually plays.** Low latency doesn't mean stable; see the next section.

## Why evenings get slow: queuing and packet loss

The network is shared. From 8 to 11 pm (Beijing time), the most people are online; busy links make data queue up, and when the queue is full some data is dropped and has to be resent. A server that's fast at noon can be slow at 9 pm. So the best server isn't necessarily the nearest one on the map, but the one answering fastest from where you are right now.

Latency only tells you how quickly you connect at this moment. The more common evening problem is **packet loss**: with enough loss, a video buffers no matter how low the latency is. That's why we judge servers by real peak-time performance, not latency alone.

### QoS: how network equipment treats different traffic
QoS (quality of service) means network equipment treats different traffic differently. The internet standard RFC 2475 describes two common methods:
- **Policing:** packets over the allowance are dropped.
- **Shaping:** packets aren't dropped but are delayed, so they queue.

Another standard, RFC 7567, explains that when a device's queue is full, newly arriving packets are dropped ("tail drop"), and that this tends to keep the queue full or nearly full for long periods, adding needless delay.

Most of the slowness you feel at peak time comes down to these two things: **queuing (higher latency) and loss (resending)**.

### TCP and UDP: two connection types
The TCP or UDP at the end of a server name is one of these two connection types.
- **TCP has built-in congestion control.** RFC 5681 specifies that when loss is detected, the sending rate drops to about half; if no reply comes at all (a timeout), it starts again almost from zero. So with a lot of loss, TCP's speed is halved again and again, which is one reason a video can buffer while latency looks fine.
- **UDP doesn't control its own speed.** RFC 8085 states that UDP provides no congestion control; the application using it has to. The network can't count on UDP to back off when congested, which is the technical background to some networks throttling UDP separately at busy times. Much video and the newer web technology QUIC (RFC 9000) run on UDP.

**Which is faster in the evening?** Some people say UDP gets throttled at peak in some regions; others report the opposite. We haven't confirmed either. The practical answer: whichever one is slow, switch to the other.

All standards are at `www.rfc-editor.org/rfc/rfc` plus the number, e.g. `rfc2475`.

## How the Test results are measured

The data on the console's Test results page comes from our scheduled automatic tests. Only signed-in users can see it, and it contains no IP addresses.

- **Network status:** every day our monitoring server connects to each server, opens the test address above, and records whether it connected and how long it took.
- **Evening peak by carrier (public test points):** we have no test servers of our own in China, so every evening at peak we use a public network-testing platform's test points on China Telecom, China Unicom and China Mobile to measure latency and loss to each server, combining the last 7 days. Public test points are unevenly spread; some provinces and carriers have very few, so treat the results as a reference, not as your home experience.
- **Streaming and AI apps:** every day, through each server, we open each service's public pages and check whether it shows the normal page, a "not available in your region" notice, or a "you're using a proxy" notice. Some services show a human-verification page first; we can't judge those, so they're marked "Undetermined".

Your own network is always the most accurate test. Tell us your region, carrier and when you had trouble in Tickets, and we'll add tests for it.
