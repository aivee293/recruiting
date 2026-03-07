# Chart.js Code Snippets for Sourcing Dashboards

## Pipeline Funnel (Horizontal Bar)

```javascript
new Chart(document.getElementById('funnelChart'), {
    type: 'bar',
    data: {
        labels: ['Identified', 'Contacted', 'Responded', 'Interested', 'Screened', 'Submitted'],
        datasets: [{
            data: [45, 28, 14, 8, 5, 3],
            backgroundColor: [
                '#3b82f6', '#6366f1', '#8b5cf6',
                '#a855f7', '#c084fc', '#d8b4fe'
            ],
            borderRadius: 6,
            barThickness: 28,
        }]
    },
    options: {
        indexAxis: 'y',
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
            legend: { display: false },
            tooltip: {
                callbacks: {
                    label: (ctx) => `${ctx.raw} candidates`
                }
            }
        },
        scales: {
            x: { grid: { display: false }, ticks: { stepSize: 10 } },
            y: { grid: { display: false } }
        }
    }
});
```

## Source Effectiveness (Doughnut)

```javascript
new Chart(document.getElementById('sourceChart'), {
    type: 'doughnut',
    data: {
        labels: ['LinkedIn', 'GitHub', 'X-Ray', 'Referral', 'Community', 'Other'],
        datasets: [{
            data: [18, 8, 6, 5, 4, 4],
            backgroundColor: [
                '#3b82f6', '#10b981', '#f59e0b',
                '#ef4444', '#8b5cf6', '#6b7280'
            ],
            borderWidth: 0,
            hoverOffset: 8,
        }]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        cutout: '60%',
        plugins: {
            legend: { position: 'bottom', labels: { padding: 16, font: { size: 12 } } },
            tooltip: {
                callbacks: {
                    label: (ctx) => `${ctx.label}: ${ctx.raw} candidates (${Math.round(ctx.raw/ctx.dataset.data.reduce((a,b)=>a+b)*100)}%)`
                }
            }
        }
    }
});
```

## Pipeline Growth Timeline (Line)

```javascript
new Chart(document.getElementById('timelineChart'), {
    type: 'line',
    data: {
        labels: ['Week 1', 'Week 2', 'Week 3', 'Week 4', 'Week 5', 'Week 6'],
        datasets: [
            {
                label: 'Identified',
                data: [8, 18, 28, 35, 40, 45],
                borderColor: '#3b82f6',
                backgroundColor: 'rgba(59, 130, 246, 0.1)',
                fill: true,
                tension: 0.3,
            },
            {
                label: 'In Pipeline',
                data: [2, 6, 10, 14, 16, 18],
                borderColor: '#10b981',
                backgroundColor: 'rgba(16, 185, 129, 0.1)',
                fill: true,
                tension: 0.3,
            }
        ]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
            legend: { position: 'bottom' }
        },
        scales: {
            y: { beginAtZero: true, grid: { color: '#f3f4f6' } },
            x: { grid: { display: false } }
        }
    }
});
```

## Compensation Range (Grouped Bar)

```javascript
new Chart(document.getElementById('compChart'), {
    type: 'bar',
    data: {
        labels: ['Startup', 'Growth', 'Enterprise', 'Big Tech'],
        datasets: [
            {
                label: 'P25',
                data: [140, 160, 170, 190],
                backgroundColor: '#bfdbfe',
                borderRadius: 4,
            },
            {
                label: 'P50',
                data: [165, 185, 195, 230],
                backgroundColor: '#3b82f6',
                borderRadius: 4,
            },
            {
                label: 'P75',
                data: [195, 220, 230, 280],
                backgroundColor: '#1e3a8a',
                borderRadius: 4,
            }
        ]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
            legend: { position: 'bottom' },
            tooltip: {
                callbacks: { label: (ctx) => `${ctx.dataset.label}: €${ctx.raw}K` }
            }
        },
        scales: {
            y: {
                beginAtZero: false,
                min: 100,
                ticks: { callback: (val) => `€${val}K` },
                grid: { color: '#f3f4f6' }
            },
            x: { grid: { display: false } }
        }
    }
});
```

## Talent Map Priority Distribution (Polar Area)

```javascript
new Chart(document.getElementById('mapChart'), {
    type: 'polarArea',
    data: {
        labels: ['Circle 1 (Direct)', 'Circle 2 (Adjacent)', 'Circle 3 (Transferable)'],
        datasets: [{
            data: [120, 350, 800],
            backgroundColor: [
                'rgba(59, 130, 246, 0.7)',
                'rgba(16, 185, 129, 0.7)',
                'rgba(245, 158, 11, 0.7)'
            ],
            borderWidth: 0,
        }]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
            legend: { position: 'bottom' },
            tooltip: {
                callbacks: { label: (ctx) => `${ctx.label}: ~${ctx.raw} candidates` }
            }
        }
    }
});
```
