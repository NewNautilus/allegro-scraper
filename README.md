[Allegro Scraper](https://apify.com/automation-lab/allegro-scraper?fpr=data)

Scrape product listings from **[Allegro.pl](https://allegro.pl)** — Poland's #1 e-commerce marketplace with over 125 million active listings. Extract prices, sellers, ratings, images, parameters, and delivery info from any search or category. Export to JSON, CSV, or Excel in minutes.

## What does Allegro.pl Product Scraper do?

Allegro.pl Product Scraper lets you **extract product listings at scale** from Poland's largest online marketplace. Just enter keywords or paste category URLs — the scraper handles pagination automatically and returns structured data for every product.

- ✅ Search by keyword across all categories
- ✅ Browse specific categories (e.g., laptops, shoes, electronics)
- ✅ Filter by price range, product condition, and sort order
- ✅ Extract complete product data: prices, sellers, images, ratings, shipping costs
- ✅ Includes product parameters (brand, specs, dimensions)
- ✅ Identifies sponsored vs. organic listings
- ✅ No Allegro account or API key required

Try it now: open the [Allegro.pl Product Scraper](https://apify.com/automation-lab/allegro-scraper) on Apify Store, enter a search keyword, and click Run.

## Who Is It For?

### 📊 E-commerce Analysts & Researchers

- Track competitor pricing across thousands of products
- Monitor price fluctuations over time with scheduled runs
- Research market positioning in specific product categories

### 🛍️ Procurement & Sourcing Teams

- Compare supplier prices for bulk purchasing decisions
- Find the best deals across millions of listings
- Build supplier shortlists based on seller ratings and reviews

### 🤖 Developers & Data Engineers

- Build price comparison platforms or shopping apps
- Power recommendation engines with real product data
- Feed business intelligence dashboards with fresh market data

### 📈 Marketing & SEO Teams

- Analyze competitor product titles and descriptions
- Track sponsored vs. organic product performance
- Research consumer demand signals from sales volume

## Why use this Allegro.pl Scraper?

- 🚀 **Fast extraction** — 60-75 products per page in under 30 seconds
- 📦 **Rich data** — 20+ fields per product including parameters, images, shipping
- 🔄 **Auto-pagination** — crawls as many pages as you need, up to 100 pages per query
- 🎯 **Flexible input** — keyword search, category URLs, price filters, condition filter
- 💾 **Multiple export formats** — JSON, CSV, Excel, XML via Apify's built-in tools
- 🔗 **API-ready** — integrate with Google Sheets, Zapier, Make, and 5,000+ apps
- 🛡️ **Resilient** — session rotation and retry logic handles bot detection automatically

## What data can you extract from Allegro.pl?

| 🏷️ Product Info | 💰 Pricing | 👤 Seller Info |
| --- | --- | --- |
| Product ID | Current price (PLN) | Seller login |
| Title | Original/sale price | Seller URL |
| Category path | Currency | Seller rating (%) |
| Condition (new/used) | Delivery price | Super Seller badge |
| Product images (up to 10) | Free delivery flag | Location |
| Product parameters |  |  |

| 📊 Engagement | 🏭 Logistics | 🔍 Search Context |
| --- | --- | --- |
| Rating (0-5) | Delivery price | Search query |
| Review count | Free delivery | Sponsored flag |
|  |  | Scraped timestamp |

## How much does it cost to scrape Allegro.pl?

This Actor uses **pay-per-event (PPE) pricing** — you pay only for products scraped, nothing for failed pages or overhead.

|  | Free plan | Starter ($29/mo) | Scale ($199/mo) | Business ($999/mo) |
| --- | --- | --- | --- | --- |
| **Per product** | $0.00345 | $0.003 | $0.00234 | $0.0018 |
| **1,000 products** | $3.45 | $3.00 | $2.34 | $1.80 |
| **10,000 products** | $34.50 | $30.00 | $23.40 | $18.00 |

Plus a one-time **$0.005 start fee** per run (covers browser startup cost).

**Real-world cost examples:**

| Query | Products | Duration | Cost (Free tier) |
| --- | --- | --- | --- |
| "laptop" (1 page) | ~74 | ~30s | ~$0.26 |
| "iPhone" (3 pages) | ~200 | ~90s | ~$0.69 |
| Category browse (5 pages) | ~350 | ~150s | ~$1.21 |

💡 Free plan users get **$5 credit** — enough for ~1,400 products.

## How to scrape Allegro.pl products

1. Open [Allegro.pl Product Scraper](https://apify.com/automation-lab/allegro-scraper) on Apify Store
2. Click **Try for free**
3. In **Search Queries**, enter keywords (e.g., `laptop gaming`, `iPhone 15`)
4. Set **Max Products per Search** (start with 20-50 to test)
5. Optionally filter by price range, condition, or sort order
6. Click **Start** and wait ~30 seconds
7. Download results in JSON, CSV, or Excel from the **Dataset** tab

### Input examples

**Keyword search (most common):**

```
{
    "searchQueries": ["laptop gaming", "tablet samsung"],
    "maxItemsPerQuery": 100,
    "sortBy": "relevance"
}
```

**Price-filtered search:**

```
{
    "searchQueries": ["buty sportowe"],
    "maxItemsPerQuery": 200,
    "minPrice": 100,
    "maxPrice": 500,
    "condition": "new",
    "sortBy": "price-asc"
}
```

**Category URL scraping:**

```
{
    "startUrls": [
        {"url": "https://allegro.pl/kategoria/laptopy-491"},
        {"url": "https://allegro.pl/kategoria/smartfony-i-telefony-komorkowe-165"}
    ],
    "maxItemsPerQuery": 300
}
```

## Input parameters

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `searchQueries` | string[] | — | Keywords to search on Allegro.pl |
| `startUrls` | URL[] | — | Direct Allegro listing or category URLs |
| `maxItemsPerQuery` | integer | 100 | Max products per query/URL |
| `minPrice` | integer | — | Min price filter in PLN |
| `maxPrice` | integer | — | Max price filter in PLN |
| `condition` | string | `all` | Product condition: `all`, `new`, `used` |
| `sortBy` | string | `relevance` | Sort: `relevance`, `price-asc`, `price-desc`, `newest` |

## Output examples

Each product is saved as a JSON object:

```
{
    "id": "17808132516",
    "url": "https://allegro.pl/oferta/hp-victus-15-gaming-ryzen-7-17808132516",
    "title": "Laptop HP Victus 15 15,6\" AMD Ryzen 7 16 GB / 512 GB szary",
    "price": 3551,
    "priceOriginal": null,
    "currency": "PLN",
    "seller": "INFLOO",
    "sellerUrl": "https://allegro.pl/uzytkownik/INFLOO",
    "sellerRating": 98.6,
    "imageUrl": "https://a.allegroimg.com/s720/11a3b1/...",
    "images": [
        "https://a.allegroimg.com/s720/11a3b1/...",
        "https://a.allegroimg.com/s360/11b9d1/..."
    ],
    "condition": "new",
    "isSponsored": false,
    "isSuperSeller": true,
    "reviewCount": 24,
    "rating": 4.8,
    "deliveryPrice": 10.49,
    "deliveryFree": false,
    "category": "Elektronika > Komputery > Laptopy",
    "location": "",
    "parameters": {
        "Marka": "HP",
        "System operacyjny": "Windows 11 Home",
        "Wielkość pamięci RAM": "16 GB",
        "Pojemność dysku": "512 GB",
        "Seria procesora": "AMD Ryzen 7",
        "Przekątna ekranu": "15.6\""
    },
    "searchQuery": "laptop gaming",
    "scrapedAt": "2026-04-03T02:41:01.609Z"
}
```

## Tips for best results

- 🔢 **Start small** — test with 20-50 products first to verify the data meets your needs
- 🌍 **Polish keywords work better** — use Polish terms (e.g., "buty sportowe" instead of "sport shoes") for more relevant results
- 📋 **Use category URLs** for comprehensive category coverage (up to 100 pages × 74 items)
- ⏱️ **Schedule runs** for price monitoring — Apify's scheduler runs actors automatically
- 💰 **Filter by price** to focus on the exact range you care about
- 🔄 **Sort by newest** to track new listings in a category
- 📊 **Export to Google Sheets** via Apify's built-in integration for team access

## Integrations

**Allegro.pl Product Scraper → Google Sheets**
Schedule daily runs and append new products to a Google Sheet for team price monitoring. Connect via Apify's Google Sheets integration in the actor settings.

**Allegro.pl Product Scraper → Slack/Discord**
Set up a webhook to alert your team when prices drop below a threshold. Combine with Make or Zapier to filter and format the notifications.

**Allegro.pl Product Scraper → Price Comparison Database**
Run the scraper for multiple product categories and store results in Apify Dataset or export to a database. Use the `id` field to track product changes over time.

**Allegro.pl Product Scraper → Make/Zapier Automation**
Trigger automated workflows from new product listings — email alerts, CRM updates, inventory management.

**Scheduled Price Monitoring**
Use Apify's scheduler (cron `0 9 * * *`) to run the scraper daily and track price trends over weeks or months.

## API Usage

### Node.js

```
import { ApifyClient } from 'apify-client';

const client = new ApifyClient({ token: 'YOUR_API_TOKEN' });

const run = await client.actor('automation-lab/allegro-scraper').call({
    searchQueries: ['laptop gaming'],
    maxItemsPerQuery: 100,
    sortBy: 'price-asc',
});

const { items } = await client.dataset(run.defaultDatasetId).listItems();
console.log(`Scraped ${items.length} products`);
```

### Python

```
from apify_client import ApifyClient

client = ApifyClient(token='YOUR_API_TOKEN')

run = client.actor('automation-lab/allegro-scraper').call(run_input={
    'searchQueries': ['laptop gaming'],
    'maxItemsPerQuery': 100,
    'sortBy': 'price-asc',
})

dataset = client.dataset(run['defaultDatasetId'])
for item in dataset.iterate_items():
    print(f"{item['title']}: {item['price']} PLN")
```

### cURL

```
curl -X POST "https://api.apify.com/v2/acts/automation-lab~allegro-scraper/runs?token=YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "searchQueries": ["laptop gaming"],
    "maxItemsPerQuery": 100,
    "sortBy": "price-asc"
  }'
```

## Use with AI agents via MCP

Allegro.pl Product Scraper is available as a tool for AI assistants that support the [Model Context Protocol (MCP)](https://docs.apify.com/platform/integrations/mcp).

Add the Apify MCP server to your AI client — this gives you access to all Apify actors, including this one:

### Setup for Claude Code

```
$claude mcp add --transport http apify "https://mcp.apify.com?tools=automation-lab/allegro-scraper"
```

### Setup for Claude Desktop, Cursor, or VS Code

Add this to your MCP config file:

```
{
    "mcpServers": {
        "apify": {
            "url": "https://mcp.apify.com?tools=automation-lab/allegro-scraper"
        }
    }
}
```

Your AI assistant will use OAuth to authenticate with your Apify account on first use.

### Example prompts

Once connected, try asking your AI assistant:

- "Use automation-lab/allegro-scraper to find the 50 cheapest new iPhone 15 listings on Allegro.pl and give me a price analysis"
- "Scrape 200 laptop products from Allegro.pl category for laptops, then identify the top 10 sellers by rating"
- "Get Allegro.pl gaming accessories priced between 50-300 PLN and export them to a spreadsheet"

Learn more in the [Apify MCP documentation](https://docs.apify.com/platform/integrations/mcp).

## Legality: Is It Legal to Scrape Allegro.pl?

Allegro.pl's product listings are publicly accessible to anyone browsing the web without authentication. This scraper only collects publicly visible data — the same information any visitor would see.

Web scraping public data is generally permissible under:

- The **CJEU Ryanair v. PR Aviation ruling** — public data scraping for legitimate business purposes is generally lawful
- **GDPR** — we collect only publicly visible product and seller data, not personal user information
- Standard **fair use principles** — data is used for analysis, not reproduction

We recommend:

- Using the data for legitimate business purposes (price research, market analysis)
- Not reproducing entire product listings verbatim without adding value
- Respecting Allegro's rate limits (built into the actor automatically)
- Reviewing [Allegro's Terms of Service](https://allegro.pl/regulaminy) for your specific use case

**This tool is provided for legitimate research and business intelligence use.** Apify's platform complies with ethical scraping standards and proxy rotation to minimize impact on target servers.

## FAQ

**How many products can I scrape from Allegro.pl?**
Allegro's search returns up to 100 pages × ~74 products = ~7,400 results per query. For comprehensive category coverage, use category URLs with `maxItemsPerQuery` set to 7400 or higher.

**How fast is the scraper?**
Each page takes approximately 15-30 seconds including browser startup. Rate: ~150-250 products per minute depending on query complexity.

**How much does it cost to scrape 10,000 Allegro products?**
At Free tier: ~$34.50. At Starter plan: ~$30.00. Higher-tier subscribers get volume discounts.

**Why are some products showing without a price?**
This typically means the listing has variable pricing (e.g., the price depends on selected variants like size/color). The `price` field shows the main price; check the product URL for full details.

**Why is the category field sometimes empty?**
Category information is derived from Allegro's internal category mapping. Some broad search queries may not associate products with a specific category path.

**Why do I get "Bot detection triggered" errors?**
This happens when Allegro's Cloudflare protection blocks the initial request. The actor automatically retries with session rotation — typically 2-3 retries are needed. If this happens frequently, try using fewer concurrent requests (already set to 1) or contact support.

**Can I scrape used items only?**
Yes! Set `condition` to `"used"` in the input. This applies the `stan=used` filter to Allegro's search.

**Why are some URLs redirecting through allegro.pl/events/clicks?**
The scraper automatically strips Allegro's tracking redirect wrappers to return clean, direct product URLs.

## Other e-commerce scrapers

Check out our other automation-lab scrapers for related platforms:

- 🛒 [Amazon Scraper](https://apify.com/automation-lab/amazon-scraper) — products, prices, reviews from Amazon
- 🏪 [eBay Scraper](https://apify.com/automation-lab/ebay-scraper) — listings from eBay marketplace
- 🎨 [Etsy Scraper](https://apify.com/automation-lab/etsy-scraper) — handmade products from Etsy
- 🏬 [Walmart Scraper](https://apify.com/automation-lab/walmart-scraper) — products from Walmart.com
- 🛍️ [Best Buy Scraper](https://apify.com/automation-lab/bestbuy-scraper) — electronics from Best Buy