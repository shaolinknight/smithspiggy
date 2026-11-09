# Runway (monthly tabs) 2.32: setup and what's new

This is the version of Runway for a budget kept with **one tab per month** (Mar, Apr, June…). It now has all of Piggy 2.32's features. The monthly-tab parts work the same as before.

## Updating from 2.1 (the version you have now)

**Files changed:** everything. The app went from one file to a small site folder, and the script is new (version 20).

1. **Put the script in the sheet.**
   - Open the budget sheet and go to **Extensions → Apps Script**.
   - Replace everything there with `Code-v20.gs`. Put your passphrase back on the `var PASSCODE = …` line, then Save.
   - Go to **Deploy → Manage deployments → ✏️ → Version: New version → Deploy**. The URL stays the same.
2. **Put the site online.** Upload the contents of the zip:
   - **Cloudflare + GitHub:** put `public/` and `wrangler.jsonc` in the repo, the same layout as Piggy's.
   - **Netlify:** drag the `public` folder onto the site's Deploys page.
3. **Open the app from the Home Screen.**
   - The app keeps its connection and settings.
   - Anything still waiting to sync is sent.
   - Tithing moves into the new **Giving** group once. If you move it back in the **app groups** tab, it stays where you put it.

## Setting up from scratch (a new phone or a new person)
1. Open the budget sheet, then go to **Extensions → Apps Script** and delete what's there.
2. In the app, open **Settings → Google Sheet → How to set up a sheet** and tap **Copy the script**. The copied script already contains a passcode. Paste it in and Save.
3. Go to **Deploy → New deployment → Web app**. Set Execute as **Me** and access **Anyone**, then approve the permission prompt.
4. Paste the web-app URL into the app and tap **Connect**.

A new, empty sheet works too. The first month tab is made in the same layout.

## How the sheet is used (unchanged)
- **Logging:** a $45 purchase adds **+45** to that category's Actual cell on the month's tab. Edits and deletes change just that part.
- **Budgets:** these come from each month's **Planned** column. Changes made in Plan are written there.
- **New months:** a month with no tab yet is copied from the latest one, with the same plan and Actual cleared.
- **New categories:** these get a row above Miscellaneous, and the `=sum(E6:E)` totals keep counting them.
- **Notes:** the notes under the income table show at the bottom of each month, and you can add or delete them there.

## New since 2.1 (everything from Piggy up to 2.32)
- **Look:** a new design, with 12 colourways and ready-made looks. The friend's colour moves to the closest new one.
- **Computers:** a desktop/tablet layout with keyboard shortcuts.
- **Setup and preview:** a first-run screen. The app can be used on the phone alone, with a sheet connected later.
- **Bills:**
  - Recurring bills can repeat every few weeks, months or years, and are checked off when paid.
  - **Autopay** bills check themselves off.
  - Bills are kept in the **recurring** tab, which gets three new columns: every, unit, next due.
- **Savings goals:** kept in a new **goals** tab.
- **Giving:** a group of its own.
- **Entries:**
  - Split a purchase across categories.
  - Mark one **paid from savings**.
  - Track what someone **owes back**, and when they paid.
- **Email alerts:** bills due, over budget, and a monthly recap. Turn them on in Settings → Alerts.
- **Several devices:** settings, category order and checked-off bills are shared through a new **app settings** tab, so a second phone or a computer stays in step.
- **Sync safety:** a change that's retried after a dropped connection is never made twice.
- **Plan:** Plan is organised as This month / Ahead / Trips / Goals, with a button to cancel a change that hasn't started yet.

## What's added to the sheet
| Tab | What it holds |
|---|---|
| app log | Gains three columns: **from savings**, **owed back**, **paid back**. The "How this tab works" note moves to column N. |
| app groups | Can now say **giving**. |
| goals | Savings goals (new). |
| app settings | A copy of the app's settings (new). Don't edit it. |
| recurring | Gains **every**, **unit**, **next due**. |

The month tabs themselves don't change.

## Worth knowing
- **"Paid from savings" and "owed back":**
  - The full amount still goes in the month's Actual cell, so the sheet's totals show everything that went out.
  - The app counts only your share against the budget.
  - The sheet and the app can therefore differ for those categories.
- **Trips:** trip spending works the same way. It's in the sheet's Actual, but kept apart in the app.
- **Next year:** "Keep these numbers for next year" in Plan makes the **Jan 2027** tab.
