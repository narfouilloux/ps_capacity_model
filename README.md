# PS Capacity Dashboard · Thynk.Cloud · 2026

> **Internal tool — VP Delivery & Customer Success only.**
> Source data: Claude conversation `490ff41e-787d-4998-b789-980f653dcadd`

A password-protected, fully interactive capacity planning dashboard for the Thynk.Cloud Professional Services team. Zero build step — pure HTML/JS served via GitHub Pages.

---

## 🚀 Live Dashboard

**[https://narfouilloux.github.io/ps_capacity_model](https://narfouilloux.github.io/ps_capacity_model)**

---

## 📊 What's in the dashboard

| Section | Content |
|---|---|
| **KPI Strip** | 2026 working forecast · Q1 actuals · billable capacity · utilisation · YoY growth |
| **Scenario Toggle** | Run-rate (€1,080K ★) · Linear (€1,050K) · Compounding (€1,154K) |
| **Annual Chart** | 2024–2026 backlog evolution with target reference line |
| **Monthly Chart** | Q1 actuals + Q2–Q4 projection by scenario |
| **Capacity Model** | Role table: Sr. Functional / Trainer / IC — FTE, util%, billable hrs/days |
| **Rate Card Stress Test** | Daily rate slider (€500–€1,400) · +IC FTE slider · 5% sick-leave buffer toggle |
| **Watch Items** | 4 flagged risks: forecast confidence, blended rate gate, trainer util, Sr. Functional allocation |

---

## 🔐 Access

The dashboard is password-gated. Change the access code before deploying:

```html
<!-- index.html, line ~230 -->
const ACCESS_CODE = 'thynk2026'; // ← change this
```

Auth persists for the browser session (`sessionStorage`) — clears on tab close.

---

## 📁 Repository structure

```
ps_capacity_model/
├── index.html      ← entire dashboard (single file, no build step)
└── README.md
```

---

## ⚡ Deploy to GitHub Pages

1. Go to **Settings → Pages** in this repo
2. Source: **Deploy from a branch**
3. Branch: `main` · Folder: `/ (root)`
4. Click **Save**
5. Dashboard is live at `https://narfouilloux.github.io/ps_capacity_model` within ~60 seconds

---

## 🔄 Updating the data

All data lives in `index.html`. To update:

| What to change | Where in `index.html` |
|---|---|
| Scenario forecast values | `SC` object in `<script>` block |
| Role table (FTE, util, hrs) | HTML table in capacity model section |
| KPI strip values | KPI `.kpi-val` elements |
| Access code | `ACCESS_CODE` constant |

---

## 📦 Dependencies

- [Chart.js 4.4.1](https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js) — loaded from CDN, no npm install
- [Google Fonts: Syne + DM Mono](https://fonts.google.com) — loaded from CDN

No Node.js, no bundler, no CI/CD required.

---

*Thynk.Cloud · Internal · March 2026*
