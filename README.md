# palavasi-sms-terms

Public **SMS Terms & Conditions** page for the text messaging program of
The Cleaning Authority - Coral Springs.

- Live URL: https://palavasiservicegroup.vercel.app
- Content owner: **Palavasi Service Group LLC**, operating as The Cleaning Authority - Coral Springs.
  The legal text on the page belongs to Palavasi and should only change with Palavasi's approval.
- Hosting: Rare Technologies LLC hosts and deploys this page as a service provider to Palavasi.

This page is the Terms & Conditions URL for Palavasi's Twilio A2P 10DLC campaign. It must stay
publicly reachable, with no login and no Vercel Deployment Protection on the production URL.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole page: hand-written HTML with an inline `<style>` block. No build step, no external requests. |
| `.vercelignore` | Keeps `README.md` out of the deployment so only the page is served. |

## Editing

1. Edit the text in `index.html`. Keep the heading structure (h1, h2, h3 per section).
2. If the terms change, update the **Effective date** line in the header.
3. Do not add external CSS, scripts, fonts, analytics, or tracking.
4. Keep hosting-provider names out of `index.html`. This README is the only place they belong.

To add another page later (for example an SMS Privacy Policy), copy `index.html` to a new file
such as `privacy.html`, keep the same `<style>` block, and replace the content inside `<main>`.

## Deploying

The Vercel project is `palavasiservicegroup`.

- This GitHub repo is connected to the Vercel project. Pushing to `main` deploys to production.
- To deploy manually from this folder instead:

  ```bash
  vercel --prod
  ```

## Checking the live page

```bash
curl -sS -o /dev/null -w "%{http_code} %{content_type}\n" https://palavasiservicegroup.vercel.app/
```

The result should be `200 text/html; charset=utf-8`. A `401`, or a redirect to vercel.com, means
Deployment Protection is on and must be turned off for production.
