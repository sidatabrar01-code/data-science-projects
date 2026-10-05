# Netflix Movies and TV Shows — Data Acquisition, Cleaning & EDA

## Project Overview

This project focuses on the fundamental stages of a Data Science workflow: **data acquisition, data cleaning, preprocessing, and exploratory data analysis (EDA)**.

The analysis is performed on a publicly available **Netflix Movies and TV Shows dataset** using Python. The objective is to understand the structure and quality of the dataset, identify missing and duplicate records, prepare the data for analysis, and discover meaningful patterns through statistical analysis and visualization.

This project was completed as part of **Week 1: Data Acquisition, Cleaning, and Exploratory Analysis**.

---

## Objectives

The main objectives of this project are:

- Acquire and load a publicly available dataset.
- Understand the structure and characteristics of the dataset.
- Identify missing values and duplicate records.
- Perform data cleaning and preprocessing.
- Analyze categorical and numerical variables.
- Generate meaningful visualizations.
- Identify important patterns and trends.
- Document the complete data preparation and EDA process.

---

## Dataset

The dataset contains information about Netflix movies and TV shows.

### Dataset Statistics

| Property | Value |
|---|---:|
| Initial Records | 6,234 |
| Number of Columns | 12 |
| Content Types | Movies, TV Shows |
| Duplicate Records | 0 |
| Dataset Format | CSV |

### Important Features

| Column | Description |
|---|---|
| `show_id` | Unique identifier for each title |
| `type` | Movie or TV Show |
| `title` | Name of the title |
| `director` | Director information |
| `cast` | Cast information |
| `country` | Country associated with the title |
| `date_added` | Date the title was added to Netflix |
| `release_year` | Original release year |
| `rating` | Content rating |
| `duration` | Movie duration or number of TV seasons |
| `listed_in` | Genres/categories |
| `description` | Description of the title |

---

## Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook / Google Colab**

---

## Project Workflow

The project follows the standard data preparation pipeline:

```text
Dataset Acquisition
        ↓
Initial Data Inspection
        ↓
Missing Value Analysis
        ↓
Duplicate Detection
        ↓
Data Cleaning
        ↓
Data Preprocessing
        ↓
Exploratory Data Analysis
        ↓
Data Visualization
        ↓
Insights & Conclusions
```

---

## 1. Data Acquisition

The Netflix dataset was loaded into a Pandas DataFrame from a CSV file.

```python
import pandas as pd

df = pd.read_csv("netflix_titles.csv")

print(df.shape)
df.head()
```

The initial dataset contained:

```text
6,234 rows × 12 columns
```

---

## 2. Initial Data Inspection

Several techniques were used to understand the dataset:

```python
df.head()
df.tail()
df.shape
df.columns
df.info()
df.describe()
```

The inspection helped identify:

- Number of records
- Number of features
- Data types
- Numerical distributions
- Categorical variables
- Potential missing values
- Structure of the dataset

---

## 3. Missing Value Analysis

Missing values were identified using Pandas.

```python
missing_values = df.isnull().sum()

print(missing_values)
```

Missing-value percentages were also calculated to understand the severity of missing information in each column.

The largest amount of missing information was observed in fields such as:

- `director`
- `cast`
- `country`

These fields were handled according to their role in the analysis rather than replacing missing information with fabricated values.

---

## 4. Duplicate Detection

The dataset was checked for duplicate records.

```python
duplicates = df.duplicated().sum()

print("Number of duplicate rows:", duplicates)
```

### Result

```text
Number of duplicate rows: 0
```

Therefore, no duplicate records needed to be removed.

---

## 5. Data Cleaning and Preprocessing

The cleaning stage focused on preparing the dataset for exploratory analysis.

The process included:

- Checking missing values
- Checking duplicate records
- Reviewing data types
- Converting date-related fields where required
- Creating useful date-based features
- Preparing categorical variables
- Handling incomplete records according to analytical requirements

For example:

```python
df["date_added"] = pd.to_datetime(
    df["date_added"],
    errors="coerce"
)

df["year_added"] = df["date_added"].dt.year
df["month_added"] = df["date_added"].dt.month
```

Creating additional features makes it possible to perform time-based analysis of Netflix content.

---

