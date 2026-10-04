# CrickBase

CrickBase is a web app that adds up how many overs a young cricketer bowls across every team they play for (club, school, district and county) and checks the total against the ECB Fast Bowling Directives. It is aimed at under-13 players and the parents and coaches who look after them, and it flags when workload goes over guidance or when pain means they should see a doctor or physiotherapist.

> **CrickBase is not a medical device. It does not diagnose anything, and it never replaces a coach, doctor or physiotherapist.** It never tells a player they are "safe" to play. It only shows how the overs they have logged compare with published guidance.

**Live site:** _link coming soon — replace this line with the GitHub Pages address once it is published._

## Who built it and why

CrickBase was built by Shiven, a Year 8 student, in the Imperial EDGE AI Startup Accelerator.

Young bowlers often play for more than one team, such as a club, a school and a county pathway. Each team only sees its own overs, so nobody adds up the total. CrickBase does that sum so overuse is easier to spot before it becomes an injury.

## What works in the current version

- **Combined workload tracking.** Log overs for each team (club, school, district, county pathway, other). They are added together into one 7-day total.
- **ECB limit checks.** Your logged overs are compared with the ECB limits for your age group (see below).
- **Warnings when a player goes over.** The app shows "Within guidance", "Approaching limit" or "Over guidance". Right after you log overs, it adds up everything logged for that day across all your teams and checks it against the daily limit.
- **Pain check with escalation.** After logging, the app asks about pain. If pain is rated 4 out of 10 or higher, or is described as getting worse or worse when bowling, it says: **"See a doctor or physiotherapist."** This rule is fixed in the app's code. A weekly check-in uses the same worsening-pain rule.
- **Stats.** Log matches (runs, wickets, overs) and see a season summary. Overs from a match are added to the workload total automatically.
- **Training plan.** A weekly checklist you can tick off and add to.

## ECB limits it checks

The limits come from the ECB Fast Bowling Directives. Set the age group in **Personalisation** (the person icon, top right). CrickBase is aimed at under-13s, so players should choose **Up to U13**.

| Age group | Maximum overs per day |
|---|---|
| Up to U13 | 10 |
| U14 / U15 | 12 |
| U16 – U19 | 18 |
| Senior | no limit applied |

It also checks two weekly rules: bowling on **more than 4 days in any 7-day period** shows "Over guidance", and bowling on **3 or more days in a row** shows "Approaching limit".

These are guidance, not a guarantee. Always check the current ECB directives and your own league's rules.

## What doesn't work yet

- **No chat on the live version.** The AI chat about workload and training plans needs an AI key, so it is only available in the demo version. The AI "tailored advice" after going over the limit is also demo-only. The doctor/physio message does not depend on AI and still works.
- **Data doesn't move between devices.** There are no accounts and no server. Everything is saved in your own browser, so it won't appear on another phone or computer, and clearing your browser data deletes it.
- **Age group defaults to U14/U15.** Under-13 players need to change it to "Up to U13" in Personalisation to get the under-13 limit.
- **Not every ECB limit is checked.** Per-spell limits and net/practice ball limits are not checked yet.
- **The 7-day summary can miss a combined day.** On the Injury prevention screen it compares the daily limit with your biggest single entry, not the combined total for the day. The check straight after logging does add up the whole day.
- **Possible double counting.** Overs logged inside a match are added to your workload automatically. If you also log the same overs separately, they are counted twice.
- **It only knows what you tell it.** Warnings are only as accurate as the overs entered.

## Run it yourself

CrickBase is a single file with no build step. Download `index.html` and open it in a browser. Fonts load from Google Fonts, so they fall back to default fonts if you are offline.

## Built with

Plain HTML, CSS and JavaScript. Data is saved in the browser with `localStorage`.

## Licence

Released under the MIT Licence. See the `LICENSE` file.
