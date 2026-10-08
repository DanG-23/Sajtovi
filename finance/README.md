# Kasa: money tracker for salary + tips

A phone-first app to log your monthly salary, the tips you make each day, and everything you spend.
It shows what's left this month, where the money went, and gives you a straight monthly report on what to fix.

## What it does

- **Log fast:** tap **+**, pick Tips / Spending / Salary / Other, type the amount (`12,50` and `12.50` both work), save.
- **Overview:** money left this month, your pace to month end, savings goal, a day-by-day chart of tips vs spending, and spending by category split into needs and wants.
- **Straight talk:** instant, blunt feedback from your numbers (overspending pace, biggest leak, small purchases adding up, categories creeping up, weekend spending).
- **Coach:** once a month (or mid-month), Claude reads your numbers and writes a report: a grade, where the money leaked, 3 to 5 concrete rules with how much each saves, and targets for next month. Next month the Overview tracks you against those targets.

## Put it on your phone

**One-time setup (on GitHub, 1 minute):**
1. Go to <https://github.com/DanG-23/Sajtovi/settings/pages>.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Pick the branch that has the `finance` folder (`main` once this is merged, or `claude/finance-tracking-app-or1q0b`), folder **/ (root)**, then **Save**.
4. Wait a minute or two until the page says "Your site is live".

**Install on the phone:** open <https://dang-23.github.io/Sajtovi/finance/> on the phone, then:
- **iPhone:** in Safari tap **Share** (under **⋯** on newer iPhones) → **Add to Home Screen** → **Add**.
- **Android:** in Chrome tap **Install** when it pops up, or **⋮** → **Install app** / **Add to Home screen**.

Kasa then has its own icon, opens full screen, and works offline. Your data is stored on the phone.
On iPhone, the home-screen app keeps its own data separate from Safari, so install it first and then start logging
(or move data over with **Settings → Export backup / Import backup**).

## Turn on the AI coach

In **Settings → AI coach**, paste an Anthropic API key from <https://console.anthropic.com/settings/keys>.
The key stays on your phone and is only sent to Anthropic. Reports use `claude-opus-5-5`; one report costs a few cents.

Without a key, the Coach still works using built-in rules (less sharp, no AI).

When the same page is opened inside the Claude app as an artifact, the coach uses your Claude account instead (no key needed) and your entries sync to your account.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole app (HTML, CSS, JS) |
| `manifest.webmanifest`, `icons/` | Lets phones install it as an app |
| `sw.js` | Offline support. Bump `VERSION` when you change the app so phones pick up the update |
| `vendor/anthropic-sdk.js` | Official Anthropic TypeScript SDK (v0.127.0), bundled for the browser |
