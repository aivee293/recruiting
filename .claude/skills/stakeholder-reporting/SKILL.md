---
name: stakeholder-reporting
description: "Turn sourcing and pipeline data into stakeholder deliverables: weekly pipeline updates, hiring-manager reports, market-insight reports, talent-map presentations, and self-contained HTML dashboards. Use when the user wants to report progress or share findings. Not for post-close retrospectives (use hiring-quality)."
---

# Stakeholder Reporting for Recruiting Sourcing

## Purpose

Compile sourcing data, insights, and progress into structured reports and visual dashboards for hiring managers and leadership. Effective reporting transforms sourcing activity into clear, actionable narratives that build stakeholder confidence and drive hiring decisions.

## Report Types

### 1. Sourcing Pipeline Report

Regular update on sourcing progress for a specific role.

**Audience:** Hiring manager
**Frequency:** Weekly or bi-weekly
**Format:** Markdown summary + optional HTML dashboard

**Contents:**
- Candidates identified this period
- Outreach status and response rates
- Pipeline stage breakdown
- Key candidate highlights
- Blockers and recommendations

### 2. Market Insights Report

Research-driven report on the talent market for a role or function.

**Audience:** Hiring manager + leadership
**Frequency:** At search kickoff, updated monthly
**Format:** Markdown report + HTML dashboard with charts

**Contents:**
- Compensation landscape
- Talent supply & demand analysis
- Competitive landscape
- Hiring difficulty assessment
- Strategic recommendations

### 3. Talent Map Report

Visual representation of the talent landscape.

**Audience:** Hiring manager + leadership
**Frequency:** At search kickoff
**Format:** Markdown + HTML with interactive tables

**Contents:**
- Target company matrix (concentric circles)
- Pool size estimates by segment
- Geographic distribution
- Key individual highlights
- Recommended approach per segment

### 4. Search Retrospective

Post-search analysis of what worked and what didn't.

**Audience:** Recruiting team + hiring manager
**Frequency:** After role is filled
**Format:** Markdown report

**Contents:**
- Search timeline and milestones
- Channel effectiveness analysis
- Funnel conversion rates
- Lessons learned
- Recommendations for future searches

## Markdown Report Structure

### Standard Report Template

```markdown
# [Report Type]: [Role Title]
**Date:** [Date]  |  **Author:** [Name]  |  **Status:** [Active/Closed]

## Executive Summary
[3-5 bullet points with key findings and recommendations]

## [Section 1]
[Content with supporting data]

## [Section 2]
[Content with supporting data]

## Key Metrics
| Metric | Value | Trend |
|--------|-------|-------|
| [Metric 1] | [Value] | [↑/↓/→] |
| [Metric 2] | [Value] | [↑/↓/→] |

## Recommendations
1. [Actionable recommendation]
2. [Actionable recommendation]

## Next Steps
- [ ] [Action item with owner]
- [ ] [Action item with owner]
```

### Pipeline Metrics Table

```markdown
## Pipeline Overview

| Stage | Count | This Week | Conversion |
|-------|-------|-----------|------------|
| Identified | 45 | +12 | - |
| Contacted | 28 | +8 | 62% |
| Responded | 14 | +3 | 50% |
| Interested | 8 | +2 | 57% |
| Screened | 5 | +1 | 63% |
| Submitted to HM | 3 | +1 | 60% |
```

## HTML Dashboard Generation

For visual dashboards, generate standalone HTML files using Chart.js for charts. Dashboards should be self-contained (no external dependencies beyond CDN) and openable in any browser.

### Dashboard Template

Use the full template from `references/dashboard-templates.md`. It includes HTML structure, CSS, Chart.js setup, KPI cards, pipeline funnel, source channel doughnut, and candidate table with placeholder comments.

### Chart Types for Sourcing

**Pipeline funnel** - Horizontal bar chart showing conversion through stages
**Source effectiveness** - Pie or doughnut chart of candidates by source channel
**Timeline** - Line chart of pipeline growth over time
**Talent map** - Table with color-coded priority indicators
**Compensation** - Box plot or range chart for salary data

### Dashboard Best Practices

- Use **4-6 KPI cards** at the top (total identified, response rate, pipeline health, time-in-stage)
- Include **2-3 charts** maximum per dashboard
- Keep **one actionable table** (top candidates, target companies, or pipeline)
- Use consistent color scheme aligned with company brand
- Ensure all data has context (comparisons, benchmarks, trends)
- Include **last updated** timestamp prominently
- Make it printable (reasonable page breaks, no horizontal scroll)

## Report Writing Guidelines

### For Hiring Managers

- Lead with insights, not activity metrics
- Frame data around decisions they need to make
- Use comparisons: "This search is performing 20% above average response rate"
- Highlight blockers clearly with recommended solutions
- Keep reports scannable: bullets, tables, bold key numbers

### For Leadership

