# palavasi-sms-terms

Public **SMS Terms & Conditions** page for the text messaging program of
The Cleaning Authority - Coral Springs.

- Terms URL (the one registered with Twilio): https://palavasiservicegroup.vercel.app/sms-terms
- Content owner: **Palavasi Service Group LLC**, operating as The Cleaning Authority - Coral Springs.
  The legal text on the page belongs to Palavasi and should only change with Palavasi's approval.
- Hosting: Rare Technologies LLC hosts and deploys this page as a service provider to Palavasi.

This page is the Terms & Conditions URL for Palavasi's Twilio A2P 10DLC campaign. It must stay
publicly reachable, with no login and no Vercel Deployment Protection on the production URL.

## Files

| File | Purpose |
| --- | --- |
| `sms-terms.html` | The whole page: hand-written HTML with an inline `<style>` block. No build step, no external requests. |
| `vercel.json` | Serves `sms-terms.html` at `/sms-terms` and rewrites `/` to it, with no redirect. |
| `.vercelignore` | Keeps `README.md` and local files out of the deployment so only the page is served. |

## Stable path

`/sms-terms` is the permanent address of these terms. The root URL `/` currently shows the same
page through a rewrite, but a future home page may replace that rewrite. Never move or rename
`sms-terms.html`, because Twilio stores the Terms URL on the campaign.

## Editing

1. Edit the text in `sms-terms.html`. Keep the heading structure (h1, h2, h3 per section).
2. If the terms change, update the **Effective date** line in the header.
3. Do not add external CSS, scripts, fonts, analytics, or tracking.
4. Keep hosting-provider names out of `sms-terms.html`. This README is the only place they belong.

To add another page later (for example an SMS Privacy Policy), copy `sms-terms.html` to a new
file such as `sms-privacy.html`, keep the same `<style>` block, replace the content inside
`<main>`, and update its canonical link. With `cleanUrls` on, it is served at `/sms-privacy`.

## Deploying

The Vercel project is `palavasiservicegroup`.

- This GitHub repo is connected to the Vercel project. Pushing to `main` deploys to production.
- To deploy manually from this folder instead:

  ```bash
  vercel --prod
  ```

## Checking the live page

```bash
for u in https://palavasiservicegroup.vercel.app/ https://palavasiservicegroup.vercel.app/sms-terms; do
  curl -sS -o /dev/null -w "$u -> %{http_code} %{content_type} redirect=%{redirect_url}\n" "$u"
done
```

Both should return `200 text/html; charset=utf-8` with an empty `redirect=`. A `401`, or a
redirect to vercel.com, means Deployment Protection is on and must be turned off for production.
