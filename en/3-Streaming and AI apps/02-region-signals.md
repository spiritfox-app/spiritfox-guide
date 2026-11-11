# How services work out where you are

Video and AI services don't judge your region only by the server you connect through. Below are nine common signals, and which ones change when you connect to our servers. When the region shown doesn't match your server, use this table to find out why.

Services don't publish everything they do. We only include what has an official statement or a technical standard behind it.

## At a glance
| Signal | Where it comes from | Changes when you connect? |
|---|---|---|
| Network address (IP) | The address you connect from | **Yes:** the service sees the server's address |
| Account history | Sign-up, sign-in and usage records | Only newly recorded addresses; past records don't change |
| Phone number | The number verified at sign-up | No |
| Payment method | Card issuing country, billing address, currency | No |
| App store region | The country or region on your store account | No |
| Device location | GPS, Wi‑Fi, cell towers (needs your permission) | No |
| DNS lookups | The step that turns a name into an address | Depends on settings; see item 7 |
| Browser and device fingerprint | Traits of your browser and device | No |
| Time zone and language | Your system settings | No |

## 1. Network address (IP)
The first and most used signal. IP addresses are allocated through regional registries to carriers and data centres; specialist geolocation companies combine registry data with what networks publish (the RFC 8805 standard) into databases sold to websites.

- **How precise:** one major geolocation company (MaxMind) publicly estimates about 99.8% accuracy at country level, much less at city level (about 66% within 50 km for US addresses). It also says this data can never pinpoint a household.
- **Address type:** some services identify VPN and proxy addresses, Netflix for one.
- Google says location can come from real-time signals like your IP address, and that IP addresses are roughly assigned by geography. Source: `policies.google.com/technologies/location-data`

## 2. Account history
A single connection shows "now"; account history shows "all along": the country at sign-up, each sign-in's time, device and address, and usual times and places.
- **YouTube Premium:** membership should mainly be used in the country where you signed up; misrepresenting your location (for example with a VPN) or trying to get around restrictions may get it cancelled. Source: `support.google.com/youtube/answer/6307365`
- **Netflix:** sharing works by household, meaning the devices connected to the internet where you mainly watch. Source: `help.netflix.com/en/node/123277`

So for services you use a lot, sticking to one region and one device keeps your history consistent.

## 3. Phone number
The country code at the start (+86, +81) shows which country issued the number, and the number type shows whether it's a VoIP number.
- **Claude:** new users must verify a phone number, with no way to skip; numbers must be from supported regions, and VoIP numbers aren't accepted. Source: `support.claude.com/en/articles/8287232`

## 4. Payment method and billing address
The first digits of a card number are assigned to the issuer under an international standard (ISO/IEC 7812), so merchants can tell which country and bank issued it; the billing address is checked against the card's; the charging currency also points to a country. This information passes only between you and the service, never through us.

## 5. App store region
Which apps you can download depends on the region registered on your store account, not on the server you use. Switching servers doesn't change it, and apps already installed keep working.
- **Apple:** before changing country or region you must spend your balance and cancel subscriptions and wait for them to end, and you may need a payment method for the new region. Source: `support.apple.com/en-us/118283`
- **Google Play:** you must be in the new country or region with a local payment method, and after changing once you must wait at least 90 days to change again. Source: `support.google.com/googleplay/answer/7431675`

## 6. Device location
Phones and computers can estimate location themselves, often much more precisely than an IP address. Google says Android estimates location from GPS, sensors, mobile network and Wi‑Fi signals. Nearby Wi‑Fi hotspots each have a fixed hardware ID, so location works indoors too.

Apps need your permission in system settings to read location; websites trigger a browser prompt. If you decline, the app doesn't get your precise location but can still see your IP address, time zone and language.

## 7. DNS lookups
Many large sites return a nearby server's address based on where the query comes from. RFC 7871 says authoritative servers return different answers based on the user's perceived network location, and the resolver asking on your behalf may pass along part of the network the query came from.

Once connected to our lines, lookups for overseas addresses happen abroad through the server, matching the server's region; see 「Sites won't open: DNS hijacking, poisoning and clearing the cache」. If you set DNS by hand in a browser or device, lookups may bypass the line, so page content and DNS lookups reveal two different regions. That shows up as slow loading or the wrong region.

## 8. Browser and device fingerprint
The W3C, which sets web standards, defines fingerprinting as a site's ability to recognise or re-recognise a visitor, browser or device through its configuration and other observable traits. Plenty of people have a 1920×1080 screen, but dozens of traits together may narrow it to your one device.
- **Passive fingerprinting:** looks only at the requests you send, including headers (browser version, system, preferred language) and the IP address.
- **Active fingerprinting:** a page runs scripts to read window size, fonts, drawing details and more.

The W3C says clearing cookies or using a VPN doesn't stop this linking, and fingerprints usually can't be cleared or reset. Source: `w3.org/TR/fingerprinting-guidance/`. Whether services use fingerprints to judge region is generally not published.

## 9. Time zone and language
Readable by any page with no permission: system time zone (in a format like `Asia/Shanghai`), preferred languages, date and currency formats. Google says browser time zone, page language and the like may be used to estimate your country (for ads). Plenty of people abroad use Chinese and Beijing time, so these are usually weighed with other signals.

## Can web video calls reveal your real address?
The browser's real-time audio and video feature (WebRTC, used by video-meeting sites) needs to know network addresses. RFC 8828 says web apps can use it to learn addresses not otherwise exposed to the internet, and in some network setups may also see your local carrier's public address.

All standards are at `www.rfc-editor.org/rfc/rfc` plus the number, e.g. `rfc7871`.
