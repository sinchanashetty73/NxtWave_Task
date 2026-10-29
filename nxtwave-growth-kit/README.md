# NxtWave Growth Challenge: Submission Kit

```
landing/index.html   Landing page + referral engine (open in browser)
landing/admin.html   Campaign control-room dashboard
social/poster-studio.html   Poster + caption generator (Instagram, Story, LinkedIn)
docs/                Growth plan, AI notes, video script, message kit, social content pack
```

## Social links
Edit `CONFIG.SOCIAL` at the top of the script in `landing/index.html` with your real Instagram, YouTube, LinkedIn, WhatsApp and Telegram links (they currently point to each platform's home page).

## Run it
Open `landing/index.html` by double-clicking it. To see the dashboard fully populated, open `landing/admin.html` and click **Load demo data**.

## Put it live (free)
1. Create a GitHub repo, upload the `landing` folder.
2. Settings → Pages → deploy from the main branch.
3. You get a public link to submit. Share `.../index.html` as the live page and `.../admin.html` as the dashboard.

## Log registrations to a real Google Sheet (5 min)
1. Create a Google Sheet. Row 1 headers: `name, phone, email, college, branch, year, code, ref, source, ts`.
2. Extensions → Apps Script. Paste:

```js
function doPost(e) {
  const s = SpreadsheetApp.getActiveSheet();
  const d = JSON.parse(e.postData.contents);
  s.appendRow([d.name, d.phone, d.email, d.college, d.branch, d.year, d.code, d.ref, d.source, d.ts]);
  return ContentService.createTextOutput("ok");
}
```
3. Deploy → New deployment → Web app → Execute as *Me*, access *Anyone* → copy the URL.
4. In `landing/index.html`, set `CONFIG.WEBHOOK_URL` to that URL.

## Add your social links
In `landing/index.html`, fill the `SOCIAL` block inside `CONFIG` with your own links (Instagram profile, YouTube channel, LinkedIn page, WhatsApp community/group, Telegram group). Until you do, each button opens that platform's home page.

## Important notes
- Without the webhook, data is stored only in the visitor's own browser (fine for a demo, not for a real campaign). Referral counts and the leaderboard are therefore per-browser until the webhook is connected and the page reads from the Sheet.
- Set `CONFIG.WORKSHOP_DATE` to the real date/time.
- The seat meter shows only real registrations, no fake numbers. Demo data is only on the admin page.
- Phone numbers and emails are personal data. Collect only what you need and tell students how it's used.
