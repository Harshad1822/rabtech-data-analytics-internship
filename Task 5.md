# Interactive Dashboard & KPI Visualizations

An executive KPI dashboard built with **Streamlit + Plotly**, with a one-page PDF export.

## KPIs
| KPI | Definition |
|---|---|
| Revenue | Sum of order revenue |
| Average Order Value (AOV) | Revenue / orders |
| Customer Acquisition Cost (CAC) | Marketing spend / new customers |
| Churn Rate | Churned customers / active customers |
| Orders | Count of orders (supporting metric) |

Each KPI card shows the change versus the previous period of equal length (percentage change, or percentage points for churn). For CAC and churn, a decrease is shown as good.

## Features
- **Slicers:** period range, region, category and channel. Every chart and KPI responds.
- **Trend area chart** with metric switch (revenue / orders / new customers) and Year / Quarter / Month granularity.
- **Geographic heatmap:** choropleth of revenue by US state.
- **Drill-down:** time (Year > Quarter > Month) and geography (Region > State).
- **Channel view:** CAC vs churn on a dual-axis chart, plus a category performance table.
- **Layout:** KPI cards first (summary), then trend and map, then drill-downs, then detail.

## Run locally
```bash
pip install -r requirements.txt
streamlit run app.py
```

## Deploy (free public link)
1. Push this folder to a public GitHub repo.
2. Go to https://share.streamlit.io, choose "New app", pick the repo, and set the main file to `app.py`.
3. Copy the resulting `*.streamlit.app` URL as the proof link.

## Files
- `app.py` – the Streamlit dashboard
- `data.py` – seeded synthetic dataset (24 months x 16 states x 5 categories x 4 channels) and KPI functions
- `make_pdf.py` – generates `Dashboard_Export.pdf` (A4 landscape)
- `Dashboard_Export.pdf` – dashboard PDF export (last 12 months vs prior 12)

## Data
The data is synthetic (seed 42). To use real data, return a DataFrame with the same columns from `load_data()` in `data.py`.
