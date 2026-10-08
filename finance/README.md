# Kasa: money tracker for salary + tips

A phone-first app to log your monthly salary, the tips you make each day, and everything you spend.
It shows what's left this month, where the money went, and gives you a straight monthly report on what to fix.

## What it does

- **Log fast:** tap **+**, pick Tips / Spending / Salary / Other, type the amount (`12,50` and `12.50` both work), save.
- **Overview:** money left this month, your pace to month end, savings goal, a day-by-day chart of tips vs spending, and spending by category split into needs and wants.
- **Straight talk:** instant, blunt feedback from your numbers (overspending pace, biggest leak, small purchases adding up, categories creeping up, weekend spending).
- **Coach:** once a month (or mid-month), Claude reads your numbers and writes a report: a grade, where the money leaked, 3 to 5 concrete rules with how much each saves, and targets for next month. Next month the Overview tracks you against those targets.

## Put it on your phone

1. Turn on GitHub Pages for this repo: **Settings → Pages → Deploy from a branch → `main` / root**.
2. Open `https://dang-23.github.io/Sajtovi/finance/` on your phone.
3. **iPhone:** Safari → Share → **Add to Home Screen**. **Android:** Chrome → ⋮ → **Install app**.

It then opens like a normal app and works offline. Your data is stored on the phone (use **Settings → Export backup** now and then).

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
