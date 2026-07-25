# Lease Deal Evaluator

Mobile-first car lease calculator with deal quality scoring, built for use at the dealership.

## Features

- **Deal scoring** using the 1% rule (monthly payment as % of MSRP)
- **Real-time calculation** as you type — no submit button
- **Florida tax logic** (6% state + configurable county surtax on monthly payment)
- **Save & compare** deals from different dealerships (persisted in localStorage)
- **Money factor / APR toggle** — enter whichever the dealer gives you
- **Offline support** via service worker (works without internet at dealership)
- **Installable** as a PWA on Android ("Add to Home Screen")

## Deal Rating Scale

| Grade | % of MSRP (pre-tax, $0 down) | Meaning |
|-------|-------------------------------|---------|
| A+    | ≤ 0.70%                       | Exceptional |
| A     | ≤ 0.85%                       | Excellent |
| B+    | ≤ 1.00%                       | Good |
| B     | ≤ 1.15%                       | Fair |
| C     | ≤ 1.30%                       | Below average |
| D     | > 1.30%                       | Poor — negotiate harder |

## Deploy to GitHub Pages

```bash
gh repo create lease-calculator --public --source=. --push
# Then enable Pages: Settings → Pages → Source: main branch
```

Or use the GitHub CLI shortcut:

```bash
gh repo create lease-calculator --public --source=. --push
gh api repos/{owner}/lease-calculator/pages -X POST -f source.branch=main -f source.path=/
```

## Usage on Android

1. Open the GitHub Pages URL in Chrome
2. Tap the three-dot menu → "Add to Home Screen"
3. The app will work offline after the first visit
