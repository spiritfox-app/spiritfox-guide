# Streaming and AI apps: choosing a server

Whichever region's server you connect to is the region video and AI services see. Every day we open these services through each server; the results are on the console's Test results page.

## Three steps
1. **Check Test results, then pick a server.** Find the column for the service you want and choose a server showing "Unlocked".
2. **For services you use a lot, stick to one region.** Many services look at your account's history; keeping one region makes things steadier.
3. **Won't open, or wrong region? Tell us.** In Tickets, say which service and which server. We'll look into it and add it to the daily tests.

## Reading the results
| Shows | Meaning |
|---|---|
| Unlocked | The service opens normally through this server |
| Region not supported | The service says it isn't available in this region |
| Proxy detected | The service spotted a proxy and asks you to turn it off |
| Undetermined | The service showed a human-verification page first; the automatic test can't get past it |
| Originals only | Netflix opens, but only shows titles it holds global rights to |
| Not tested | This test run didn't complete; it doesn't mean the service is blocked |

Services we test now:
- **Video:** YouTube, Netflix, Disney+, Prime Video, TikTok, Spotify.
- **AI:** ChatGPT, Claude, Gemini, Grok, Meta AI, Copilot, Perplexity.

**What the tests do and don't tell you:** we don't sign in to any account; we only open each service's public pages. So "Unlocked" means the service opened through this server at that moment. It doesn't guarantee every title plays after you sign in, or that 4K works; some restrictions only appear after signing in or paying. Services can also change their rules at any time. Every result shows its test time; for how we test, see the last section of 「How your connection travels: latency, packet loss and peak hours」.

## Each service's own rules
A minute spent here saves a lot of trouble.

**Video services**
- **YouTube Premium:** membership should mainly be used in the country where you signed up; misrepresenting your location (for example with a VPN) to get around restrictions may get it cancelled. Source: `support.google.com/youtube/answer/6307365`
- **Netflix:** when it detects a VPN or proxy it asks you to turn it off and try again; live programmes and ad-supported plans aren't available over a VPN. With a VPN you may only see titles Netflix holds global rights to, the "originals only" situation. Sources: `help.netflix.com/en/node/277`, `help.netflix.com/en/node/114701`

**AI apps:** besides the server you connect through, AI apps also look at where you are and at your phone number.
- **ChatGPT:** the supported list includes Japan, Singapore, South Korea, the US and Indonesia, but not China mainland, Hong Kong or Macao. OpenAI says using it from an unsupported region may lead to the account being blocked or suspended. Sources: `help.openai.com/en/articles/7947663`, `help.openai.com/en/articles/9131992`
- **Claude:** the supported regions list doesn't include China mainland or Hong Kong. Source: `anthropic.com/legal/supported-regions`
- **Gemini:** among the web app's available regions, China mainland is Workspace only. Source: `support.google.com/gemini/answer/13575153`

Please follow each service's terms. Their rules change; their official pages are the final word. SpiritFox has no partnership with these services.

## Common questions

<details><summary>Netflix says "You seem to be using a VPN or proxy"?</summary>

Netflix recognised a proxy address. Try a server that shows "Unlocked" in Test results.

</details>

<details><summary>It says Unlocked, so why won't it play, or why does it stutter?</summary>

"Unlocked" only means the page opened at test time, not that every title plays after you sign in. Evening congestion also affects playback; video apps lower the quality first and raise it again once speed recovers. For slow evenings, see 「Can't connect or slow: check in this order」.

</details>

<details><summary>Why does the phone app give a different result from the website?</summary>

Apps and websites give the service different information, such as device location, app store region, system language and time zone. Services combine these to work out where you are; see 「How services work out where you are」.

</details>

<details><summary>Why is a membership shared with family restricted?</summary>

Many services tie membership to the country where it started and check that it's the same household using it. Following the service's household rules is the easiest way.

</details>

<details><summary>My payment card is from a different region than my server. What happens?</summary>

Payment method and billing address are also signals services use for region, and some require them to match the account region at checkout. Check the service's requirements before paying.

</details>
