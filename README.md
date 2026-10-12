# India-Stocks-241-270-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 241 to 270)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-241-270-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (241 to 270)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 241 | `ACC` | ACC Ltd. | `ACC.NS` |
| 242 | `ACMESOLAR` | ACME Solar Holdings Ltd. | `ACMESOLAR.NS` |
| 243 | `AWL` | AWL Agri Business Ltd. | `AWL.NS` |
| 244 | `AADHARHFC` | Aadhar Housing Finance Ltd. | `AADHARHFC.NS` |
| 245 | `AARTIIND` | Aarti Industries Ltd. | `AARTIIND.NS` |
| 246 | `AAVAS` | Aavas Financiers Ltd. | `AAVAS.NS` |
| 247 | `ACE` | Action Construction Equipment Ltd. | `ACE.NS` |
| 248 | `ACUTAAS` | Acutaas Chemicals Ltd. | `ACUTAAS.NS` |
| 249 | `ABREL` | Aditya Birla Real Estate Ltd. | `ABREL.NS` |
| 250 | `ABSLAMC` | Aditya Birla Sun Life AMC Ltd. | `ABSLAMC.NS` |
| 251 | `CPPLUS` | Aditya Infotech Ltd. | `CPPLUS.NS` |
| 252 | `AEGISLOG` | Aegis Logistics Ltd. | `AEGISLOG.NS` |
| 253 | `AEGISVOPAK` | Aegis Vopak Terminals Ltd. | `AEGISVOPAK.NS` |
| 254 | `AETHER` | Aether Industries Ltd. | `AETHER.NS` |
| 255 | `AFCONS` | Afcons Infrastructure Ltd. | `AFCONS.NS` |
| 256 | `AFFLE` | Affle 3i Ltd. | `AFFLE.NS` |
| 257 | `ABDL` | Allied Blenders and Distillers Ltd. | `ABDL.NS` |
| 258 | `ARE&M` | Amara Raja Energy & Mobility Ltd. | `ARE&M.NS` |
| 259 | `AMBER` | Amber Enterprises India Ltd. | `AMBER.NS` |
| 260 | `ANANDRATHI` | Anand Rathi Wealth Ltd. | `ANANDRATHI.NS` |
| 261 | `ANANTRAJ` | Anant Raj Ltd. | `ANANTRAJ.NS` |
| 262 | `ANGELONE` | Angel One Ltd. | `ANGELONE.NS` |
| 263 | `ANURAS` | Anupam Rasayan India Ltd. | `ANURAS.NS` |
| 264 | `APOLLOTYRE` | Apollo Tyres Ltd. | `APOLLOTYRE.NS` |
| 265 | `APTUS` | Aptus Value Housing Finance India Ltd. | `APTUS.NS` |
| 266 | `ASAHIINDIA` | Asahi India Glass Ltd. | `ASAHIINDIA.NS` |
| 267 | `ATHERENERG` | Ather Energy Ltd. | `ATHERENERG.NS` |
| 268 | `ATUL` | Atul Ltd. | `ATUL.NS` |
| 269 | `AVANTIFEED` | Avanti Feeds Ltd. | `AVANTIFEED.NS` |
| 270 | `AZAD` | Azad Engineering Ltd. | `AZAD.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream ACC 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-241-270-Historical-Data/main/ACC/1m/2026/10/ACC_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
