---
name: g2-review-miner
description: Takes a G2 or Capterra product URL, scrapes up to 100 reviews via Apify, and outputs a battlecard-ready competitive intelligence report: clustered pros/cons, switching reasons, buyer objections, discovery questions, and positioning opportunity. Use when asked to analyze competitor reviews, mine G2 data, build a competitive battlecard, understand why buyers switch, research competitor weaknesses, or turn review data into sales intelligence. Trigger when a user says "analyze reviews for", "mine G2 for", "build a battlecard from reviews", "what do buyers say about", "research competitor on G2", "why do people switch from", or "turn G2 reviews into a battlecard".
compatibility: [claude-code, gemini-cli, github-copilot]
---

# G2 Review Miner

Scrape G2 or Capterra reviews for any product. Output a battlecard-ready competitive intelligence report with clustered themes, switching reasons, and buyer objections.

---

**Critical rule:** All quotes in the output must be verbatim from the review data. Never paraphrase, summarize, or invent a quote. If a theme has fewer than 2 supporting reviews, do not include it.

---

## Common Mistakes

| The agent will want to... | Why that's wrong |
|---|---|
| Paraphrase quotes to make them sound cleaner | Battlecard credibility depends on exact buyer language. Paraphrased quotes are useless. |
| Continue after Apify returns fewer than 5 reviews | Fewer than 5 reviews produces unreliable themes. The URL is likely wrong or the product has no data. |
| Hallucinate a theme not supported by the reviews | One fabricated theme invalidates the whole battlecard for the sales team using it. |
| Skip the Gemini retry on empty response | A truncated analysis produces an incomplete battlecard with no signal to the user. |

---

## Step 1: Setup Check

```bash
echo "GEMINI_API_KEY: ${GEMINI_API_KEY:+set}"
echo "APIFY_API_TOKEN: ${APIFY_API_TOKEN:+set}"
```

**If GEMINI_API_KEY is missing:** Stop. Tell the user: "GEMINI_API_KEY is required. Get it at aistudio.google.com. Add it to your .env file."

**If APIFY_API_TOKEN is missing:** Stop. Tell the user: "APIFY_API_TOKEN is required to scrape G2/Capterra. Get it at console.apify.com/account/integrations. Free tier includes enough credits for ~50 runs."

---

## Step 2: Gather Input

You need:
- A G2 or Capterra product URL (required)
- Optional: focus mode: `full` (default), `objections-only`, or `switching-reasons`

**URL format guidance:**
- G2: `https://www.g2.com/products/[product-slug]/reviews`
- Capterra: `https://www.capterra.com/p/[ID]/[product-name]/reviews/`

Auto-detect the platform from the URL domain. If neither `g2.com` nor `capterra.com` appears in the URL: ask the user to provide a valid G2 or Capterra reviews page URL.

If the user has not provided a URL, ask: "What is the G2 or Capterra reviews URL for the product you want to analyze?"

---

## Step 3: Scrape Reviews via Apify

**For G2 URLs** (automation-lab/g2-scraper):

```bash
curl -s -X POST \
  "https://api.apify.com/v2/acts/automation-lab~g2-scraper/run-sync-get-dataset-items?token=$APIFY_API_TOKEN&timeout=120" \
  -H "Content-Type: application/json" \
  -d "{\"url\": \"G2_URL_HERE\", \"maxReviews\": 100, \"sortBy\": \"recent\"}" \
  > /tmp/g2-raw-response.json

python3 -c "
import json, sys
data = json.load(open('/tmp/g2-raw-response.json'))
print(f'Reviews fetched: {len(data)}')
"
```

**For Capterra URLs** (epctex/capterra-scraper):

```bash
curl -s -X POST \
  "https://api.apify.com/v2/acts/epctex~capterra-scraper/run-sync-get-dataset-items?token=$APIFY_API_TOKEN&timeout=120" \
  -H "Content-Type: application/json" \
  -d "{\"startUrls\": [{\"url\": \"CAPTERRA_URL_HERE\"}], \"maxItems\": 100}" \
  > /tmp/g2-raw-response.json

python3 -c "
import json, sys
data = json.load(open('/tmp/g2-raw-response.json'))
print(f'Reviews fetched: {len(data)}')
"
```

**If response returns fewer than 5 reviews:** Stop. Tell the user: "Could not fetch enough reviews. Check that the URL points to a product reviews page (not a category or search page). G2 format: g2.com/products/[slug]/reviews. Capterra format: capterra.com/p/[ID]/[name]/reviews/"

**If the curl request times out or returns an error:** Try once with `timeout=180`. If it still fails: tell the user "Apify request failed. Check your APIFY_API_TOKEN and try again. If the issue persists, the product may have anti-scraping protections."

---

## Step 4: Pre-process Reviews

Extract and normalize fields from the raw response:

```bash
python3 << 'PYEOF'
import json, sys

raw = json.load(open('/tmp/g2-raw-response.json'))
reviews = []

for r in raw:
    # Handle both G2 and Capterra field naming
    pros = r.get('pros') or r.get('benefits') or ''
    cons = r.get('cons') or r.get('drawbacks') or ''
    
    # Skip reviews with no substantive text
    if not pros.strip() and not cons.strip():
        continue
    
    reviews.append({
        'rating': r.get('rating') or r.get('overallRating') or '',
        'pros': pros.strip(),
        'cons': cons.strip(),
        'loveTheme': r.get('loveTheme') or '',
        'hateTheme': r.get('hateTheme') or '',
        'reviewerTitle': r.get('reviewerTitle') or r.get('jobTitle') or '',
        'companySize': r.get('companySize') or '',
        'reviewDate': r.get('reviewDate') or r.get('date') or '',
    })

# Cap at 100
reviews = reviews[:100]
json.dump(reviews, open('/tmp/g2-reviews-clean.json', 'w'), indent=2)
print(f'Reviews after filtering: {len(reviews)}')
PYEOF
```

