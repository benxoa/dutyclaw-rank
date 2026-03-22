# HEARTBEAT.md – Rank (SEO Agent)

# Scheduled automation tasks that Rank runs periodically.
# Rank MUST notify the user via Telegram after every heartbeat run.

## Daily Tasks (run every morning at 7:00 AM user timezone)

- TASK: rank_tracker
  description: Check current SERP positions for all tracked keywords by scraping Google search results. Compare against previous day. Flag any keyword that moved up or down more than 3 positions. Send daily rank movement summary.

- TASK: indexing_check
  description: Spot-check that key pages are still indexed by Google (using site: search operator via Playwright). Alert immediately if any important page appears to have been deindexed.

## Weekly Tasks (run every Monday at 8:00 AM)

- TASK: full_seo_report
  description: Compile weekly SEO performance summary — rank movement trends, top gaining and losing keywords, pages that need attention, and 3 recommended actions for the week. Save report to /app/data/rank/reports/weekly/.

- TASK: competitor_keyword_gap
  description: Scrape top 3 competitor sites and identify keywords they rank for that the user's site does not. Score by opportunity (search volume vs competition). Deliver top 20 gap keywords with suggested content angles.

- TASK: backlink_monitor
  description: Check the site's backlink profile for new links gained and links lost in the past 7 days (via scraping or connected API). Alert if any high-value backlinks were lost.

- TASK: technical_seo_crawl
  description: Crawl the site for common technical issues — broken internal links, missing meta descriptions, duplicate title tags, missing alt text, redirect chains. Deliver prioritized fix list.

## Monthly Tasks (run on the 1st of each month)

- TASK: full_technical_audit
  description: Run a comprehensive technical SEO audit covering: crawlability, indexing, page speed, Core Web Vitals, schema markup, sitemap validity, robots.txt, canonicalization, and mobile usability. Generate full audit report with severity ratings.

- TASK: keyword_opportunity_scan
  description: Research 50 new keyword opportunities in the site's niche. Cluster by intent (informational, commercial, transactional). Score by difficulty and traffic potential. Deliver prioritized keyword roadmap for the next month.

## On-Demand Triggers (user can say any of these)

- "Research keywords for [topic]"
- "Write a content brief for [keyword]"
- "Audit [URL or site]"
- "Check my rankings for [keyword]"
- "What keywords is [competitor] ranking for?"
- "Find internal linking opportunities"
- "Check my page speed"
- "Generate a sitemap"
- "Find broken links on my site"
- "What's my keyword gap vs [competitor]?"
