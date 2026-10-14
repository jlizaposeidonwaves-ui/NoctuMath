# NoctuMath — Go-Live Setup (about 30 minutes, mostly clicking)

## What changed in this version
- Real checkout buttons replace the fake card form (Lemon Squeezy hosted checkout)
- License-key activation built into the paywall ("already paid? activate your key")
- Cancel subscription now opens the real Lemon Squeezy customer portal
- New pages: privacy.html and terms.html (required by payment processors)
- PWA restored: manifest.webmanifest + sw.js (app installs and works offline)

## Your 5 steps (the only things I can't do for you)

### 1. Lemon Squeezy account (10 min)
- Sign up at app.lemonsqueezy.com and finish store verification
  (same process you started for Celestial Foresight — one account covers both)
- Store name: NoctuMath. When it asks for your site: https://noctumath.com

### 2. Create the product (10 min)
- Products > New Product > name: "NoctuMath Parent Plan"
- Pricing: two variants —
  - Monthly: $4.99 subscription, bills monthly
  - Yearly: $39 subscription, bills yearly
- Turn ON "Generate license keys" for the product (this is the important switch)
- For each variant, click Share > copy the checkout link

### 3. Paste 3 things into index.html (2 min)
Near the top of the app script, find `NM_PAY` and replace:
- PASTE_MONTHLY_CHECKOUT_URL  -> your monthly checkout link
- PASTE_YEARLY_CHECKOUT_URL   -> your yearly checkout link
- CUSTOMER_PORTAL             -> Settings > Store > Customer portal URL

### 4. Deploy (5 min)
- Upload ALL files in this folder to your GitHub repo (replace old index.html)
- GitHub Pages redeploys automatically; noctumath.com updates in ~1 minute

### 5. Test with $0 (5 min)
- In Lemon Squeezy, generate a test license key (Licenses > create)
- Open noctumath.com > Parent Plan > paste the key > Activate
- Dashboard, worksheets, 50-question quizzes should unlock

## How a real purchase flows (all automatic)
1. Parent clicks Subscribe -> Lemon Squeezy checkout (cards, PayPal, Apple Pay)
2. LS emails them a receipt + license key
3. They paste the key into the app once -> Parent Plan unlocks on that device
4. Billing, tax/VAT, refunds, cancellation: handled by Lemon Squeezy.
   You just get paid out.

## Still missing (Phase 2 — after first sales)
- Cloud accounts (progress syncs across devices; needs a small backend)
- Weekly parent progress emails (retention engine)
- support@noctumath.com inbox (Google Workspace ~$6/mo, or free forwarding)

Questions? Paste me any Lemon Squeezy screen and I'll tell you what to click.
