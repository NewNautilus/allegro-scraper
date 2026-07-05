[Allegro Scraper](https://apify.com/studio-amba/allegro-scraper?fpr=data)

# Allegro Scraper

Scrape **product listings, prices, seller data, and reviews** from [Allegro.pl](https://allegro.pl) — Poland's largest e-commerce marketplace with 21M+ active users. No login or cookies required.

## What does Allegro Scraper do?

This actor extracts structured product data from Allegro.pl search results and category pages. Get product names, prices in PLN, original prices, discounts, seller information, ratings, delivery options, and product condition (new/used) — all in a clean JSON format ready for analysis.

Run it on the **Apify platform** to leverage automatic proxy rotation, scheduling, API access, and integrations with Google Sheets, Slack, Zapier, and more.

## Why use Allegro Scraper?

- **Price monitoring** — Track competitor prices and discover deals on Poland's biggest marketplace
- **Market research** — Analyze product categories, pricing trends, and seller competition on Allegro
- **E-commerce intelligence** — Monitor product availability, discounts, and seller ratings at scale
- **Lead generation** — Find and analyze top sellers in any product category

## How to use Allegro Scraper

1. Click **Try for free** to open the actor in Apify Console
2. Enter a **search query** (e.g., "laptop") or paste an **Allegro category URL**
3. Optionally set price filters, condition (new/used), and sort order
4. Click **Start** and wait for the run to finish
5. Download your data as JSON, CSV, Excel, or connect via API

## Input

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `query` | String | No | Search for products by keyword (default: "laptop") |
| `category` | String | No | Direct Allegro category URL (overrides search query) |
| `minPrice` | Integer | No | Minimum price filter in PLN |
| `maxPrice` | Integer | No | Maximum price filter in PLN |
| `condition` | String | No | Filter: `all`, `new`, or `used` (default: all) |
| `sortBy` | String | No | Sort: `relevance`, `price_asc`, `price_desc`, `newest`, `popularity` |
| `maxResults` | Integer | No | Maximum results to return (default: 100) |
| `proxyConfiguration` | Object | No | Proxy settings — **residential proxies strongly recommended** |

## Output

Each result contains:

| Field | Type | Example |
| --- | --- | --- |
| `name` | String | `"Lenovo ThinkPad T14 Gen 5 14\" i7-1355U 16GB 512GB"` |
| `brand` | String | `"Lenovo"` |
| `price` | Number | `3499.00` |
| `currency` | String | `"PLN"` |
| `originalPrice` | Number | `4299.00` |
| `discount` | String | `"-19%"` |
| `rating` | Number | `4.8` |
| `reviewCount` | Number | `56` |
| `sellerName` | String | `"TechStore_PL"` |
| `sellerRating` | String | `"Super Sprzedawca"` |
| `freeDelivery` | Boolean | `true` |
| `condition` | String | `"new"` |
| `imageUrl` | String | Product image URL |
| `url` | String | Full Allegro offer URL |
| `scrapedAt` | String | ISO 8601 timestamp |

## Example output

```
{
    "name": "Lenovo ThinkPad T14 Gen 5 14\" i7-1355U 16GB 512GB SSD",
    "brand": "Lenovo",
    "price": 3499.00,
    "currency": "PLN",
    "originalPrice": 4299.00,
    "discount": "-19%",
    "rating": 4.8,
    "reviewCount": 56,
    "sellerName": "TechStore_PL",
    "sellerRating": "Super Sprzedawca",
    "freeDelivery": true,
    "condition": "new",
    "imageUrl": "https://a.allegroimg.com/original/...",
    "url": "https://allegro.pl/oferta/lenovo-thinkpad-t14-gen-5-...",
    "scrapedAt": "2026-04-06T12:00:00.000Z"
}
```

You can download the dataset in various formats such as JSON, HTML, CSV, or Excel.

## Cost estimate

This actor uses Playwright (browser-based) due to Allegro's anti-bot protection. Estimated cost:

- ~**0.5 compute units per 100 results** with residential proxies
- Approximately **$2-5 per 1,000 products** depending on proxy usage

## Tips

- **Use residential proxies** — Allegro uses DataDome anti-bot protection. Residential proxies significantly improve success rates.
- **Start small** — Test with `maxResults: 10` first to verify the scraper works with your proxy setup.
- **Use category URLs** — For targeted scraping, paste a specific Allegro category URL instead of using search.
- **Schedule runs** — Set up daily or weekly runs to track price changes over time.

## Limitations

- Allegro.pl uses DataDome anti-bot protection — residential proxies are required for reliable scraping
- Some product details (full specs, description) are only available on individual product pages
- Data is scraped from the public website and may change without notice
- This actor scrapes listing pages for speed; for detailed product data, consider scraping individual offer pages

## FAQ

**Is it legal to scrape Allegro?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible product listings. Always review Allegro's terms of service and use the data responsibly.

**Why do I need residential proxies?**
Allegro uses DataDome, a sophisticated anti-bot service. Datacenter proxies are typically blocked. Residential proxies mimic real user traffic and provide much higher success rates.

**Can I scrape specific categories?**
Yes! Paste any Allegro category URL (e.g., `https://allegro.pl/kategoria/laptopy-491`) into the `category` input field.

Have feedback or issues? Open an issue in the [Issues tab](https://console.apify.com/actors) or contact us for a custom solution.