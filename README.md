# Multi-Source Feedback Intelligence System

A production-ready Python system that aggregates app reviews from multiple
sources, performs AI-powered sentiment analysis, detects trends, prioritises
issues, and renders a live Streamlit dashboard with downloadable PDF reports.

## Features

| Feature | Details |
|---|---|
| **Data Sources** | Google Play Store, Apple App Store, CSV surveys |
| **Sentiment Analysis** | DistilBERT (HuggingFace), confidence + score |
| **Trend Detection** | Daily avg, 7-day rolling, 20% drop alerts |
| **Issue Prioritisation** | Keyword frequency × negative sentiment strength |
| **Dashboard** | Streamlit — filters, KPIs, charts, table |
| **PDF Reports** | ReportLab Platypus — charts, tables, recommendations |
| **Testing** | pytest + pytest-cov (>80 % coverage) |
| **Deployment** | Docker multi-stage build |

## Quick Start

### Local
```bash
python3.10 -m venv venv && source venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

### Docker
```bash
docker build -t feedback-intelligence .
docker run -p 8501:8501 \
  -e COMPANY_NAME="Acme Corp" \
  -e LOG_LEVEL=INFO \
  feedback-intelligence
```

Open `http://localhost:8501` in your browser.

## Project Structure