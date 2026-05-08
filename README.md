  # 🗳️ ECI — Tamil Nadu Assembly Elections 2026

  <img width="1302" height="729" alt="Screenshot 2026-05-09 000732" src="https://github.com/user-attachments/assets/88c9b5f5-22ad-47bf-bc21-4aff35193b5c" />


<div align="center">

  <br><br>
  <p>
    <img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" />
    <img src="https://img.shields.io/badge/DAX-Advanced-0052CC?style=for-the-badge&logo=databricks&logoColor=white" />
    <img src="https://img.shields.io/badge/Python-Data%20Prep-3776AB?style=for-the-badge&logo=python&logoColor=white" />
    <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" />
  </p>

  <p>
    <img src="https://img.shields.io/badge/Constituencies-234-E65100?style=for-the-badge" />
    <img src="https://img.shields.io/badge/Candidates-3%2C872-6A1B9A?style=for-the-badge" />
    <img src="https://img.shields.io/badge/Votes%20Cast-4.93%20Crore-2E7D32?style=for-the-badge" />
    <img src="https://img.shields.io/badge/Parties-105-1565C0?style=for-the-badge" />
  </p>

  > **A fully interactive Power BI Results Intelligence Dashboard built on real ECI election data — tracking seats won, vote share, gender split, cumulative count trend, and constituency-level EVM votes across all 234 Tamil Nadu Assembly constituencies.**

</div>

---

## 📌 Project Overview

| Detail | Value |
|---|---|
| **Tool** | Microsoft Power BI Desktop |
| **Data Source** | Official ECI Results — Tamil Nadu Assembly Elections 2026 |
| **Dataset** | 4,257 rows × 11 columns |
| **Total Constituencies** | 234 |
| **Total Candidates** | 3,872 |
| **Total Parties** | 105 |
| **Total Votes Cast** | 4.93 Crore (49,323,725) |
| **Counting Rounds** | 14/14 → 40/40 |
| **Data Prepared Using** | Python (pandas) + PostgreSQL |
| **Last Updated** | 04 May 2026 |

---

## 🎯 Business Problem

Tamil Nadu's 2026 Assembly Election generated millions of data points across 234 constituencies — but raw ECI results data is a flat CSV that tells no story on its own.

**This dashboard answers the questions every citizen, journalist, and political analyst asks:**

- 🏆 Which party won the most seats — and did they secure a majority?
- 📊 What is each party's actual vote share percentage?
- 🗺️ How did specific constituencies vote — who won where?
- 👥 How did female vs male voter turnout compare?
- 📈 How did the cumulative vote count build round by round on counting day?
- ⚠️ How close was the winning party to the 118-seat majority mark?

---

## 🏆 Key Election Results

### Seats Won

| Party | Seats Won | Vote Share |
|---|---|---|
| 🟠 Tamilaga Vettri Kazhagam (TVK) | **107** | 34.92% |
| 🔴 Dravida Munnetra Kazhagam (DMK) | **60** | 24.19% |
| 🟢 All India ADMK (AIADMK) | **47** | 21.21% |
| 🔵 Indian National Congress (INC) | **5** | 3.37% |
| 🟣 Pattali Makkal Katchi (PMK) | **4** | — |
| Others | **11** | — |
| **Total** | **234** | |

> ⚠️ **Key Insight:** TVK emerged as the **single largest party** with 107 seats and 34.92% vote share — but fell **11 seats short** of the **118-seat majority mark** out of 234 total constituencies.

---

### Gender Voter Split

| Gender | Votes Cast |
|---|---|
| 👩 Female Votes | **25.16 Million** |
| 👨 Male Votes | **24.17 Million** |

> 📌 Female voters **outnumbered male voters** — a notable democratic shift in Tamil Nadu's political landscape.

---

## 📊 Dashboard Visuals — Complete Inventory

### KPI Cards (Top Row)
| Card | Value |
|---|---|
| Total Votes Cast | 4.93 Crore |
| Total Candidates | 3,872 |
| Total Constituencies | 234 |
| Leading Party | Tamilaga Vettri Kazhagam |

### Party Seat Scorecards
| Scorecard | Party | Seats |
|---|---|---|
| 🟠 | TVK | 107 |
| 🔴 | DMK | 60 |
| 🟢 | ADMK | 47 |

### Charts & Visuals
| Visual | Type | What it shows |
|---|---|---|
| Top 5 Seats Won | Horizontal Bar Chart | Party-wise seat tally ranked |
| Top 5 Party Vote Share | Donut Chart | % vote share per major party |
| Count Trend | Area Chart | Cumulative vote count by round (14/14 → 40/40) |
| Total EVM Votes by Constituency | Sparkline | Constituency-level EVM vote distribution |
| Female / Male Votes | KPI Cards with icons | Gender-split voter turnout |

### Insight Cards (Left Panel)
| Insight | Description |
|---|---|
| 🥇 Winner Insight | TVK won 107 seats with 34.9% vote share as single largest party |
| ⚠️ Majority Gap | TVK fell 11 seats short of the 118-seat majority mark |
| 📊 Total Votes | 4.93 Crore votes cast across 234 constituencies — 2.11 Lakh avg per seat |

### Slicers (Filters)
- **Party** — Filter all visuals by political party
- **District** — Filter by Tamil Nadu district
- **Constituency** — Drill down to a single constituency

---

## 🗂️ Dataset Structure

**File:** `eci_results_tamilnadu_2026.csv`
**Rows:** 4,257 &nbsp;|&nbsp; **Columns:** 11

