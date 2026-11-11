# What happens when a server has a problem

In short: a server problem is our job, and most of the time you don't need to do anything.

## What you'll see
- **The server you're on stops responding.** With Auto select on, the app moves to one that works; you'll usually just feel a brief pause. If you picked a server by hand, the app keeps using it; pick another, or switch back to Auto select.
- **We put in a new server.** Your app gets it when it updates the subscription. To get it right away, update the subscription in the app.
- **No server connects.** First check the console's Servers page for any of ours that are offline, then go through 「Can't connect or slow: check in this order」.
- **Only one network fails.** For example, mobile data works but home Wi‑Fi doesn't: the problem is most likely that network.

## What we do behind the scenes
- **Automatic detection and replacement.** Monitoring connects to every server from outside, the way a user would. If a server stops responding, or its address becomes unreachable from some networks, the system removes it and brings in a new server or a new address.
- **No single point of failure.** The account system, subscription delivery and servers each exist in more than one place, and don't depend on one company or one data centre. A problem in one place usually affects only part of the service; we design to avoid the whole service stopping. If it is ever fully down for more than 4 hours, traffic is added automatically under the compensation rule in 「Account, plans and traffic」.
- **Your plan is yours alone.** Servers check account credentials on every connection and refuse anything unrecognised. When an account has noticeably more devices online at once than one person normally uses, a person reviews it.
- **Encrypted end to end.** Your device and the server agree on keys only they know; anyone on the path sees gibberish and can't alter it.
- **Encrypted backups.** Accounts, plans and usage records are backed up encrypted, stored separately from the system, and restores have been rehearsed.
- **Hardened before going live.** Before carrying its first user, each server has unneeded entry points closed, key-only sign-in, security updates installed and an admin entry not open to the public internet.
- **Hardware keys for admin accounts.** A password alone can't get into the back end; a physical security key is also required.
- **Official software only.** Every file is checked against its fingerprint, components are pinned to reviewed versions, and security fixes are applied quickly.

We don't publish our providers, number of servers, locations or how they connect. That wouldn't help you use the service, but it would help anyone trying to attack or disrupt it.
