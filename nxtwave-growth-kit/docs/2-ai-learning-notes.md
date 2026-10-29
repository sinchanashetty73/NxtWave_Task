# AI + Learning Notes

> ⚠️ **Edit before submitting.** These notes are drafted from how this kit was actually built with Claude. NxtWave is evaluating *your* judgment, so go through each entry, change anything that isn't true for you, and add your own real moments (even 1–2 of your own will make it stronger). Do not submit as-is.

## Examples: Asked → AI suggested → What I changed

### 1. The channel mix
- **Asked:** "Plan a campaign to get 500 final-year engineering students to register for a free workshop with ₹2,000 and 7 days."
- **AI suggested:** A broad mix including Google/Meta ads, influencer shout-outs, college fest tie-ups, Telegram, Reddit, YouTube Shorts and email.
- **What I changed:** Cut it to 4 channels. With ₹2,000, paid ads would give maybe 40–60 registrations, while peer distribution (ambassadors, club emails, referrals) is nearly free and trusted. I put about three quarters of the expected registrations on peer channels and kept paid to a ₹1,000 boost as a test.

### 2. The landing page
- **Asked:** "Build a landing page for the workshop."
- **AI suggested:** A standard hero + form + FAQ page.
- **What I changed:** The challenge said everyone will build a landing page, so I pushed for a referral engine on top: personal links, reward tiers, share card, branch-specific project picker, and a dashboard that tells me if I'll hit 500.

### 3. The numbers
- **Asked:** "Show how the 500 registrations could come in."
- **AI suggested:** Round-number targets per channel.
- **What I changed:** Rebuilt each estimate bottom-up (members × views × conversion), and added a dashboard that projects the finish from actual pace, so the plan can self-correct on Day 3.

## What AI suggested that I deliberately rejected, and why

1. **Fake urgency and fake social proof** ("only 12 seats left!", pre-filled "registered" counts). Rejected: the workshop is online with no seat limit, and fake scarcity damages trust with students. The seat meter on the page shows only real registrations; the demo data lives in the admin page and is labelled as demo.
2. **Buying a mass WhatsApp broadcast / scraped student numbers.** Rejected: spammy, may violate WhatsApp policy and privacy norms, and cold messages convert poorly compared to messages from a classmate.
3. **Spending most of the budget on Instagram/Google ads.** Rejected: students ignore ads; ₹2,000 would buy too few clicks to matter.
4. **A complex backend (login, database, payments).** Rejected for the 48-hour window: the form posts to a Google Sheet through a small script, which is enough to run the campaign and ship on time.
5. **Gamified "random lucky draw" prizes.** Rejected: it attracts people who only want the prize. Rewards are instead tied to the workshop (Starter Kit, Interview Cheat-Sheet, priority Q&A).

## What changed between first idea and final solution
- **First idea:** a nice-looking landing page plus a long list of channels.
- **Final:** a smaller plan with one working growth loop (register → get link → friends register → unlock rewards) and a dashboard to steer the campaign daily.

## If I had another 24 hours
1. Connect the form to a real Google Sheet and test end to end with real people.
2. Add a WhatsApp reminder flow (n8n or WhatsApp Business API) for T-24h, T-1h and "live now".
3. Add a post-workshop project submission page with an AI-based first-pass evaluation against a rubric.
4. A/B test two headlines on the page.
5. Record ambassador onboarding as a 2-minute video.
