# HTML Dashboard Templates

## Pipeline Dashboard Template

Full self-contained HTML for a sourcing pipeline dashboard. Copy and customize.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sourcing Pipeline Dashboard</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif; background: #f0f2f5; color: #1a1a2e; padding: 24px; }
        .container { max-width: 1200px; margin: 0 auto; }
        .header { background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%); color: white; padding: 32px; border-radius: 16px; margin-bottom: 24px; }
        .header h1 { font-size: 1.8em; margin-bottom: 4px; }
        .header .subtitle { opacity: 0.7; font-size: 0.95em; }
        .kpi-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 16px; margin-bottom: 24px; }
        .kpi-card { background: white; border-radius: 12px; padding: 24px; box-shadow: 0 1px 3px rgba(0,0,0,0.08); }
        .kpi-value { font-size: 2.2em; font-weight: 700; line-height: 1.2; }
        .kpi-label { font-size: 0.8em; color: #6b7280; text-transform: uppercase; letter-spacing: 0.05em; margin-top: 4px; }
        .kpi-change { font-size: 0.85em; margin-top: 8px; }
        .up { color: #059669; } .down { color: #dc2626; } .neutral { color: #6b7280; }
        .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; margin-bottom: 24px; }
        .card { background: white; border-radius: 12px; padding: 24px; box-shadow: 0 1px 3px rgba(0,0,0,0.08); margin-bottom: 24px; }
        .card h2 { font-size: 1.1em; color: #374151; margin-bottom: 16px; padding-bottom: 12px; border-bottom: 1px solid #e5e7eb; }
        .chart-container { position: relative; height: 300px; }
        table { width: 100%; border-collapse: collapse; }
        th { font-size: 0.75em; font-weight: 600; color: #6b7280; text-transform: uppercase; letter-spacing: 0.05em; text-align: left; padding: 12px; border-bottom: 2px solid #e5e7eb; }
        td { padding: 12px; border-bottom: 1px solid #f3f4f6; font-size: 0.9em; }
        tr:hover td { background: #f9fafb; }
        .badge { display: inline-block; padding: 4px 12px; border-radius: 20px; font-size: 0.75em; font-weight: 600; }
        .badge-green { background: #d1fae5; color: #065f46; }
        .badge-yellow { background: #fef3c7; color: #92400e; }
        .badge-blue { background: #dbeafe; color: #1e40af; }
        .badge-red { background: #fee2e2; color: #991b1b; }
        .footer { text-align: center; padding: 24px; color: #9ca3af; font-size: 0.8em; }
        @media (max-width: 768px) { .grid-2 { grid-template-columns: 1fr; } }
        @media print { body { padding: 0; background: white; } .card { box-shadow: none; border: 1px solid #e5e7eb; page-break-inside: avoid; } }
    </style>
</head>
<body>
<div class="container">
    <div class="header">
        <h1><!-- ROLE TITLE --> - Sourcing Pipeline</h1>
        <div class="subtitle">Updated: <!-- DATE --> | Week <!-- WEEK_NUM --></div>
    </div>

    <!-- KPI Cards -->
    <div class="kpi-grid">
        <div class="kpi-card">
            <div class="kpi-value"><!-- TOTAL_IDENTIFIED --></div>
            <div class="kpi-label">Candidates Identified</div>
            <div class="kpi-change up">+<!-- NEW_THIS_WEEK --> this week</div>
        </div>
        <div class="kpi-card">
            <div class="kpi-value"><!-- RESPONSE_RATE -->%</div>
            <div class="kpi-label">Response Rate</div>
            <div class="kpi-change neutral">Industry avg: 15-25%</div>
        </div>
        <div class="kpi-card">
            <div class="kpi-value"><!-- IN_PIPELINE --></div>
            <div class="kpi-label">Active in Pipeline</div>
            <div class="kpi-change up"><!-- PIPELINE_CHANGE --></div>
        </div>
        <div class="kpi-card">
            <div class="kpi-value"><!-- SUBMITTED_HM --></div>
            <div class="kpi-label">Submitted to HM</div>
            <div class="kpi-change">Target: <!-- TARGET --></div>
        </div>
    </div>

    <!-- Charts Row -->
    <div class="grid-2">
        <div class="card">
            <h2>Pipeline Funnel</h2>
            <div class="chart-container">
                <canvas id="funnelChart"></canvas>
            </div>
        </div>
        <div class="card">
            <h2>Source Channels</h2>
            <div class="chart-container">
                <canvas id="sourceChart"></canvas>
            </div>
        </div>
    </div>

    <!-- Candidates Table -->
    <div class="card">
        <h2>Top Candidates</h2>
        <table>
            <thead>
                <tr>
                    <th>Candidate</th>
                    <th>Current Company</th>
                    <th>Stage</th>
                    <th>Source</th>
                    <th>Notes</th>
                </tr>
            </thead>
            <tbody>
                <!-- CANDIDATE_ROWS -->
                <tr>
                    <td><strong><!-- NAME --></strong></td>
                    <td><!-- COMPANY --></td>
                    <td><span class="badge badge-green"><!-- STAGE --></span></td>
                    <td><!-- SOURCE --></td>
                    <td><!-- NOTES --></td>
                </tr>
            </tbody>
        </table>
    </div>
</div>

<div class="footer">Generated by Talent Sourcing Plugin | <!-- DATE --></div>

<script>
// Pipeline Funnel Chart
new Chart(document.getElementById('funnelChart'), {
    type: 'bar',
    data: {
        labels: ['Identified', 'Contacted', 'Responded', 'Interested', 'Screened', 'Submitted'],
        datasets: [{
            data: [/* FUNNEL_DATA */],
            backgroundColor: ['#3b82f6', '#6366f1', '#8b5cf6', '#a855f7', '#c084fc', '#d8b4fe'],
            borderRadius: 6,
        }]
    },
    options: {
        indexAxis: 'y',
        responsive: true,
        maintainAspectRatio: false,
        plugins: { legend: { display: false } },
        scales: { x: { grid: { display: false } }, y: { grid: { display: false } } }
    }
});

// Source Channel Doughnut
new Chart(document.getElementById('sourceChart'), {
    type: 'doughnut',
    data: {
        labels: [/* SOURCE_LABELS */],
        datasets: [{
            data: [/* SOURCE_DATA */],
            backgroundColor: ['#3b82f6', '#10b981', '#f59e0b', '#ef4444', '#8b5cf6', '#6b7280'],
        }]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: { legend: { position: 'bottom' } }
    }
});
</script>
</body>
</html>
```

## Usage Notes

- Replace all `<!-- PLACEHOLDER -->` comments with actual data
- Chart data arrays should be populated with numbers: `[45, 28, 14, 8, 5, 3]`
- Badge colors: green (positive stages), blue (in progress), yellow (waiting), red (blocked)
- The template is fully self-contained - only external dependency is Chart.js CDN
- Print-friendly with `@media print` styles
- Responsive for mobile viewing
