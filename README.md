[README.md](https://github.com/user-attachments/files/26900328/README.md)
# 💰 Wealth Tracker | ධන සටහන

A powerful, single-file personal wealth and income tracking web app with real-time live tickers, Google Sheets sync, multi-currency support, and detailed charts for every income type. No server required — runs entirely in the browser.

---

## ✨ Features at a glance

- **Portfolio home screen** — combined live earnings ticker across all your income sources, with progress bars, FX conversion, and per-second/minute/hour/day rates
- **7 income types** — Business, Job, Rental, Fixed Deposit, Investment, Farming, Other
- **Google Sheets sync** — all data syncs to your own Google Sheet automatically
- **Multi-currency** — 17 currencies with live FX conversion (portfolio hero converts everything to your chosen display currency)
- **Charts** — rich Chart.js visualisations for every income type
- **Dark / light theme** — system-aware, toggleable
- **Bilingual** — English and Sinhala (සිංහල) UI
- **Loans tracker** — track debts linked to any income source
- **Attendance & leave** — full schedule management for Job sources
- **Offline-first** — all data persists in localStorage; Google Sheets is an optional sync layer
- **Single HTML file** — no build step, no dependencies to install, no server

---

## 📱 Getting started

1. Download `index.html` Or Go to https://sun250sw-alt.github.io/biz/
2. Open it in any modern browser (Chrome, Safari, Firefox, Edge)
3. Follow the onboarding — name your first income source and pick its type
4. Optionally connect Google Sheets for cloud backup and sync

That's it. No login required to use locally.

---

## 🏦 Income types

| Type | Icon | What it tracks |
|---|---|---|
| **Business** | 🏪 | Daily sales, expenses, profit/loss, hourly targets, ops log |
| **Job** | 💼 | Salary, attendance, leave, payslips, hourly rate |
| **Rental** | 🏠 | Rent payments, tenants, maintenance costs, loan offset |
| **Fixed Deposit** | 🏦 | Interest accrual, maturity timeline, renewal tracking |
| **Investment** | 📈 | Portfolio value, holdings, transactions, dividends |
| **Farming** | 🌾 | Season accrual, harvest log, costs, sales |
| **Other** | ✦ | Passive/freelance income, expenses, trend charts |

---

## 📊 Charts — by income type

### 🏪 Business
- Revenue vs target (daily/weekly/monthly)
- Profit trend
- Expense breakdown

### 💼 Job
- Hours worked (day/week/month)
- Income earned per period
- Attendance rate & on-time stats

### 🏠 Rental
- Monthly rent income — last 12 months
- Cumulative income this year
- Income vs loan/maintenance costs (daily net)

### 🏦 Fixed Deposit
- Monthly interest projection over full term
- Principal vs total interest vs maturity value
- Monthly interest last 12 months (respects FD start/end dates)

### 📈 Investment
- Capital breakdown doughnut (invested vs gain/loss)
- Current value vs invested bar chart
- Net gain/loss bar with breakeven line

### 🌾 Farming
- Season accrual progress (actual vs projected)
- Daily accrual bars for elapsed season days
- Season timeline card (start, harvest date, % complete)

### ✦ Other income
- Monthly income trend — last 12 months
- Cumulative income this year
- Daily income — last 30 days

---

## 🌍 Currencies supported

| Code | Symbol | Code | Symbol |
|---|---|---|---|
| LKR | රු | USD | $ |
| EUR | € | GBP | £ |
| AUD | A$ | CAD | C$ |
| SGD | S$ | JPY | ¥ |
| CNY | ¥ | INR | ₹ |
| AED | د.إ | SAR | ر.س |
| MYR | RM | THB | ฿ |
| KRW | ₩ | QAR | ر.ق |
| KWD | د.ك | | |

- Each income source has its **own currency** set independently in the Edit modal
- The **portfolio display currency** (topbar dropdown) converts the combined hero total via live FX rates
- FX rates refresh every 15 minutes from [open.er-api.com](https://open.er-api.com)

---

## ☁️ Google Sheets sync

1. Sign in with Google (OAuth) from the app
2. A **Wealth Tracker** folder is created in your Drive automatically
3. Each income source gets its own sheet tab
4. Data syncs on every save (debounced) and on demand via the sync button
5. The app reads back from Sheets on sign-in — your data follows you across devices

> Your data stays in **your own** Google Drive. Anthropic/the app never stores it.

---

## 🗂️ Data storage

| Layer | What's stored |
|---|---|
| `localStorage` | All income data, expenses, attendance, portData, FX cache |
| Google Sheets | Mirror of all data — used for cross-device sync and backup |

Data keys follow the pattern `smt_{bizId}_{type}` (e.g. `smt_biz1_income`).

---

## 🛠️ Tech stack

| Library | Version | Used for |
|---|---|---|
| [Chart.js](https://www.chartjs.org) | 4.4.1 | All charts |
| Google OAuth2 | — | Authentication |
| Google Sheets API v4 | — | Cloud sync |
| open.er-api.com | — | Live FX rates |

No npm, no build tools, no frameworks. Pure HTML + CSS + vanilla JS in one file.

---

## 📁 File structure

```
index.html          ← entire app (HTML + CSS + JS, single file)
README.md           ← this file
```

---

## 🔒 Privacy

- No data is ever sent to any third-party server except:
  - **Google Sheets API** (your own Drive, authenticated by you)
  - **open.er-api.com** (anonymous FX rate fetch, no personal data)
- All processing happens locally in your browser
- No analytics, no ads, no tracking

---

## 📝 Changelog

### Latest
- ✅ Charts added for all income types (Rental, FD, Investment, Farming, Other)
- ✅ All cash amounts now use comma-separated thousand separators
- ✅ Hourly rates display at 2 decimal places throughout
- ✅ Currency symbols now correctly follow each source's own currency everywhere
- ✅ Portfolio home currency changer (topbar) now responds immediately
- ✅ Job progress bar now shows correct period salary target (month/day/year)
- ✅ `getBizCur()` now has 4-layer fallback — no more incorrect LKR default
- ✅ Source currencies persist reliably across page reloads

---

## 🤝 Contributing

This is a single-file app — all contributions go into `index.html`. Keep the no-build-step philosophy: no npm, no bundler, no external CSS frameworks.

---

## 📄 License

MIT — free to use, modify and distribute.
