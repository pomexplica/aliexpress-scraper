# AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K

Turn any AliExpress search into a clean table: price, original price, discount, **exact units sold**, rating, store, shipping and delivery dates, images and rank, in the country and currency you choose.

**[Run it on Apify](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)**: no install, no login, free credit on a new Apify account.

## What you get

For every product in the results:

- **Identity:** product ID, link, title, main image and the image gallery shown on the card.
- **Price:** current price, original (struck-through) price, discount %, currency and the price text as shown.
- **Demand:** exact units sold (`sold: 60710`, not just "60K+ sold"), the text AliExpress shows, and the star rating.
- **Seller:** store name, when AliExpress puts it on the search card (mostly on sponsored results and outside the US).
- **Delivery:** free-shipping flag, delivery window in days and the estimated delivery dates for your country.
- **Context:** rank in the search, page, keyword, total results AliExpress reports for the keyword, Choice badge, sponsored (ad) flag, selling points, category IDs and the listing date.

## Pricing

**No login, no cookies, no API key. You pay only for what is delivered: $0.001 per product ($1 per 1,000).** Failed or empty searches are never charged.

That is the free-plan price; Apify paid plans (Bronze, Silver, Gold) pay less per item.

## Call it by API

```bash
curl -X POST "https://api.apify.com/v2/acts/pomlabs~aliexpress-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"keywords": ["wireless earbuds"]}'
```

Python:

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("pomlabs/aliexpress-scraper").call(run_input={"keywords": ["wireless earbuds"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Use it from Claude, Cursor or any MCP client

```bash
claude mcp add aliexpress "https://mcp.apify.com?tools=pomlabs/aliexpress-scraper" -t http
```

## Ready-made examples

- [AliExpress best selling products 2026, by units sold](https://apify.com/pomlabs/aliexpress-scraper/examples/aliexpress-best-selling-products)
- [Track AliExpress prices for a keyword](https://apify.com/pomlabs/aliexpress-scraper/examples/aliexpress-price-tracker)
- [AliExpress products in Brazil with prices in BRL](https://apify.com/pomlabs/aliexpress-scraper/examples/aliexpress-products-brazil-brl)

## More Actors by Pom Labs

- [YouTube Transcript Scraper: Translate, No Login · $3/1K](https://apify.com/pomlabs/youtube-transcript-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [Reddit Scraper: Deleted & Removed, Mods, Hidden Profiles](https://apify.com/pomlabs/reddit-posts-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [LinkedIn Company Scraper (No Cookies): Posts, Similar Companies](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [Instagram Profile Scraper: Exact Followers, Reels Views](https://apify.com/pomlabs/instagram-profile-data?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [LinkedIn Profile Scraper (No Cookies) + Similar Profiles](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [Threads Scraper: Keyword Search, Posts & Profiles · No Login](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [AI Brand Visibility Tracker - ChatGPT, Claude & Perplexity](https://apify.com/pomlabs/ai-brand-visibility?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [Mercado Livre & Amazon BR Coupon Code Checker](https://apify.com/pomlabs/mercadolivre-coupon-checker?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [Page Time Machine · Wayback Diff + AI · No Login · $2.5/1K](https://apify.com/pomlabs/page-time-machine?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [Video Downloader: TikTok No Watermark, Instagram, YouTube, X](https://apify.com/pomlabs/video-downloader?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [NSFW Image Detector & Image Tagger - Moderation + Categories](https://apify.com/pomlabs/image-moderation-tagger?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)
- [Google Trends Scraper: Related Queries, No 429 · $2/1K](https://apify.com/pomlabs/google-trends-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper)

Full documentation, input fields and output format: [AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K on Apify](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=aliexpress-scraper).
