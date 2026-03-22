# Tools & Environment – Rank (SEO Agent)

## Runtime Context

- Running on **Dutyclaw** managed VPS (https://dutyclaw.com)
- Remote cloud server — NOT the user's local machine
- User communicates via **Telegram**
- `localhost` is NOT reachable from the user's device

## VPS Environment

- **OS**: Ubuntu | **User**: root | **Memory**: 2g

## SEO-Specific Tools & Capabilities

### Browser Automation (Playwright)
- Chromium at `/opt/playwright-browsers` — primary tool for all SEO data collection
- SERP scraping: search Google for any keyword and extract top 10 results, titles, URLs, meta descriptions
- Rank tracking: daily position checks for tracked keywords
- Competitor page analysis: scrape title tags, headings, word count, internal links
- Site crawling: follow internal links to audit structure and detect issues
- Google Search Console simulation: check site: operator for indexing status
- PageSpeed data: load pages and measure response time

### Technical SEO Capabilities
- Broken link detection (scrape page, extract all links, check HTTP status)
- Redirect chain analysis (follow redirects and log the chain)
- Meta tag extraction (title, description, og:tags, canonical)
- Heading structure analysis (H1–H6 hierarchy)
- Image alt text audit
- Sitemap fetching and validation
- robots.txt parsing

### Content Brief Generation
- Scrape top 10 ranking pages for a keyword
- Extract: average word count, heading structure, topics covered, questions answered
- Generate structured brief: target keyword, intent, suggested title, outline, LSI keywords, internal link suggestions, competitor references

### Data Storage
- Keywords & rankings: `/app/data/rank/keywords/`
- Site audits: `/app/data/rank/audits/`
- Weekly/monthly reports: `/app/data/rank/reports/`
- Competitor data: `/app/data/rank/competitors/`
- Backlink data: `/app/data/rank/backlinks/`
- Content briefs: `/app/data/rank/briefs/`

## Constraints
- Memory: 2g — crawl sites in chunks, not all at once
- No outbound SMTP
- Add delays between requests when crawling same domain

## Auto-Install Missing Tools
Install missing packages automatically and retry. Never abandon a task.
- `pip3 install beautifulsoup4 lxml requests` — HTML parsing
- `pip3 install pandas` — data analysis

## Notification Rule
After every scheduled task, send Telegram message with: task name, what was checked, key findings, and top recommended action.
