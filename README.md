# Philippine-Drama

Short-drama streaming app for Philippine viewers: vertical 1–2 minute episodes, first episodes free, later episodes unlocked with coins. Working app name: **Serye** (placeholder until the business name is registered).

## Status

| Part | State |
|---|---|
| Clickable prototype (`prototype/index.html`) | Done, test mode only |
| Production app (Android + web) | Not started |
| Backend (Firebase, Singapore region) | Not started |
| Payments (Google Play billing, PayMongo) | Waiting on business registration |

## Try the prototype

Open `prototype/index.html` in any browser (best on a phone-sized window). All data stays in that browser. Top-ups are simulated and charge nothing.

## Coin accounting rules

These rules apply in the prototype and must carry into production:

- Money is stored as whole centavos. No floating-point amounts.
- Paid coins sit in purchase lots, spent first-in first-out. Unspent paid coins are deferred revenue (a liability).
- Revenue is recognized when paid coins unlock an episode. The last coins of a lot carry its remaining value, so rounding never leaves a centavo behind.
- Bonus coins (sign-up, daily check-in, ads) have no cash value and are tracked separately.
- Unlocks and purchases are idempotent: the same episode or payment is never charged or credited twice.
- Balances are derived from the ledger, never edited directly.
- Cash received must always equal recognized revenue plus deferred revenue.

## Open decisions

- Spend order: bonus coins first (current) or paid coins first.
- Episode price and coin pack pricing.
- When BIR treats coin sales as taxable: at purchase or at unlock (confirm with accountant).

## Content

All series are original stories made with AI video tools. No copying of existing series. Sample series in the prototype are placeholders written for testing.
