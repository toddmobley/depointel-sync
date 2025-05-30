# DepoIntel Sync

This project automates the extraction of civil litigation cases from Trellis API and logs attorney + deposition data into a Google Sheet for sales outreach by Veritext.

---

## 🔁 How It Works

- Runs daily using GitHub Actions
- Queries Trellis API for recent civil litigation cases by region and case type
- Extracts attorney name, firm, case type, deposition date
- Pushes data into a Google Sheet used by the DepoIntel dashboard

---

## ⚙️ Setup Instructions

### 1. Environment Variables (set in GitHub Secrets)

- `SHEET_ID` — Your target Google Sheet ID
- `TRELLIS_API_URL` — Your Trellis API endpoint
- `TRELLIS_API_KEY` — API key for authentication
- `GOOGLE_CREDS_B64` — base64-encoded credentials.json (Google Service Account)

### 2. GitHub Actions

- Workflow file: `.github/workflows/sync.yml`
- Schedule: Daily at 8 AM EST
- Also supports manual runs via GitHub UI

---

## 🔐 Security Notes

- `credentials.json` is never committed — stored securely via base64 secret
- All keys and tokens are managed through encrypted GitHub Secrets

---

## 📈 Dashboard Integration

This repo feeds a live dashboard built in React + Tailwind that visualizes:
- Attorney info
- Event timelines
- Lead scoring
- Outreach response rates

---

## 🔧 Future Enhancements

- Slack/Email alerts on sync completion
- Integration with CRM
- Error logging and retries
