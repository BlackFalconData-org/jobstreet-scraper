# JobStreet Scraper

Extract structured data from [my.jobstreet.com](https://my.jobstreet.com) — job listings from JobStreet (my.jobstreet.com, sg.jobstreet.com, id.jobstreet.com, ph.jobstreet.com). Get title, company, salary, location, description, and company profiles.

**[JobStreet Scraper â€” MY, SG, ID & PH Job Listings on Apify →](https://apify.com/blackfalcondata/jobstreet-scraper)**

---

## Key features




**Search with filters** — Search by keyword and location. Filter by country, sort mode, and more.

**Detail enrichment** — Fetch full job descriptions, salary data, employer profiles, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

---

## Use cases




**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from jobstreet.com on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from jobstreet.com.

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

---

## Related products by Black Falcon Data




- [StepStone Scraper](https://github.com/BlackFalconData-org/stepstone-scraper) — Job listings from 18 European portals
- [Indeed Job Scraper](https://github.com/BlackFalconData-org/indeed-job-scraper) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://github.com/BlackFalconData-org/glassdoor-job-scraper) — Glassdoor listings with company ratings

---

*Last updated: 2026 03*