| Column | Type | Description |
|---|---|---|
| `Code` | VARCHAR | Constituency code (e.g. S221) |
| `Constituency` | VARCHAR | Constituency name with serial number |
| `Candidate` | VARCHAR | Full candidate name |
| `Party` | VARCHAR | Party name (105 unique parties) |
| `EVM Votes` | INT | Votes cast on Electronic Voting Machine |
| `Postal Votes` | INT | Postal ballot votes |
| `Total Votes` | INT | EVM Votes + Postal Votes |
| `% Votes` | DECIMAL | Candidate's vote percentage in constituency |
| `Round` | VARCHAR | Counting round (e.g. 26/26, 40/40) |
| `Last Updated Time` | TIME | Time of last data update |
| `Last Updated Date` | DATE | Date of last data update (04-05-2026) |

---

## 🧮 DAX Measures Used

```dax
-- Total Votes Cast
Total Votes =
    SUM( 'eci_results_tamilnadu_2026'[Total Votes] )

-- Total Candidates
Total Candidates =
    DISTINCTCOUNT( 'eci_results_tamilnadu_2026'[Candidate] )

-- Total Constituencies
Total Constituencies =
    DISTINCTCOUNT( 'eci_results_tamilnadu_2026'[Constituency] )

-- Is Winner Calculated Column (added before measure)
Is Winner =
VAR MaxVotesInConstituency =
    CALCULATE(
        MAX( 'eci_results_tamilnadu_2026'[Total Votes] ),
        ALLEXCEPT(
            'eci_results_tamilnadu_2026',
            'eci_results_tamilnadu_2026'[Constituency]
        )
    )
RETURN
    IF( 'eci_results_tamilnadu_2026'[Total Votes] = MaxVotesInConstituency, 1, 0 )

-- Seats Won (uses Is Winner column)
Seats Won =
    SUM( 'eci_results_tamilnadu_2026'[Is Winner] )

-- Vote Share %
Vote Share % =
DIVIDE(
    SUM( 'eci_results_tamilnadu_2026'[Total Votes] ),
    CALCULATE(
        SUM( 'eci_results_tamilnadu_2026'[Total Votes] ),
        ALL( 'eci_results_tamilnadu_2026'[Party] )
    ),
    0
)

-- Majority Mark (static reference)
Majority Mark = 118

-- Majority Gap (for TVK insight card)
Majority Gap =
    [Majority Mark] - CALCULATE( [Seats Won],
        'eci_results_tamilnadu_2026'[Party] = "Tamilaga Vettri Kazhagam"
    )

-- Average Votes Per Seat
Avg Votes Per Seat =
    DIVIDE( [Total Votes], [Total Constituencies], 0 )
```

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard design, data modelling, all visuals |
| **DAX** | All measures — Seats Won, Vote Share %, Majority Gap, Avg Votes |
| **Python (pandas)** | Data cleaning — added `Is_Winner` column, handled encoding |
| **Power Query (M)** | Data transformation and column type fixes inside Power BI |
| **PostgreSQL** | SQL-based data validation before ingestion |
| **GitHub** | Version control and portfolio hosting |

---

## 📁 Repository Structure

```
eci-tamilnadu-2026-dashboard/
│
├── 📄 README.md                            ← You are here
├── 📊 ECI_TamilNadu_2026.pbix              ← Power BI dashboard file
├── 📁 data/
│   ├── 📄 eci_results_tamilnadu_2026.csv   ← Raw ECI results (4,257 rows)
│   └── 📄 eci_results_with_winner.csv      ← Enriched data with Is_Winner column
└── 📁 assets/
    └── 🖼️ dashboard_screenshot.png         ← Dashboard preview image
```

---

## 🚀 How to Open This Project

```bash
# Step 1 — Clone this repository
git clone https://github.com/bisht5431-source/eci-tamilnadu-2026-dashboard.git

# Step 2 — Open Power BI Desktop
# Download free: https://powerbi.microsoft.com/desktop

# Step 3 — Open the .pbix file
# File → Open → ECI_TamilNadu_2026.pbix

# Step 4 — Explore the dashboard
# Use Party, District, and Constituency slicers to filter live
# All visuals cross-filter automatically on click
```

---

## 💼 What This Project Demonstrates

| Skill | Evidence in Dashboard |
|---|---|
| **DAX Measure Architecture** | 8 custom measures — Seats Won, Vote Share %, Majority Gap, Avg Votes Per Seat |
| **Calculated Columns** | Is Winner column using ALLEXCEPT for constituency-level max vote logic |
| **Data Cleaning (Python)** | pandas used to build Is_Winner enriched dataset before Power BI import |
| **Complex Filter Context** | ALLEXCEPT, ALL, CALCULATE used correctly for row-context calculations |
| **Interactive Slicers** | 3 slicers (Party, District, Constituency) cross-filtering all 7+ visuals |
| **Business Storytelling** | Smart insight cards translate numbers into political narrative |
| **Geopolitical Data Analysis** | Real government dataset — not a tutorial dataset |
| **Chart Variety** | Bar chart, donut chart, area chart, sparkline, KPI cards all in one report |

---

## 📬 Connect With Me

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/dataanalyst-manish)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/bisht5431-source)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:alphainsights123@gmail.com)

</div>

---

<div align="center">

**⭐ If this project helped you, please star the repository — it helps other analysts find it.**

*Built by Manish Bisht — Data Analyst Intern · Intellipaat Software Solutions Pvt. Ltd.*
*SQL · Power BI · DAX · Python · Excel*

</div>
