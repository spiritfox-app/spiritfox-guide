# How to turn on IPv6 on your home router

Turning on IPv6 doesn't change the IPv4 address your carrier gives you; leave the WAN page as it is. You only change the router's "IPv6" page, and it takes about five minutes.

## First, relax: only one page changes
- **IPv4 stays the same.** Your carrier's IPv4 address, broadband account and dial-up method stay as they are. You don't need to ask the carrier for a new IP.
- **IPv6 is an extra road alongside.** Once on, the router asks the carrier for a set of IPv6 addresses over the same broadband connection and hands them out to your devices. Both kinds work together, and every site you could open before still opens.

| Settings page | Change it? |
|---|---|
| Wireless (Wi‑Fi name and password) | No |
| WAN / Internet (broadband account, IPv4) | No |
| IPv6 | Only this one |

## Step 0: Test first; you may already have it
Many newer modems and routers ship with IPv6 already on.
1. Disconnect the SpiritFox app on your phone.
2. On your home Wi‑Fi, open `test-ipv6.com` in a browser.
3. If it shows an IPv6 address and **10/10**, you already have it and don't need to change anything. If it shows **No IPv6 address detected** and **0/10**, carry on.

## Step 1: Sign in to the router and find the IPv6 page
1. Find the admin address and password, usually on a label on the back or bottom of the router.
2. On a phone or computer connected to that Wi‑Fi, enter the admin address in a browser and sign in.
3. Look for "IPv6" in the menu, often under "Advanced" or "Network".
4. **Take a screenshot first** so you can put things back exactly as they were.

Nothing takes effect until you click "Save" or "Apply".

## Step 2: Set the connection type to Native
Under "Connection type", choose **Native** (some routers say "Auto").
- **The router does the dial-up** (you entered the broadband account in the router): choose Native.
- **The router sits behind a fibre modem that holds the broadband account:** try Native first. If you still have no IPv6 after saving, change it to **Passthrough** and try again.
- The various tunnel options in the list are for special networks; ignore them.

A few settings below usually fill in automatically. **Leave them at their defaults.** On ASUS, for example:
- Connection interface: PPP (shown when you dial up)
- DHCP-PD: Enable
- Auto configuration setting: Stateless
- Connect to DNS server automatically: Enable
- Router Advertisement: Enable

If there's an "IPv6 firewall", keep it on.

## Step 3: Save
Click "Save" or "Apply" once. The router reconnects briefly; wait 30 seconds to a minute. Some routers need a restart.

To undo: go back to the IPv6 page, set the connection type back to what it was (usually "Disable"), and apply. Everything is as before.

## Step 4: Check
1. Disconnect the SpiritFox app on your phone.
2. On home Wi‑Fi, open `test-ipv6.com`. If it shows an IPv6 address, you're done. Reconnect the app and Auto select will use the IPv6 lines.

**Still no IPv6?**
1. Turn your phone's Wi‑Fi off and on, then test again.
2. Check whether the router got IPv6 from the broadband line: on ASUS, see "System Log → IPv6" and the "WAN IPv6 Address" row; on other brands, the WAN IPv6 address on the status page.
3. If that row is empty, the router is set up correctly but the broadband line isn't providing IPv6 yet. Call your broadband support and say: "I'd like IPv6 turned on for my broadband, with an IPv6 prefix delegated to my router." They can usually do it remotely or book a visit.
4. If your broadband doesn't offer IPv6 yet, leave the router setting as it is; it will start working once IPv6 is turned on. Until then, the app uses the IPv4 backup line automatically.

## Where to find it on common brands
| Router | Where IPv6 is |
|---|---|
| ASUS | Advanced Settings → IPv6 → change Connection type from Disable to Native → Apply |
| Xiaomi | Mi Home app → Network settings → IPv6; or admin page → Common settings → Internet settings → IPv6, choose "Auto" |
| Huawei | AI Life app → Network settings → IPv6; or admin page → More functions → Network settings → IPv6, turn it on |
| TP-Link | Advanced → Network → IPv6 (on some models Internet → IPv6), turn on and choose Auto |
| H3C | More → Interface management → IPv6 settings (some models need Pro mode first) |

Menu names vary a little between models. Look for the item with "IPv6" in its name.

## Common questions
<details><summary>Will this break my home internet?</summary>

No. Only the IPv6 page changes, so IPv4 keeps working. The router reconnects briefly when you save and is back within tens of seconds.

</details>

<details><summary>Does this work on building or estate broadband?</summary>

It varies. Go through the steps; if there's still no IPv6, ask your broadband provider. Until then, the app uses the IPv4 backup line automatically.

</details>
