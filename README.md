## Email Generation Assistant (AI Engineer Assessment)

This repo implements:
- An **Email Generation Assistant** that takes `Intent`, `Key Facts`, and `Tone`
- **Advanced prompt engineering** (role-playing + few-shot examples)
- An **evaluation script** with **3 custom metrics** and **two-model comparison**
- Structured evaluation outputs (`CSV` + `JSON`) and a generated **final report**

### Setup

1. Create and activate a virtual environment (recommended)
   - Windows (PowerShell):
     - `python -m venv .venv`
     - `.venv\Scripts\Activate.ps1`
   - macOS/Linux:
     - `python3 -m venv .venv`
     - `source .venv/bin/activate`
2. Install dependencies:
   - `pip install -r requirements.txt`
3. Configure your environment variables:
   - Copy `.env.example` to `.env` and set `GROQ_API_KEY`
     - Windows (PowerShell): `Copy-Item .env.example .env`
     - macOS/Linux: `cp .env.example .env`

### Run: generate a single email

- `python generate_emails.py`

### Run: evaluation (10 scenarios, 2 models, 3 metrics)

- `python evaluate.py`

Outputs:
- `evaluation_results.csv` (scores only, easy to scan)
- `evaluation_report.json` (metrics definitions + full raw data + per-model summary)
- `FINAL_REPORT.md` (prompt template + metric logic + raw data pointers + comparative analysis)

### Run: report generation only (no API calls)

If you already have `evaluation_results.json`, you can regenerate the structured report + final report without re-running the models:
- `python generate_report.py`

This also writes:
- `evaluation_results_upgraded.json` / `evaluation_results_upgraded.csv` (ensures artifacts match the current 3 metrics, even if your original run used older metrics)

