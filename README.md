# 🦠 COVID-19 Pandemic Data Analysis

## 📋 Overview
This project analyzes the COVID-19 pandemic using Python, focusing on confirmed cases, deaths, and recoveries across different countries and regions from January 2020 to May 2021.

## 📁 Dataset
The dataset contains 3 sheets in Excel format:
- **Confirmed Cases** — 276 countries, daily cumulative confirmed cases
- **Deaths** — 276 countries, daily cumulative death counts
- **Recovered** — 261 countries, daily cumulative recovery counts
- **Date Range:** January 22, 2020 — May 29, 2021

## 🛠️ Libraries Used
- Pandas
- NumPy
- Matplotlib

## 📊 Analysis Questions & Results

---

### ✅ Q1 — Data Loading
Loaded 3 datasets from Excel using Pandas:
- Confirmed: (276, 498)
- Deaths: (276, 498)
- Recovered: (261, 498)

---

### ✅ Q2 — Data Exploration
- Explored shape, data types and structure of all 3 datasets
- **Plot 1:** Confirmed cases over time for Top 10 countries — USA had steepest curve
- **Plot 2:** Confirmed cases by province in China — Hubei was the epicenter

---

### ✅ Q3 — Handling Missing Data
- Found ~194 missing values across datasets
- Applied **Forward Fill then Backward Fill** for time-series imputation
- Result: **0 missing values** after cleaning

---

### ✅ Q4 — Data Cleaning
- Replaced blank Province/State values with **All Provinces**
- 190 entries updated across confirmed and deaths datasets

---

### ✅ Q5 — Independent Dataset Analysis

#### Q5.1 — Peak Daily New Cases (Germany, France, Italy)
| Country | Peak Cases | Date |
|---------|-----------|------|
| Germany | 49,044 | Dec 30, 2020 |
| France  | 117,900 | Nov 4, 2021 |
| Italy   | 40,902 | Nov 13, 2020 |

France had the highest single-day surge driven by the Delta variant.

#### Q5.2 — Recovery Rates: Canada vs Australia (Dec 31, 2020)
| Country | Confirmed | Recovered | Recovery Rate |
|---------|-----------|-----------|---------------|
| Canada    | 584,409 | 493,638 | 84.47% |
| Australia | 28,425  | 22,565  | 79.38% |

Canada showed better recovery management despite 20x more cases.

#### Q5.3 — Death Rates by Province in Canada
| | Province | Death Rate |
|--|---------|----------|
| Highest | Quebec | 3.01% |
| Lowest  | Prince Edward Island | 0.00% |

---

### ✅ Q6 — Data Transformation

#### Q6.1 — Wide to Long Format
- Transformed deaths dataset from wide to long format
- Shape after transformation: (136,344 rows x 6 columns)
- Each row represents one country on one specific date

#### Q6.2 — Total Deaths Per Country
USA led with highest total deaths followed by Brazil, Mexico and India.

#### Q6.3 — Top 5 Countries by Average Daily Deaths
USA, Brazil, India, Mexico and UK had highest average daily deaths.

#### Q6.4 — USA Death Milestones
| Milestone | Value |
|-----------|-------|
| First death | Feb 29, 2020 |
| Deaths by end of 2020 | 352,163 |
| Total deaths (May 2021) | 594,306 |

---

### ✅ Q7 — Data Merging

#### Q7.1 — Merged Dataset
- Merged all 3 datasets on Country/Region, Province/State and Date
- Final merged shape: (136,344 rows x 8 columns)
- Columns: Province/State, Country/Region, Lat, Long, Date, Confirmed, Deaths, Recovered

#### Q7.2 — Monthly Global Progression
| Month | Confirmed | Deaths | Recovered |
|-------|-----------|--------|-----------|
| Jan 2020 | 5,925 | 204 | 152 |
| Jun 2020 | 10,376,317 | 504,669 | 5,257,314 |
| Dec 2020 | 83,061,713 | 1,816,552 | 52,769,815 |
| May 2021 | 169,159,387 | 3,517,346 | 105,694,249 |

Cases doubled every 2 months through 2020.

#### Q7.3 — Monthly Analysis: USA, Italy and Brazil
- USA — Hit 1M cases by April 2020, stopped reporting recoveries in 2021
- Italy — First major European epicenter, flattened curve in summer 2020
- Brazil — Exploded from May 2020, 16.4M cases by May 2021

---

### ✅ Q8 — Combined Data Analysis

#### Q8.1 — Highest Average Death Rates in 2020
| Rank | Country | Avg Death Rate |
|------|---------|---------------|
| 1st | Yemen | 24.95% |
| 2nd | MS Zaandam | 21.90% |
| 3rd | Sudan | 10.37% |

Yemen's high rate due to collapsed healthcare system from ongoing civil war.

#### Q8.2 — South Africa: Recoveries vs Deaths
| Metric | Value |
|--------|-------|
| Total Confirmed | 1,659,070 |
| Total Deaths | 56,363 |
| Recovery Rate | 93.68% |
| Ratio | 27.6x more recoveries than deaths |

#### Q8.3 — USA Monthly Recovery Ratio (Mar 2020 — May 2021)
| Month | Recovery Ratio |
|-------|---------------|
| Mar 2020 | 3.7% |
| Oct 2020 | 39.41% (Highest) |
| Jan 2021+ | 0% (USA stopped reporting) |

October 2020 had the highest recovery ratio due to improved treatment protocols.

---

## 🔑 Key Insights
1. USA had the highest total cases and deaths globally
2. Yemen had the worst death rate due to collapsed healthcare
3. South Africa showed excellent recovery management (93.68%)
4. France experienced the highest single-day surge (117,900 cases)
5. Global cases doubled every 2 months throughout 2020
6. Recovery rates improved as doctors learned better treatment protocols

## 📂 Repository Structure
- covid19_analysis.ipynb — Main Jupyter Notebook
- covid_19_dataset.xlsx  — Dataset (3 sheets)
- README.md              — Project documentation

## 👤 Author
Your Name
