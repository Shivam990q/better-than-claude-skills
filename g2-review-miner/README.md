# g2-review-miner

Mine G2 or Capterra reviews for any product. Get a battlecard-ready competitive intelligence report in minutes: clustered pros/cons, switching reasons, buyer objections, and positioning gaps.

## Installation

### Prerequisites

You need [Node.js](https://nodejs.org/) installed. It comes with `npx` built in.

### Option 1: npx (All Agents)

```bash
npx "@opendirectory.dev/skills" install g2-review-miner --target claude
```

Supported `--target` values: `claude`, `gemini`, `codex`, `opencode`, `anti-gravity`, `openclaw`, `hermes`

### Option 2: Native Plugin (Claude Code Only)

Run these two commands inside your Claude Code terminal:

```bash
# Add the OpenDirectory marketplace
/plugin marketplace add Varnan-Tech/opendirectory

# Install a skill directly
/plugin install g2-review-miner@opendirectory-marketplace
```

### Option 3: Claude Desktop App

**Step 1: Download**
Click **Code → Download ZIP** on this repo's GitHub page.

**Step 2: Install**
1. Open Claude Desktop > Customize > Skills > **+** > Upload a skill
2. Drop the downloaded zip or extracted folder

## What It Does

- Takes a G2 or Capterra product URL
- Scrapes up to 100 reviews via Apify (handles anti-bot protections automatically)
- Clusters pros and cons into themes with frequency counts and verbatim quotes
- Extracts switching reasons by pattern: missing features, pricing, performance, support, integrations
- Surfaces buyer objections with suggested sales responses
- Generates discovery questions for your sales reps
- Identifies positioning opportunities based on what buyers consistently ask for but don't get
- Saves output to `docs/competitive-intel/[product]-[date].md`

## Requirements

| Requirement | Purpose | How to Set Up |
|---|---|---|
| Gemini API key | Review clustering and battlecard generation | aistudio.google.com, Get API key |
| Apify API token | Scraping G2 and Capterra reviews | console.apify.com/account/integrations |

## Setup

```bash
cp .env.example .env
# Add GEMINI_API_KEY and APIFY_API_TOKEN
```

Apify's free tier includes $5 platform credits: enough for approximately 50 runs.

## How to Use

```
"Mine G2 reviews for https://www.g2.com/products/notion/reviews"
"Build a battlecard from Capterra reviews: https://www.capterra.com/p/186596/Notion/reviews/"
"What do buyers say about HubSpot CRM? https://www.g2.com/products/hubspot-crm/reviews"
"Why do people switch from Salesforce? https://www.g2.com/products/salesforce-crm/reviews"
"Analyze competitor reviews for https://www.g2.com/products/[slug]/reviews"
```

## Output

Each run produces a 6-section battlecard:

1. **What buyers love**: clustered positive themes with verbatim quotes
2. **What buyers complain about**: clustered negative themes with verbatim quotes
3. **Why buyers switch**: switching reasons by pattern (feature gap, pricing, performance, support, integration)
4. **Common objections**: what prevents new buyers from adopting, with suggested sales responses
5. **Discovery questions**: 5 open-ended questions your sales reps can use
6. **Positioning opportunity**: what gap in this product's reviews represents an opening

## Cost per Run

- Apify: ~$0.02-$0.08 per 100 reviews
- Gemini: ~$0.01-$0.03 per analysis
- Total: ~$0.10-$0.30 per competitor

## Project Structure

```
g2-review-miner/
├── SKILL.md
├── README.md
├── .env.example
├── evals/
│   └── evals.json
└── references/
    ├── battlecard-format.md
    └── apify-actors.md
```

## License

MIT
