# Agent: RANK

**Description:**
RANK is an SEO automation agent — handling keyword research, on-page optimization, content briefs, backlink monitoring, competitor ranking analysis, and technical SEO audits so your site climbs and stays at the top.

**Type:** automation
**Enabled:** true

## Capabilities
- web_browsing
- keyword_research
- serp_analysis
- content_brief_generation
- on_page_seo_audit
- backlink_monitoring
- competitor_ranking_tracking
- technical_seo_audit
- internal_linking_suggestions
- rank_tracking
- sitemap_analysis
- page_speed_analysis
- telegram_notifications
- task_scheduling
- data_scraping

## Default Personality
PERSONALITY.md

## Settings
- maxConcurrentTasks: 2
- enableBrowser: true
- browserProfile: rank
- headlessBrowser: true
- logLevel: info

## Integrations

### Telegram
- enabled: true
- botToken: `${TELEGRAM_BOT_TOKEN_DUTYCLAW}`
- note: Required for rank change alerts and weekly SEO reports

### Google Search Console
- enabled: false
- note: Optional — connect to pull real click, impression, and ranking data
- siteUrl: `${GSC_SITE_URL}`
- credentialsFile: `${GSC_CREDENTIALS_JSON_PATH}`

### SerpAPI
- enabled: false
- note: Optional — for structured SERP data without manual scraping
- apiKey: `${SERPAPI_API_KEY}`

### Ahrefs
- enabled: false
- note: Optional — for backlink data and keyword difficulty scores
- apiKey: `${AHREFS_API_KEY}`

### SEMrush
- enabled: false
- note: Optional — for keyword research and competitor gap analysis
- apiKey: `${SEMRUSH_API_KEY}`

### Google PageSpeed Insights
- enabled: false
- note: Optional — for Core Web Vitals and page speed data
- apiKey: `${PAGESPEED_API_KEY}`

## Watchlist
- note: Add your site and competitor sites here for continuous monitoring
- targetSite: ""
- competitorSites: []
- trackedKeywords: []

## Browser Settings
- args:
  - --disable-dev-shm-usage
  - --disable-gpu
  - --single-process
  - --disable-background-networking
  - --disable-extensions
  - --disable-software-rasterizer
- maxConcurrentBrowsers: 1

## Data Paths
- keywords: /app/data/rank/keywords/
- audits: /app/data/rank/audits/
- reports: /app/data/rank/reports/
- competitors: /app/data/rank/competitors/
- backlinks: /app/data/rank/backlinks/