- Focus on strategic insights over tactical details
- Include market context (supply/demand, compensation trends)
- Frame recommendations in business terms
- Quantify trade-offs: "Expanding budget by €20K increases pool by 40%"
- Keep to one page / one screen when possible

### Data Integrity

- Always cite data sources
- Note data recency and limitations
- Distinguish between hard data and estimates
- Flag where sample sizes are small
- Use ranges rather than false precision

## File Organization

Store reports in the role-based directory structure:

```
roles/
└── senior-backend-engineer/
    └── reports/
        ├── pipeline-week-NN.md            ← e.g., pipeline-week-06.md
        ├── market-insights-YYYY-MM.md     ← e.g., market-insights-2026-02.md
        ├── dashboard.html                 ← updated in place
        └── retrospective.md
```

## Brand Guidelines

All branded reports and PDF-exportable deliverables MUST follow the QuoIntelligence brand guidelines. See `.claude/skills/stakeholder-reporting/references/brandguidelines.pdf` for the complete specification including:

- **60-30-10 color rule** — White (60%), QUO Sec Blue (30%), QUO Main Orange (10%)
- **Typography** — Inter font family at specified weights and sizes
- **Logo placement** — White logo on dark headers, dark logo on light footers
- **Print CSS** — Required `@media print` rules for browser-to-PDF export
- **CSS custom properties** — Standardized variables for all templates

### PDF Export Workflow (Automated — Puppeteer)

The preferred method uses a mechanical pipeline that avoids Chrome's default header/footer (which prints `file:///` URLs on every page):

**Pipeline: markdown → HTML body → branded HTML → Puppeteer PDF**

```bash
# Step 1: Strip any metadata lines (e.g., "Analyst:" prefix) from source markdown
sed '/^Analyst:/d' SOURCE.md > /tmp/market-clean.md

# Step 2: Convert markdown → HTML body fragment
npx marked --gfm /tmp/market-clean.md > /tmp/market-body.html

# Step 3: Build branded HTML wrapper (see references/market-insights-template.md)
#   - Base64-encode logos from .claude/assets/PNG/
#   - Inject body HTML into branded template with CSS, charts, print styles
#   - Charts use hidden divs + DOMContentLoaded JS to relocate inline
bash /tmp/build-branded.sh   # outputs /tmp/market-branded.html

# Step 4: Generate PDF with Puppeteer (no URL footer)
node /tmp/print-pdf.mjs
```

**Puppeteer script** (`print-pdf.mjs`):

```javascript
import puppeteer from 'puppeteer';
const browser = await puppeteer.launch({
    headless: true,
    executablePath: '/usr/bin/google-chrome-stable',
    args: ['--no-sandbox', '--disable-gpu', '--disable-setuid-sandbox']
});
const page = await browser.newPage();
await page.goto('file:///tmp/market-branded.html', { waitUntil: 'networkidle0', timeout: 30000 });
await page.pdf({
    path: 'roles/[role-name]/reports/market-insights-YYYY-MM.pdf',
    format: 'A4',
    printBackground: true,
    displayHeaderFooter: false,
    margin: { top: '10mm', bottom: '10mm', left: '0', right: '0' }
});
await browser.close();
```

**Key details:**
- `displayHeaderFooter: false` — suppresses Chrome's default URL/date footer on every page
- `printBackground: true` — required for brand colors (blue header, table headers, chart cards)
- Logos are base64-embedded in the HTML for self-contained output
- Charts use Chart.js loaded from CDN; hidden initially then repositioned via DOM relocation
- The Puppeteer script must run from a directory where `puppeteer` is installed as a Node module

**Chart DOM relocation technique:** Charts are placed as hidden `<div>` blocks after the `</div>` closing the content body. A `DOMContentLoaded` script scans `<h3>` headings for section numbers (e.g., "1.4", "3.2") and uses `insertBefore()` to move the chart blocks to their contextually correct positions. This keeps the markdown→HTML conversion mechanical while placing charts inline.

**Why not `--print-to-pdf-no-header`?** Chrome's CLI flag does not reliably suppress the source URL footer in Chrome 133+. Puppeteer's `displayHeaderFooter: false` is the correct solution.

### PDF Export Workflow (Manual Fallback)

If Puppeteer is unavailable:

1. Generate the HTML report using the branded template
2. Open in browser and verify layout
3. Print to PDF: Ctrl+P / Cmd+P, Save as PDF, **Background graphics: ON**
4. Save to `roles/[role-name]/reports/`

## Additional Resources

### Reference Files

You are **strongly encouraged** to read the reference files

- **`references/brandguidelines.pdf`** - your brand guidelines
- **`references/market-insights-template.md`** - Branded HTML template for market insights reports (PDF-ready)
- **`references/dashboard-templates.md`** - Complete HTML dashboard templates for pipeline dashboards
- **`references/chart-examples.md`** - Chart.js code snippets for common sourcing visualizations
