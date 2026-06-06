# 🎬 Netflix Content Strategy — Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-1.5+-green?logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

An end-to-end Exploratory Data Analysis of the Netflix Titles Dataset (8,807 titles) using Python.  
The goal is to uncover content trends, audience targeting patterns, and geographic distribution insights that explain Netflix's growth strategy.

---

## 📊 Key Findings

| # | Insight | Finding |
|---|---------|---------|
| 1 | **Content surge** | Netflix added **70% of its entire library after 2016** — a clear strategic pivot |
| 2 | **Movies dominate** | Movies make up **~69%** of content vs 31% TV Shows |
| 3 | **Top producer** | **USA (36%)** leads content production; **India is #2 at 11%** |
| 4 | **Peak release months** | **July and December** consistently see the highest content additions |
| 5 | **Target audience** | **TV-MA and TV-14** are the dominant ratings — Netflix skews adult |
| 6 | **Top genre** | **International Movies** is the #1 genre, reflecting Netflix's global push |
| 7 | **Content shift** | TV Show additions grew **3x faster** than Movies between 2018–2020 |

---

## 📂 Dataset

- **Source:** [Netflix Titles Dataset — Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)
- **Size:** 8,807 rows × 12 columns
- **Features:** title, type, director, cast, country, date_added, release_year, rating, duration, listed_in, description

---

## 🛠️ Tools & Libraries

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading, cleaning, manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Base visualizations |
| `seaborn` | Statistical plots and styling |
| `wordcloud` | Genre frequency visualization |
| `jupyter notebook` | Interactive analysis environment |

---

## 📁 Project Structure

```
netflix-eda/
│
├── netflix_eda_analysis.ipynb    # Main analysis notebook
├── netflix_titles.csv            # Dataset (download from Kaggle)
├── plots/                        # Saved chart images
│   ├── content_growth.png
│   ├── movies_vs_shows.png
│   ├── top_countries.png
│   ├── monthly_additions.png
│   ├── rating_distribution.png
│   └── genre_wordcloud.png
├── requirements.txt
└── README.md
```

---

## 🔍 Analysis Sections

### 1. Data Cleaning
- Handled **missing values** in `country`, `date_added`, and `rating` columns
- Parsed `date_added` into `year_added` and `month_added` features
- Removed duplicates and standardised text columns
- Final clean dataset: **~8,600 usable rows**

### 2. Content Type Distribution
- Pie chart and bar chart showing Movies vs TV Shows split
- **Finding:** Netflix is primarily a movie platform but is actively growing its TV Show catalogue

### 3. Content Growth Over Time
- Line chart of titles added per year (2008–2021)
- **Finding:** Exponential growth from 2016 onwards — Netflix's content investment strategy is clearly visible in the data

### 4. Geographic Analysis
- Horizontal bar chart of top 10 content-producing countries
- **Finding:** USA dominates but India's rapid rise signals a major market push

### 5. Monthly Release Patterns
- Bar chart of titles added by month
- **Finding:** July (summer holidays) and December (festive season) are Netflix's preferred release windows

### 6. Audience Rating Analysis
- Distribution of content ratings (G, PG, PG-13, TV-MA, TV-14, etc.)
- **Finding:** Adult content (TV-MA + TV-14) accounts for over 60% of the catalogue

### 7. Genre Analysis (WordCloud)
- WordCloud of `listed_in` categories
- **Finding:** International Movies, Dramas, and Comedies are the three dominant genres

---

## 💡 Business Recommendations

Based on the analysis, here are data-driven recommendations for Netflix's content strategy:

**1. Double down on TV Shows**  
TV Show additions grew 3x faster than Movies between 2018–2020. Binge-watching behaviour strongly favours multi-season originals — this is where Netflix should continue investing for subscriber retention.

**2. Expand Indian and regional content**  
India is the #2 content-producing country but regional language content (Hindi, Tamil, Telugu) remains underrepresented in top genres. Localised originals are a clear growth lever for the South Asian market.

**3. Optimise release timing**  
July and December are peak content windows — likely timed to school/college holidays. Marketing teams should align major title launches with these months for maximum subscriber impact.

**4. Family content is an untapped opportunity**  
TV-G and TV-Y content (family/kids) is heavily underrepresented relative to adult content. With increasing competition from Disney+, family programming is a strategic white space for Netflix.

**5. Leverage International Movies category**  
International Movies is the #1 genre — Netflix's global audience is actively seeking non-English content. Investing in subtitling and dubbing of regional titles can accelerate this further.

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/sidatabrar01-code/data-science-projects.git
cd data-science-projects
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Download the dataset**  
Download `netflix_titles.csv` from [Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows) and place it in the project root folder.

**4. Run the notebook**
```bash
jupyter notebook netflix_eda_analysis.ipynb
```

---

## 📋 Requirements

```
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
wordcloud>=1.9.0
jupyter>=1.0.0
```

---

## 📈 Sample Visualizations

> *(Add your chart screenshots here after running the notebook)*  
> Drag and drop images into this section on GitHub, or reference files from the `plots/` folder:

```markdown
![Content Growth Over Time](plots/content_growth.png)
![Top Countries](plots/top_countries.png)
![Genre WordCloud](plots/genre_wordcloud.png)
```

---

## 🎯 Skills Demonstrated

- **Data Cleaning** — handling nulls, parsing dates, deduplication  
- **Exploratory Data Analysis** — univariate, bivariate, and time-series analysis  
- **Data Visualisation** — bar charts, line charts, pie charts, heatmaps, WordCloud  
- **Business Thinking** — translating data insights into actionable recommendations  
- **Python Libraries** — Pandas, NumPy, Matplotlib, Seaborn  

---

## 👤 About Me

**Sidat Abrar Idrish**  
3rd Year CSE Student | Aspiring Data Scientist  
📍 Karnataka, India

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/sidat-abraridrish-06026225a)
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-black?logo=github)](https://github.com/sidatabrar01-code)
[![Credly](https://img.shields.io/badge/Credly-Certifications-orange?logo=credly)](https://www.credly.com/users/sidat-abraridrish)

---

*If you found this project useful, please consider giving it a ⭐ — it helps others discover it!*
