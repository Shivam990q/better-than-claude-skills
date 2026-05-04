# Apify Actors Reference

## Primary Actors

### G2: automation-lab/g2-scraper
- Actor ID: `automation-lab~g2-scraper`
- Supports: 5M+ reviews across 220K+ products
- Input fields: `url` (G2 product reviews URL), `maxReviews` (int), `sortBy` ("recent" | "helpful")
- Key output fields:
  - `rating`: overall star rating (1-5)
  - `pros`: text summary of positive aspects
  - `cons`: text summary of negative aspects
  - `loveTheme`: G2's NLP-extracted positive sentiment theme
  - `hateTheme`: G2's NLP-extracted negative sentiment theme
  - `reviewerTitle`: reviewer's job title
  - `companySize`: categorical: "Small-Business", "Mid-Market", "Enterprise"
  - `reviewDate`: ISO date string
  - Per-dimension ratings: `easeOfUse`, `qualityOfSupport`, `easiestToDoBusinessWith`

### Capterra: epctex/capterra-scraper
- Actor ID: `epctex~capterra-scraper`
- Input fields: `startUrls` (array of URL objects), `maxItems` (int)
- Key output fields:
  - `overallRating`: star rating
  - `benefits`: pros equivalent
  - `drawbacks`: cons equivalent
  - `jobTitle`: reviewer title
  - `date`: review date

## Fallback Actor
If the primary actor fails or returns 0 results, try the combined scraper:

### zen-studio/software-review-scraper
- Actor ID: `zen-studio~software-review-scraper`
- Handles: G2 + Capterra + Trustpilot in one actor
- Use when: primary actor returns empty, times out, or hits rate limits

## API Call Pattern
All actors use the synchronous run endpoint:
```
POST https://api.apify.com/v2/acts/{ACTOR_ID}/run-sync-get-dataset-items?token={TOKEN}&timeout=120
```

- `run-sync-get-dataset-items`: waits for completion and returns results directly (no polling needed)
- `timeout=120`: 120 seconds max (increase to 180 if scraping large review sets)
- Returns: JSON array of review objects

## Cost
- Free plan: $5 platform credits (~50 runs)
- Typical run: ~$0.02-$0.08 for 100 reviews
- Compute: ~0.07-0.08 CUs per 100-review batch

## URL Formats
G2 product reviews:
```
https://www.g2.com/products/[product-slug]/reviews
```

Capterra product reviews:
```
https://www.capterra.com/p/[numeric-id]/[product-name]/reviews/
```

To find the slug: go to the product's G2 page and copy from the URL bar.