---

## Step 5: Analyze with Gemini

Write the analysis request and call Gemini:

```bash
python3 << 'PYEOF'
import json

reviews = json.load(open('/tmp/g2-reviews-clean.json'))
review_text = json.dumps(reviews, indent=2)

request = {
    "system_instruction": {
        "parts": [{
            "text": "You are a competitive intelligence analyst. Analyze the provided product reviews and output a structured JSON battlecard. Rules: (1) Every quote must be verbatim from the review data. (2) Only include a theme if at least 2 reviews support it. (3) Do not invent, paraphrase, or summarize quotes. (4) Do not use marketing language. (5) Do not name specific competitor products in the positioning opportunity section. Output only valid JSON, no commentary."
        }]
    },
    "contents": [{
        "parts": [{
            "text": f"Analyze these product reviews and return a JSON object with exactly these 6 keys:\n\n1. top_pros: array of 4-6 objects, each with: theme (string), review_count (int), quotes (array of 2 verbatim strings)\n2. top_cons: array of 4-6 objects, each with: theme (string), review_count (int), quotes (array of 2 verbatim strings)\n3. switching_reasons: array of 3-5 objects, each with: reason (string), pattern (one of: missing_feature, pricing, performance, support, integration), quote (verbatim string)\n4. buyer_objections: array of 4-6 objects, each with: objection (string), frequency (High/Medium/Low), suggested_response (string)\n5. discovery_questions: array of exactly 5 open-ended questions (strings) a sales rep can ask based on the pain themes found\n6. positioning_opportunity: string of 2-3 sentences describing what gap in this product's reviews represents an opening\n\nReviews:\n{review_text}"
        }]
    }],
    "generationConfig": {
        "temperature": 0.2,
        "maxOutputTokens": 4096
    }
}

json.dump(request, open('/tmp/g2-analysis-request.json', 'w'))
PYEOF

curl -s -X POST \
  "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=$GEMINI_API_KEY" \
  -H "Content-Type: application/json" \
  -d @/tmp/g2-analysis-request.json \
  | python3 -c "
import sys, json
d = json.load(sys.stdin)
text = d['candidates'][0]['content']['parts'][0]['text']
# Strip markdown code fences if present
text = text.strip()
if text.startswith('\`\`\`'):
    text = '\n'.join(text.split('\n')[1:-1])
print(text)
json.dump(json.loads(text), open('/tmp/g2-battlecard.json', 'w'), indent=2)
print('Analysis saved to /tmp/g2-battlecard.json', file=sys.stderr)
"
```

**If the Gemini response is empty or JSON parsing fails:** Retry once with `maxOutputTokens` reduced to 2048:

```bash
# Retry with reduced token limit
python3 -c "
import json
req = json.load(open('/tmp/g2-analysis-request.json'))
req['generationConfig']['maxOutputTokens'] = 2048
json.dump(req, open('/tmp/g2-analysis-request.json', 'w'))
"
# Re-run the same curl command above
```

If the retry also fails: present whatever partial output was returned, mark missing sections with `[INCOMPLETE]`, and tell the user: "Gemini analysis was incomplete. Partial results shown below. Try again with a smaller review set by adding a date filter to the URL."

---

## Step 6: Self-QA

Before presenting output, verify:

- [ ] Each theme in top_pros and top_cons has review_count >= 2
- [ ] All quotes exist verbatim in `/tmp/g2-reviews-clean.json` (spot-check 3 quotes)
- [ ] buyer_objections has at least 3 items
- [ ] All 5 discovery_questions are open-ended (start with "How", "What", "When", "Why", "Tell me", "Walk me through")
- [ ] positioning_opportunity does not name specific competitor products
- [ ] No marketing language: "game-changing", "revolutionary", "powerful", "seamless", "best-in-class"

If any check fails: fix before presenting. Do not present output with QA failures.

---

## Step 7: Save Output

Extract product name from URL slug, then save:

```bash
PRODUCT_SLUG=$(echo "G2_URL_HERE" | python3 -c "import sys; u=sys.stdin.read().strip(); print(u.split('/products/')[-1].split('/')[0] if 'g2.com' else u.split('/')[-2])")
DATE=$(date +%Y-%m-%d)
OUTPUT_FILE="docs/competitive-intel/${PRODUCT_SLUG}-${DATE}.md"
mkdir -p docs/competitive-intel
echo "Saving to $OUTPUT_FILE"
```

---

## Step 8: Present Output

```
## G2 Review Mining: [Product Name]
Source: [URL] | Reviews analyzed: [N] | Date: [today]

---

### What buyers love

[For each theme: "**[Theme]** ([N] reviews)" followed by 2 indented quotes]

---

### What buyers complain about

[For each theme: "**[Theme]** ([N] reviews)" followed by 2 indented quotes]

---

### Why buyers switch or consider switching

[For each reason: "**[Reason]** ([pattern type])" followed by the verbatim quote]

---

### Common objections your sales team will face

| Objection | Frequency | Suggested response |
|---|---|---|
[one row per objection]

---

### Discovery questions for your sales reps

1. [question]
2. [question]
3. [question]
4. [question]
5. [question]

---

### Positioning opportunity

[2-3 sentences]

---
Saved to: [OUTPUT_FILE]
```

Clean up temp files after presenting:

```bash
rm -f /tmp/g2-raw-response.json /tmp/g2-reviews-clean.json /tmp/g2-analysis-request.json /tmp/g2-battlecard.json
```
