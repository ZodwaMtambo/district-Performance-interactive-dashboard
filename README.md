# DoE Education Performance Dashboard : Power BI

An interactive Power BI dashboard built on South African Department of Education (DoE) matric results, covering 9 provinces and their districts. The raw dataset was cleaned and prepared in **Excel** before being loaded into **Power BI**, where DAX measures and five linked report pages were built to turn it into a fully interactive, decision-ready dashboard.

## 🧹 Workflow

1. **Data cleaning (Excel)** : raw DoE dataset was cleaned: null/missing values handled, columns standardised to correct data types (numbers, text, percentages), and inconsistent province/district naming fixed before loading into Power BI.
2. **Data modelling (Power BI / DAX)** :custom measures built to calculate pass rates, gender splits, rankings, and contribution percentages, all formatted to two decimal places.
3. **Dashboard build (Power BI)** : 5 interactive report pages with slicers (Province, District) that filter every visual on a page simultaneously.

## 📄 Dashboard Pages

### 1. Executive Overview
KPI cards for **Total Enrolment, Total Wrote, Total Passed, Total Failed, Total Bachelors, Exam Participation %, Pass Rate %**, a clustered column chart of pass rate by province, and a donut chart of Bachelor's pass contribution by province.
- **Key insight found:** exam participation across all three provinces in the dataset (Limpopo, Mpumalanga, North West) is **92.18%**, every province has a pass rate above 60%, and **Limpopo has the highest overall pass rate at 72.11%**.

### 2. Provincial Performance
Answers Q1, Q3, Q6, Q9 — a clustered column chart of male vs. female enrolment by province, a table of the **Gender Gap** measure, a pivot/matrix table showing **Average District Passes** per province, and a clustered column chart comparing female enrolment against Bachelor's passes by province.
- **Key insight found:** males outnumber females in almost every province except Limpopo, which also has the largest age gap.

### 3. District Performance
Answers Q2, Q4, Q7 ,a bar chart of **Total Bachelors** by district, a ranked table using a **District Rank** DAX measure over **Pass Rate %**, and a table of **Exam Participation %** by district.
- **Key insight found:** the top 5 performing districts by pass rate are **Mopani West, Capricorn North, Mopani East, Vhembe East, and Sekhukhune South**.

### 4. Overall Academic & Gender Performance
Answers Q5, Q10 , a combo chart plotting **Bachelor Pass Rate %** against **Overall Pass Rate %** by district, and a 100% stacked column chart of **Male %** / **Female %** by district (both built with `DIVIDE()`).
- **Key insights found:** districts with a high overall pass rate but comparatively low Bachelor's pass rate are **Mopani West, Mopani East, Capricorn North, and Bohlabela**. For gender balance, **Dr Ruth Segomotsi Mompati** (50.18% M / 49.82% F) and **Ngaka Modiri Molema** (50.21% M / 49.79% F) are the most balanced districts, while **Capricorn North** (46.56% M / 53.44% F) has the largest disparity, with female enrolment exceeding male.

### 5. Geographic Analysis
Answers Q11 , a map visual plotting every district, bubble size driven by **Pass Rate %**, coloured/legend by **Province**, with **Pass Rate %, Number Passed, and Number Failed** in the tooltip.
- **Key insight found:** performance clusters by province rather than randomly by district — **Limpopo** districts consistently show the largest bubbles (~72.34% average pass rate), led by **Mopani West** and **Capricorn North**; **Mpumalanga** districts cluster lowest (~68.72% average), with **Bohlabela** (66.13%) and **Ehlanzeni** (66.63%) the weakest; **North West** sits in between (~69.85%). This points to shared provincial factors (resourcing, infrastructure, administrative support) driving performance more than purely local conditions.

## 🧮 DAX Measures Used

| Measure | Purpose |
|---|---|
| `Pass Rate %` | Overall pass rate per province/district |
| `Total Bachelors` | Count of learners passing with Bachelor's admission |
| `Gender Gap` | Difference between male and female enrolment |
| `Exam Participation %` | Share of enrolled learners who wrote the exam |
| `Overall Pass Rate %` / `Bachelor Pass Rate %` | Compared side-by-side per district |
| `Average District Passes` | Average number of passes per district, rolled up by province |
| `District Rank` | Ranks districts by `Pass Rate %` |
| `Bachelor Contribution %` | Each province's share of total Bachelor's passes |
| `Male %` / `Female %` | Gender split per district, via `DIVIDE()` |

## 🖱️ Interactivity

Every visual on every page responds to the **Province** and **District** slicers, so results can be drilled from a national view down to a single district.

## 📁 Repo Contents

```
├── DoE_Education_Performance_Dashboard.pbix   # Power BI report file
├── Project_Brief.pdf                          # Original assignment brief
├── screenshots/                               # Dashboard page previews
└── README.md
```

## 🚀 How to View

1. Download `DoE_Education_Performance_Dashboard.pbix`
2. Open in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
3. Use the Province/District slicers to filter each page

---
*Academic group project for COMS5023A, School of Computer Science and Applied Mathematics, University of the Witwatersrand.*
