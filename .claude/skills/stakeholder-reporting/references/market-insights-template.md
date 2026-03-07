# Branded Market Insights HTML Template

## Overview

Self-contained HTML template for market insights reports with "Your Company Name" brand guidelines applied. Designed for browser-to-PDF export via Ctrl+P / Cmd+P with "Background graphics: ON".

**Brand compliance:** Follows `.claude/skills/stakeholder-reporting/references/brand-guidelines.md`

## Usage

1. Copy the full HTML below
2. Replace all `<!-- PLACEHOLDER -->` comments with actual data
3. Populate Chart.js data arrays with numbers
4. Open in browser, verify layout
5. Print to PDF (Ctrl+P, Save as PDF, Background graphics ON)
6. Save PDF to `roles/[role-name]/reports/`

## Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title><!-- REPORT_TITLE --> - Market Insights</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        /* === CSS Custom Properties (from brand-guidelines.md) === */
        :root {
            --main: #D8512B;
            --sec: #2C3085;
            --white: #F7FEFE;
            --light-grey: #DFE3E7;
            --dark-grey: #333333;
            --black: #0D090F;
            /* Functional status colors (not in brand palette — extended for data visualization) */
            --color-success: #10b981;
            --color-warning: #f59e0b;
            --color-danger: #ef4444;
            --font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif;
            --spacing-sm: 8px;
            --spacing-md: 16px;
            --spacing-lg: 24px;
            --spacing-xl: 32px;
            --radius-sm: 6px;
            --radius-md: 12px;
            --radius-lg: 16px;
        }

        /* === Reset & Base === */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: var(--font-family);
            background: var(--light-grey);
            color: var(--dark-grey);
            font-size: 14px;
            line-height: 1.6;
            padding: var(--spacing-lg);
        }
        .container {
            max-width: 1100px;
            margin: 0 auto;
        }

        /* === Header === */
        .header {
            background: var(--sec);
            color: var(--white);
            padding: var(--spacing-xl) var(--spacing-xl) var(--spacing-lg);
            border-radius: var(--radius-lg) var(--radius-lg) 0 0;
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
        }
        .header-content { flex: 1; }
        .header-logo {
            height: 32px;
            margin-bottom: var(--spacing-md);
        }
        .header h1 {
            font-size: 28px;
            font-weight: 700;
            color: var(--white);
            margin-bottom: 4px;
            line-height: 1.2;
        }
        .header .subtitle {
            font-size: 14px;
            opacity: 0.8;
            font-weight: 400;
        }
        .header .meta {
            font-size: 12px;
            opacity: 0.65;
            margin-top: var(--spacing-sm);
        }
        .difficulty-badge {
            display: inline-block;
            padding: 6px 16px;
            border-radius: 20px;
            font-size: 13px;
            font-weight: 600;
            margin-top: var(--spacing-md);
        }
        .difficulty-high { background: var(--color-danger); color: white; }
        .difficulty-medium { background: var(--color-warning); color: white; }
        .difficulty-low { background: var(--color-success); color: white; }
        .difficulty-very-high { background: #991b1b; color: white; }

        /* === Content Body (60% White) === */
        .content-body {
            background: var(--white);
            padding: var(--spacing-xl);
            border-radius: 0 0 var(--radius-lg) var(--radius-lg);
        }

        /* === Executive Summary === */
        .exec-summary {
            background: rgba(44, 48, 133, 0.04);
            border-left: 4px solid var(--sec);
            padding: var(--spacing-lg);
            border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
            margin-bottom: var(--spacing-xl);
        }
        .exec-summary h2 {
            font-size: 16px;
            font-weight: 600;
            color: var(--sec);
            margin-bottom: var(--spacing-sm);
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }
        .exec-summary ul {
            list-style: none;
            padding: 0;
        }
        .exec-summary li {
            padding: 4px 0;
            padding-left: 20px;
            position: relative;
        }
        .exec-summary li::before {
            content: '';
            position: absolute;
            left: 0;
            top: 12px;
            width: 8px;
            height: 8px;
            background: var(--main);
            border-radius: 2px;
        }

        /* === KPI Grid === */
        .kpi-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: var(--spacing-md);
            margin-bottom: var(--spacing-xl);
        }
        .kpi-card {
            background: white;
            border-radius: var(--radius-md);
            padding: var(--spacing-lg);
            border: 1px solid var(--light-grey);
            border-left: 4px solid var(--sec);
        }
        .kpi-value {
            font-size: 36px;
            font-weight: 700;
            color: var(--main);
            line-height: 1.1;
        }
        .kpi-label {
            font-size: 11px;
            color: #6b7280;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            margin-top: 4px;
            font-weight: 500;
        }
        .kpi-detail {
            font-size: 12px;
            color: var(--dark-grey);
            margin-top: var(--spacing-sm);
        }

        /* === Section Headers === */
        .section {
            margin-bottom: var(--spacing-xl);
        }
        .section h2 {
            font-size: 20px;
            font-weight: 600;
            color: var(--sec);
            margin-bottom: var(--spacing-md);
            padding-bottom: var(--spacing-sm);
            border-bottom: 2px solid var(--light-grey);
        }
        .section h3 {
            font-size: 16px;
            font-weight: 600;
            color: var(--dark-grey);
            margin-bottom: var(--spacing-sm);
            margin-top: var(--spacing-md);
        }
        .section p {
            margin-bottom: var(--spacing-sm);
        }

        /* === Tables === */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: var(--spacing-md);
            font-size: 13px;
        }
        thead th {
            background: var(--sec);
            color: var(--white);
            font-size: 12px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.04em;
            text-align: left;
            padding: 12px var(--spacing-md);
        }
        thead th:first-child { border-radius: var(--radius-sm) 0 0 0; }
        thead th:last-child { border-radius: 0 var(--radius-sm) 0 0; }
        tbody td {
            padding: 10px var(--spacing-md);
            border-bottom: 1px solid var(--light-grey);
        }
        tbody tr:nth-child(even) { background: rgba(223, 227, 231, 0.3); }
        tbody tr:hover td { background: rgba(216, 81, 43, 0.04); }

        /* === Charts === */
        .grid-2 {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: var(--spacing-lg);
            margin-bottom: var(--spacing-xl);
        }
        .card {
            background: white;
            border-radius: var(--radius-md);
            padding: var(--spacing-lg);
            border: 1px solid var(--light-grey);
        }
        .card h3 {
            font-size: 14px;
            font-weight: 600;
            color: var(--sec);
            margin-bottom: var(--spacing-md);
            padding-bottom: var(--spacing-sm);
            border-bottom: 1px solid var(--light-grey);
        }
        .chart-container {
            position: relative;
            height: 280px;
        }

        /* === Badges === */
        .badge {
            display: inline-block;
            padding: 3px 10px;
            border-radius: 12px;
            font-size: 11px;
            font-weight: 600;
        }
        .badge-high { background: #fee2e2; color: #991b1b; }
        .badge-medium { background: #fef3c7; color: #92400e; }
        .badge-low { background: #d1fae5; color: #065f46; }
        .badge-info { background: #dbeafe; color: #1e40af; }

        /* === Callout box === */
        .callout {
            background: rgba(216, 81, 43, 0.06);
            border-left: 4px solid var(--main);
            padding: var(--spacing-md) var(--spacing-lg);
            border-radius: 0 var(--radius-sm) var(--radius-sm) 0;
            margin: var(--spacing-md) 0;
            font-size: 13px;
        }
        .callout strong { color: var(--main); }

        /* === Recommendations list === */
        .recommendations {
            counter-reset: rec;
            list-style: none;
            padding: 0;
        }
        .recommendations li {
            counter-increment: rec;
            padding: var(--spacing-sm) 0 var(--spacing-sm) 36px;
            position: relative;
            border-bottom: 1px solid var(--light-grey);
        }
        .recommendations li:last-child { border-bottom: none; }
        .recommendations li::before {
            content: counter(rec);
            position: absolute;
            left: 0;
            top: var(--spacing-sm);
            width: 24px;
            height: 24px;
            background: var(--sec);
            color: white;
            border-radius: 50%;
            font-size: 12px;
            font-weight: 700;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* === Footer === */
        .footer {
            text-align: center;
            padding: var(--spacing-lg) var(--spacing-md);
            color: #9ca3af;
            font-size: 11px;
            border-top: 1px solid var(--light-grey);
            margin-top: var(--spacing-xl);
        }
        .footer-logo {
            height: 20px;
            margin-bottom: var(--spacing-sm);
            opacity: 0.7;
        }

        /* === Source citation === */
        .source-note {
            font-size: 11px;
            color: #9ca3af;
            font-style: italic;
            margin-top: 4px;
        }

        /* === Responsive === */
        @media (max-width: 768px) {
            .grid-2 { grid-template-columns: 1fr; }
            .header { flex-direction: column; }
        }

        /* === Print / PDF Export === */
        @media print {
            body {
                padding: 0;
                background: white;
                font-size: 12px;
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
            }
            .container { max-width: 100%; }
            .header {
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
                border-radius: 0;
            }
            .content-body {
                border-radius: 0;
                padding: var(--spacing-lg);
            }
            .card, .kpi-card {
                box-shadow: none;
                border: 1px solid var(--light-grey);
                page-break-inside: avoid;
            }
            .section {
                page-break-inside: avoid;
            }
            table {
                page-break-inside: auto;
            }
            tr {
                page-break-inside: avoid;
            }
            thead {
                display: table-header-group;
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
            }
            .page-break {
                page-break-before: always;
            }
            .no-print {
                display: none !important;
            }
        }
    </style>
</head>
<body>
<div class="container">

    <!-- ============ HEADER ============ -->
    <div class="header">
        <div class="header-content">
            <img src="x.png" alt="x" class="header-logo">

            <h1><!-- REPORT_TITLE --></h1>
            <div class="subtitle"><!-- REPORT_SUBTITLE e.g. "job title" --></div>
            <div class="meta">
                <!-- DATE --> &bull; <!-- AUTHOR --> &bull; <!-- SOURCES_SUMMARY -->
            </div>
            <div class="difficulty-badge difficulty-high">
                <!-- DIFFICULTY_RATING e.g. "Hiring Difficulty: High (3.4/5)" -->
            </div>
        </div>
    </div>

    <!-- ============ CONTENT ============ -->
    <div class="content-body">

        <!-- Executive Summary -->
        <div class="exec-summary">
            <h2>Executive Summary</h2>
            <ul>
                <li><!-- FINDING_1 --></li>
                <li><!-- FINDING_2 --></li>
                <li><!-- FINDING_3 --></li>
                <li><!-- FINDING_4 --></li>
            </ul>
            <div class="callout" style="margin-top: 16px;">
                <strong>Recommendation:</strong> <!-- TOP_LINE_RECOMMENDATION -->
            </div>
        </div>

        <!-- KPI Cards -->
        <div class="kpi-grid">
            <div class="kpi-card">
                <div class="kpi-value"><!-- TALENT_POOL_SIZE --></div>
                <div class="kpi-label">Est. Talent Pool</div>
                <div class="kpi-detail"><!-- POOL_METHODOLOGY --></div>
            </div>
            <div class="kpi-card">
                <div class="kpi-value"><!-- COMPETING_ROLES --></div>
                <div class="kpi-label">Open Competing Roles</div>
                <div class="kpi-detail"><!-- ROLE_TREND --></div>
            </div>
            <div class="kpi-card">
                <div class="kpi-value"><!-- MEDIAN_OTE --></div>
                <div class="kpi-label">Median OTE</div>
                <div class="kpi-detail"><!-- OTE_SOURCE --></div>
            </div>
            <div class="kpi-card">
                <div class="kpi-value"><!-- MARKET_BALANCE --></div>
                <div class="kpi-label">Market Balance</div>
                <div class="kpi-detail"><!-- BALANCE_DETAIL --></div>
            </div>
        </div>

        <!-- Section 1: Compensation Landscape -->
        <div class="section">
            <h2>1. Compensation Landscape</h2>

            <h3>Base Salary & OTE by Segment</h3>
            <table>
                <thead>
                    <tr>
                        <th>Segment</th>
                        <th>Base (P25)</th>
                        <th>Base (P50)</th>
                        <th>Base (P75)</th>
                        <th>OTE (P50)</th>
                        <th>Source</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- COMP_ROW: repeat for each segment -->
                    <tr>
                        <td><strong><!-- SEGMENT_NAME --></strong></td>
                        <td><!-- BASE_P25 --></td>
                        <td><!-- BASE_P50 --></td>
                        <td><!-- BASE_P75 --></td>
                        <td><!-- OTE_P50 --></td>
                        <td class="source-note"><!-- SOURCE --></td>
                    </tr>
                </tbody>
            </table>
            <p class="source-note">Sources: <!-- COMP_SOURCES --></p>

            <h3>Geographic Adjustments</h3>
            <table>
                <thead>
                    <tr>
                        <th>Location</th>
                        <th>Adjustment vs. Base</th>
                        <th>Notes</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- GEO_ROW: repeat for each location -->
                    <tr>
                        <td><!-- LOCATION --></td>
                        <td><!-- ADJUSTMENT --></td>
                        <td><!-- NOTES --></td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Charts Row -->
        <div class="grid-2">
            <div class="card">
                <h3>Compensation by Segment</h3>
                <div class="chart-container">
                    <canvas id="compChart"></canvas>
                </div>
            </div>
            <div class="card">
                <h3>Talent Supply vs. Demand</h3>
                <div class="chart-container">
                    <canvas id="supplyDemandChart"></canvas>
                </div>
            </div>
        </div>

        <!-- Section 2: Talent Supply & Demand -->
        <div class="section">
            <h2>2. Talent Supply & Demand</h2>

            <h3>Supply Analysis</h3>
            <table>
                <thead>
                    <tr>
                        <th>Metric</th>
                        <th>Estimate</th>
                        <th>Methodology</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Total addressable pool</td>
                        <td><strong><!-- TOTAL_POOL --></strong></td>
                        <td><!-- POOL_METHOD --></td>
                    </tr>
                    <tr>
                        <td>Active candidates</td>
                        <td><strong><!-- ACTIVE_CANDIDATES --></strong></td>
                        <td><!-- ACTIVE_METHOD --></td>
                    </tr>
                    <tr>
                        <td>Passive but reachable</td>
                        <td><strong><!-- PASSIVE_CANDIDATES --></strong></td>
                        <td><!-- PASSIVE_METHOD --></td>
                    </tr>
                </tbody>
            </table>

            <h3>Top Hiring Competitors</h3>
            <table>
                <thead>
                    <tr>
                        <th>Company</th>
                        <th>Open Roles</th>
                        <th>Est. Comp Range</th>
                        <th>Brand Strength</th>
                        <th>Threat</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- COMPETITOR_ROW: repeat for each company -->
                    <tr>
                        <td><strong><!-- COMPANY --></strong></td>
                        <td><!-- OPEN_ROLES --></td>
                        <td><!-- COMP_RANGE --></td>
                        <td><span class="badge badge-high"><!-- BRAND --></span></td>
                        <td><span class="badge badge-high"><!-- THREAT --></span></td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Section 3: Hiring Difficulty Assessment -->
        <div class="section">
            <h2>3. Hiring Difficulty Assessment</h2>
            <table>
                <thead>
                    <tr>
                        <th>Factor</th>
                        <th>Score (1-5)</th>
                        <th>Assessment</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- DIFFICULTY_ROW: repeat for each factor -->
                    <tr>
                        <td><!-- FACTOR_NAME --></td>
                        <td><strong><!-- SCORE --></strong></td>
                        <td><!-- DETAIL --></td>
                    </tr>
                    <tr style="background: rgba(44, 48, 133, 0.06);">
                        <td><strong>Average</strong></td>
                        <td><strong style="color: var(--main); font-size: 16px;"><!-- AVG_SCORE --></strong></td>
                        <td><strong><!-- OVERALL_RATING --></strong></td>
                    </tr>
                </tbody>
            </table>
            <div class="callout">
                <strong>Scale:</strong>
                1.0-2.0 Low (standard process) &bull;
                2.1-3.0 Medium (competitive pressure) &bull;
                3.1-4.0 High (aggressive strategy needed) &bull;
                4.1-5.0 Very High (consider role redesign)
            </div>
        </div>

        <!-- Section 4: Market Trends -->
        <div class="section">
            <h2>4. Market Trends</h2>
            <!-- TREND: repeat block for each trend -->
            <h3><!-- TREND_TITLE --></h3>
            <p><!-- TREND_DESCRIPTION --></p>
        </div>

        <!-- Section 5: Recommendations -->
        <div class="section">
            <h2>5. Recommendations</h2>
            <ol class="recommendations">
                <li>
                    <strong><!-- REC_TITLE_1 --></strong><br>
                    <!-- REC_DETAIL_1 -->
                </li>
                <li>
                    <strong><!-- REC_TITLE_2 --></strong><br>
                    <!-- REC_DETAIL_2 -->
                </li>
                <li>
                    <strong><!-- REC_TITLE_3 --></strong><br>
                    <!-- REC_DETAIL_3 -->
                </li>
                <li>
                    <strong><!-- REC_TITLE_4 --></strong><br>
                    <!-- REC_DETAIL_4 -->
                </li>
            </ol>
        </div>

        <!-- Section 6: Data Sources -->
        <div class="section">
            <h2>Appendix: Data Sources & Methodology</h2>
            <p class="source-note"><!-- DATA_SOURCES_AND_METHODOLOGY --></p>
        </div>

    </div><!-- /content-body -->

    <!-- ============ FOOTER ============ -->
    <div class="footer">
        <img src="x.png" alt="x" class="footer-logo"><br>
        yourcompanyname &mdash; Generated <!-- DATE -->
    </div>

</div><!-- /container -->

<!-- ============ CHARTS ============ -->
<script>
// Brand color palette
// Brand palette + derived tints for multi-series charts
const BrandColors = [
    '#2C3085',  // Sec Blue (brand)
    '#D8512B',  //  Main Orange (brand)
    '#4a4db0',  // Blue lighter (derived tint — not in brand palette)
    '#e07a5a',  // Orange lighter (derived tint — not in brand palette)
    '#DFE3E7',  // Light Grey (brand)
    '#333333',  // Dark Grey (brand)
];

// Compensation Chart (grouped bar)
new Chart(document.getElementById('compChart'), {
    type: 'bar',
    data: {
        labels: [/* SEGMENT_LABELS e.g. 'Startup', 'Growth', 'Enterprise' */],
        datasets: [
            {
                label: 'Base P50',
                data: [/* BASE_P50_DATA */],
                backgroundColor: BrandColors[0],
                borderRadius: 4,
            },
            {
                label: 'OTE P50',
                data: [/* OTE_P50_DATA */],
                backgroundColor: BrandColors[1],
                borderRadius: 4,
            }
        ]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
            legend: {
                position: 'bottom',
                labels: { font: { family: 'Inter', size: 11 }, padding: 16 }
            }
        },
        scales: {
            x: { grid: { display: false }, ticks: { font: { family: 'Inter', size: 11 } } },
            y: {
                grid: { color: '#DFE3E7' },
                ticks: {
                    font: { family: 'Inter', size: 11 },
                    callback: function(value) { return '\u20AC' + value.toLocaleString(); }
                }
            }
        }
    }
});

// Supply vs Demand Chart (doughnut or bar)
new Chart(document.getElementById('supplyDemandChart'), {
    type: 'doughnut',
    data: {
        labels: [/* SUPPLY_DEMAND_LABELS e.g. 'Active Candidates', 'Passive Reachable', 'Open Roles' */],
        datasets: [{
            data: [/* SUPPLY_DEMAND_DATA */],
            backgroundColor: [BrandColors[0], BrandColors[2], BrandColors[1]],
            borderWidth: 2,
            borderColor: '#fff',
        }]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
            legend: {
                position: 'bottom',
                labels: { font: { family: 'Inter', size: 11 }, padding: 16 }
            }
        }
    }
});
</script>
</body>
</html>
```

## Customization Notes

### Embedding Logos as Base64

For fully self-contained HTML (works offline and in PDF), replace the logo `src` attributes:

**Header logo (white on blue):**
```html
<img src="data:image/png;base64,PASTE_LOGO_NEGATIVE_BASE64_HERE" alt="x" class="header-logo">
```

**Footer logo (dark on white):**
```html
<img src="data:image/png;base64,PASTE_LOGO_POSITIVE_BASE64_HERE" alt="x" class="footer-logo">
```

The base64-encoded logos are generated from `.claude/assets/*/*` and `.claude/assets/*/*`.

### Adding Chart Types

Additional chart examples are in `chart-examples.md`. Common additions for market insights:

- **Pipeline funnel** — horizontal bar chart showing conversion
- **Timeline** — line chart for posting trend over time
- **Compensation range** — box plot or grouped bar for P25/P50/P75

### Difficulty Badge Colors

Set the badge class based on the hiring difficulty score:

| Score Range | Class | Color |
|-------------|-------|-------|
| 1.0 - 2.0 | `difficulty-low` | Green |
| 2.1 - 3.0 | `difficulty-medium` | Amber |
| 3.1 - 4.0 | `difficulty-high` | Red |
| 4.1 - 5.0 | `difficulty-very-high` | Dark Red |

### PDF Export Checklist

- [ ] All `<!-- PLACEHOLDER -->` comments replaced with real data
- [ ] Chart.js data arrays populated with numbers
- [ ] Logo images embedded as base64 (or accessible via file path)
- [ ] Difficulty badge class matches the score
- [ ] Badge classes on competitor table match threat levels
- [ ] Print preview checked with "Background graphics: ON"
- [ ] Footer date matches report date