# Exploratory Data Analysis

## 6. Movies vs TV Shows

The `type` column was analyzed to compare the number of Movies and TV Shows.

```python
df["type"].value_counts()
```

This analysis shows the composition of the Netflix catalog represented by the dataset.

---

## 7. Release Year Analysis

The distribution of `release_year` was examined to understand the historical range of titles.

```python
df["release_year"].describe()
```

A histogram was also used to visualize the distribution.

```python
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 5))

plt.hist(
    df["release_year"],
    bins=30
)

plt.title("Distribution of Release Years")
plt.xlabel("Release Year")
plt.ylabel("Number of Titles")

plt.show()
```

---

## 8. Content Ratings

The distribution of Netflix content ratings was explored to understand the types of content present in the dataset.

```python
df["rating"].value_counts()
```

A visualization was created to make the distribution easier to interpret.

---

## 9. Genre Analysis

The `listed_in` column was examined to identify frequently occurring genres and categories.

```python
df["listed_in"].value_counts()
```

Because a title can belong to multiple categories, genre analysis can be further improved by splitting the comma-separated values into individual categories.

---

## 10. Duration Analysis

The `duration` column contains different types of information:

- Movie duration in minutes
- Number of seasons for TV Shows

Therefore, Movies and TV Shows should be analyzed separately rather than treating duration as a single numerical variable.

---

# Visualizations

The project includes visualizations for understanding:

1. Missing values
2. Movies vs TV Shows
3. Release-year distribution
4. Content ratings
5. Country distribution
6. Genre distribution
7. Movie duration
8. TV Show seasons
9. Content added over time
10. Relationships between selected numerical variables

Example:

```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 6))

sns.countplot(
    data=df,
    x="type"
)

plt.title("Movies vs TV Shows")
plt.xlabel("Content Type")
plt.ylabel("Number of Titles")

plt.show()
```

---

# Key Insights

The analysis produced several important observations:

- The dataset contains **6,234 Netflix titles** across **12 columns**.
- The dataset includes both **Movies and TV Shows**.
- No duplicate records were identified.
- Missing information is concentrated mainly in the `director`, `cast`, and `country` fields.
- The dataset covers titles released across a wide range of years.
- Netflix content can be analyzed using multiple dimensions including content type, release year, rating, country, genre, and duration.
- Movie duration and TV Show duration require separate treatment because they represent different concepts.

---

# Data Quality Considerations

Several considerations were identified during the analysis:

### Missing Data

Some columns contain substantial missing information. Missing values should be handled according to the purpose of the analysis instead of blindly replacing them.

### Multiple Values in a Single Column

Fields such as `country` and `listed_in` may contain multiple values in a single record.

For advanced analysis, these fields can be normalized into separate rows.

### Duration

The `duration` column represents:

```text
Movie → Duration in minutes
TV Show → Number of seasons
```

Therefore, it should not be treated as one common numerical feature.

---

# Project Structure

```text
Netflix-Data-Analysis/
│
├── netflix_titles.csv
│
├── netflix_analysis.ipynb
│
├── Week_1_Netflix_Data_Analysis_Report.docx
│
└── README.md
```

---

# Future Improvements

The project can be extended by:

- Performing detailed country-wise analysis.
- Performing advanced genre analysis.
- Creating separate movie and TV-show datasets.
- Building interactive dashboards.
- Performing statistical hypothesis testing.
- Applying clustering techniques.
- Building a Netflix recommendation system.
- Performing Natural Language Processing on title descriptions.
- Developing machine-learning models based on the dataset.

---

# Conclusion

This project demonstrates the essential first steps of a Data Science workflow using a real-world Netflix dataset.

The dataset was acquired, inspected, analyzed for missing and duplicate records, cleaned where appropriate, and explored using statistical techniques and visualizations.

The analysis provides a strong foundation for further work involving **data visualization, statistical analysis, machine learning, recommendation systems, and natural language processing**.

---

## Author

**Abrar Sidat**

Computer Science and Engineering  
Ghousia College of Engineering, Ramanagaram, Karnataka, India

---

## Project Type

**Data Science | Data Cleaning | Exploratory Data Analysis | Python**

---

## License

This project is intended for educational and learning purposes.
