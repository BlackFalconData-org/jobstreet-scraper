# JobStreet Scraper

Extract structured data from [my.jobstreet.com](https://my.jobstreet.com) — job listings from JobStreet (my.jobstreet.com, sg.jobstreet.com, id.jobstreet.com, ph.jobstreet.com). Get title, company, salary, location, description, and company profiles.

**[JobStreet Scraper on Apify →](https://apify.com/blackfalcondata/jobstreet-scraper?fpr=1h3gvi)**


## 🚀 How to use this actor

> ### 💚 $5 free Apify credits — every month
> No credit card required. No commitment. Cancel anytime.

### 👉 [Sign up free on Apify →](https://console.apify.com/sign-up?fpr=1h3gvi)

1. **Click sign up** — pick GitHub, Google, or email; takes ~30 seconds
2. **Open this actor** — input is pre-filled with a working example
3. **Click Start** — export results as JSON, CSV, or Excel

Your **$5 monthly platform credit** is enough to run this actor right away — and again every month — scraping typically several hundred to several thousand results per run, depending on your input.



## 🚀 How to use this actor

> ### 💚 $5 free Apify credits — every month
> No credit card required. No commitment. Cancel anytime.

### 👉 [Sign up free on Apify →](https://console.apify.com/sign-up?fpr=1h3gvi)

1. **Click sign up** — pick GitHub, Google, or email; takes ~30 seconds
2. **Open this actor** — input is pre-filled with a working example
3. **Click Start** — export results as JSON, CSV, or Excel

Your **$5 monthly platform credit** is enough to run this actor right away — and again every month — scraping typically several hundred to several thousand results per run, depending on your input.


---

## Key features








**Search with filters** — Search by keyword and location. Filter by 🌍 country, sort by, date range, and more.

**Detail enrichment** — Fetch full job descriptions, salary data, employer profiles, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

**Change classification** — Track unchanged, expired, cross-run repost detection across runs. Build audit trails of how listings evolve over time.

**Compact output** — Emit core fields only (AI-agent / MCP-friendly). Keeps response size small for LLM workflows.

**Description truncation** — Cap description length per listing to control output size and cost.

**Result cap** — Stop after N listings (up to 1.000). Set to 0 for the full catalog.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases








**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from jobstreet.com on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from jobstreet.com.

**Change monitoring**
Run daily or hourly in incremental mode to capture only new, updated, or expired listings. Perfect for price-tracking, churn analysis, and alerting pipelines.

**Compensation benchmarking**
Aggregate salary ranges across roles, industries, and locations on jobstreet.com to inform pricing decisions, hiring plans, or candidate negotiations.

**Lead generation**
Extract employer contact details alongside listings to build outreach lists for recruiters, staffing agencies, or B2B sales teams.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

---

## Quick start

```json
{
  "query": "software engineer",
  "maxResults": 50,
  "includeDetails": true
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `query` | string | — | Job search keywords. Use JSON array for multi-query. |
| `country` | enum | `"MY"` | Which JobStreet market to search. |
| `location` | string | — | City, state, or region. Use JSON array for multi-location. |
| `startUrls` | array | — | Direct search or job detail URLs. |
| `maxResults` | integer | `25` | Maximum total job listings to return (0 = unlimited). |
| `maxPages` | integer | `5` | Maximum SERP pages to scrape per search source. |
| `sortMode` | enum | — | Sort results by relevance or date. |
| `dateRange` | string | — | Filter jobs posted within a time range (e.g. '1', '3', '7', '14', '31'). |
| `workType` | string | — | Filter by work type code (e.g. '242' for Full Time on JobStreet). |
| `workArrangement` | string | — | Filter by work arrangement code (e.g. '2' for Remote). |
| `includeDetails` | boolean | `true` | Fetch each job's detail page for full description, salary data, and company info. |
| `descriptionMaxLength` | integer | `0` | Truncate description to this many characters. 0 = no truncation. |
| `compact` | boolean | `false` | Output only core fields (for AI-agent/MCP workflows). |
| `incrementalMode` | boolean | `false` | Compare against previous run state. Requires stateKey. |
| `stateKey` | string | — | Stable identifier for the tracked search universe (e.g. "my-software-kl"). |
| `emitUnchanged` | boolean | `false` | When incremental, also emit records that haven't changed. |
| `emitExpired` | boolean | `false` | When incremental, also emit records no longer found. |

---

## FAQ

<!-- WRITE: 4-6 Q&A pairs relevant to this product -->

**Is it legal to scrape my.jobstreet.com?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible information. Always check the target site's terms of service for your specific use case.

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage.

---

## Known limitations

<!-- WRITE: 4-6 honest limitations -->

- <!-- WRITE: limitation 1 -->
- <!-- WRITE: limitation 2 -->


## Output fields

Every listing returns the same 58-field schema. Missing values are `null` — never omitted.

- `jobId`
- `seekJobId`
- `title`
- `canonicalUrl`
- `company`
- `companyUrl`
- `advertiserId`
- `location`
- `locationCountry`
- `locationState`
- `locationSuburb`
- `locationPostcode`
- `salaryText`
- `salaryMin`
- `salaryMax`
- `salaryCurrency`
- `salaryType`
- `employmentType`
- `workArrangement`
- `category`
- `subCategory`
- `roleId`
- `teaser`
- `bulletPoints`
- `description`
- `descriptionHtml`
- `descriptionMarkdown`
- `descriptionLength`
- `contentQuality`
- `companyIndustry`
- `companySize`
- `companyWebsite`
- `phoneNumber`
- `screeningQuestions`
- `applyUrl`
- `postedDate`
- `validThrough`
- `contentHash`
- `isSponsored`
- `sourceUrl`
- `sourceCountry`
- `sourceDomain`
- `searchQuery`
- `searchUrl`
- `scrapedAt`
- `fetchedAt`
- `detailFetched`
- `extractedEmails`
- `changeType`
- `trackedHash`
- `firstSeenAt`
- `lastSeenAt`
- `previousSeenAt`
- `expiredAt`
- `stateKey`
- `isRepost`
- `repostOfId`
- `repostDetectedAt`


## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "jobId": "485469726b257aa48bceebec68c9213bdf9a52e7ba3595af9158237164ad24c0",
  "seekJobId": "91247023",
  "title": "Associate Software Engineer (0-2 years)",
  "canonicalUrl": "https://my.jobstreet.com/job/91247023",
  "company": "Software International Corporation (M) Sdn Bhd",
  "companyUrl": "https://my.jobstreet.com/companies/software-international-corporation-168553406415897",
  "advertiserId": "60627682",
  "location": "Kuala Lumpur, Malaysia",
  "locationCountry": "MY",
  "locationState": "Kuala Lumpur",
  "locationSuburb": null,
  "locationPostcode": null
}
```

*Truncated — full records contain 58 fields. See Output fields for the complete schema.*


**[Try JobStreet Scraper now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/jobstreet-scraper?fpr=1h3gvi)**


## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.01 |
| Result | $0.002 |

See the [actor on Apify](https://apify.com/blackfalcondata/jobstreet-scraper?fpr=1h3gvi) for current pricing.

---

## Related products by Black Falcon Data








- [StepStone Scraper](https://apify.com/blackfalcondata/stepstone-scraper?fpr=1h3gvi) — Job listings from 18 European portals
- [Indeed Job Scraper](https://apify.com/blackfalcondata/indeed-job-scraper?fpr=1h3gvi) — Indeed job listings with salary data
- [LinkedIn Jobs Scraper](https://apify.com/blackfalcondata/linkedin-jobs-scraper?fpr=1h3gvi) — World's largest professional network — global job listings, no login required
- [Glassdoor Job Scraper](https://apify.com/blackfalcondata/glassdoor-job-scraper?fpr=1h3gvi) — Glassdoor listings with company ratings
- [Arbeitsagentur Scraper](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Germany's official job portal (1M+ listings)
- [SEEK Scraper](https://apify.com/blackfalcondata/seek-scraper?fpr=1h3gvi) — Australia & NZ's largest job board

---


## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. [Sign up free](https://console.apify.com/sign-up?fpr=1h3gvi) — $5 credit included
2. Open the actor and paste your input
3. Click Start — results download as JSON, CSV, or Excel

Need more volume? [See pricing](https://apify.com/pricing?fpr=1h3gvi).

---

---

*Last updated: 2026 03*
