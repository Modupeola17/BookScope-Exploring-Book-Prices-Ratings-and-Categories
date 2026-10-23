# BookScope: Exploring Book Prices, Ratings and Categories

<img width="1210" height="685" alt="BookScope Dashboard" src="https://github.com/user-attachments/assets/4480de17-e6ad-4963-bf9a-0d7bb62af096" />


**An End-to-End Data Analytics Project**

BookScope is a data analytics project that explores book prices, ratings, availability and categories using data collected from [Books to Scrape](https://books.toscrape.com/).

The project demonstrates an end-to-end analytics workflow, from web scraping and data cleaning to exploratory data analysis, visualisation and interactive dashboard development.

The goal was to transform raw web data into meaningful insights and present the findings through an interactive Power BI dashboard.

## Introduction

Data analytics involves more than creating charts. It requires collecting data, assessing its quality, preparing it for analysis, identifying patterns and communicating findings clearly.

BookScope applies these principles to a dataset of 1,000 book records collected through web scraping. Python was used for data collection, pandas for cleaning and analysis, and Power BI for interactive visualisation.

The project explores three main areas:

- Book prices and their distribution.
- Star ratings and their frequencies.
- Differences in book prices and counts across categories.

## Story of the Data

The data was collected from [Books to Scrape](https://books.toscrape.com/), a demonstration website designed for practising web scraping.

The website contains book listings with information such as titles, prices, ratings and availability. These fields provided a foundation for exploring how the collected books were distributed across price ranges, rating levels and categories.

The project was guided by questions such as:

- What is the typical listed price of a book?
- Which star ratings appear most frequently?
- Is there a linear relationship between book price and rating?
- How do book counts and average prices differ across categories?
- How can the findings be presented in an interactive dashboard?

**Data context:** Books to Scrape is a practice website. Its prices and ratings should not be interpreted as verified real-world retail prices or actual customer satisfaction measurements.

## Data Journey and Structure

The project followed a structured data workflow.

1. **Web scraping:** Python Requests retrieved web pages, while BeautifulSoup parsed their HTML.
2. **Data extraction:** Book information was collected across 50 pages, producing 1,000 records.
3. **Data cleaning:** pandas was used to inspect and standardise values, convert data types and check missing values and repeated titles.
4. **Data enrichment:** Category information was added to support category-level analysis.
5. **Exploratory data analysis:** Descriptive statistics, distributions, correlations and category-level comparisons were examined.
6. **Data visualisation:** Charts were created in Python to communicate analytical findings.
7. **Dashboard development:** Power BI was used to build the interactive BookScope dashboard.

### Dataset Structure

The enriched dataset contains 1,000 rows and five main columns.

| Column | Description |
|---|---|
| `title` | The title of each book |
| `price` | The listed book price, stored numerically |
| `rating` | The star rating, converted to a numeric value from 1 to 5 |
| `availability` | The availability information displayed on the website |
| `category` | The book's category |

The raw and cleaned datasets were kept separate to preserve the original extracted records and make the cleaning process easier to trace.

## Data Splitting and Preprocessing

The raw dataset was preserved separately from the cleaned dataset. The cleaned data was then used for exploratory analysis and dashboard development.

The preprocessing steps included:

- Removing unwanted characters from price values.
- Converting prices into numeric data types.
- Mapping written star ratings to integers from 1 to 5.
- Inspecting missing values and data types.
- Reviewing repeated titles rather than automatically removing records based on title alone.
- Enriching category information where possible.
- Standardising the final dataset for analysis and visualisation.

After category enrichment, 67 records had missing category values across 49 distinct non-missing categories. These missing values were retained where categories could not be reliably established.

## Pre-Analysis

Before interpreting the data, I examined the dataset's dimensions, column names, data types, missing values and repeated titles.

This stage helped establish the dataset's condition and identify issues that could affect calculations or visualisations.

Checking the structure of the data before analysis also helped ensure that price and rating fields were suitable for numerical calculations.

## In-Analysis

Exploratory data analysis was used to understand the distribution of book prices and ratings and to investigate relationships between numerical variables.

### 1. Book Price Analysis

| Statistic | Result |
|---|---:|
| Number of books | 1,000 |
| Mean price | £35.07 |
| Median price | £35.98 |
| Minimum price | £10.00 |
| Maximum price | £59.99 |
| Standard deviation | £14.45 |
| First quartile (Q1) | £22.11 |
| Third quartile (Q3) | £47.46 |

The mean price was slightly lower than the median. The observed prices ranged from £10.00 to £59.99, with a standard deviation of £14.45.

These statistics provide a summary of price distribution within the collected practice dataset.

### 2. Rating Analysis

| Rating | Number of books |
|---|---:|
| 1 star | 226 |
| 2 stars | 196 |
| 3 stars | 203 |
| 4 stars | 179 |
| 5 stars | 196 |
| **Total** | **1,000** |

The average rating was **2.92 out of 5**. The median rating was 3, while the mode was 1.

One-star books formed the largest individual rating group, with 226 records. Four-star books formed the smallest group, with 179 records.

### 3. Price and Rating Relationship

The calculated correlation between price and rating was approximately **0.028**.

This value is very close to zero, indicating almost no linear relationship between price and rating in the collected dataset.

The result does not establish that price and quality are unrelated. The analysis is descriptive, and the source website's ratings are practice data rather than verified measures of customer satisfaction.

### 4. Category-Level Analysis

Category-level analysis was used to compare book counts and average prices across groups.

In the enriched analysis, the categories with the highest record counts included Default, with 152 records; Nonfiction, with 110; and Sequential Art, with 75.

Fantasy had an average listed price of £39.59, while Food and Drink had an average listed price of £31.41 among the categories included in that analysis.

These results illustrate how grouping records by category can reveal differences that may not be apparent from individual book listings.

### 5. Outlier Analysis

The interquartile range (IQR) method was used to identify potential price outliers.

The calculated lower and upper bounds were approximately -£15.92 and £85.48. All observed prices fell within these bounds.

Therefore, **no price outliers were identified using the 1.5 × IQR rule**.

This conclusion applies to the selected statistical method; it does not guarantee that every source value is error-free.

## Post-Analysis and Data Visualisations

Visualisations were created to make the results easier to understand and compare.

The Python analysis included:

- Bar chart of book ratings.
- Pie chart of rating distribution.
- Histogram of book prices.
- Scatter plot of price against rating.
- Box plot of prices by rating.
- Heatmap of numerical relationships.
- Line chart of average price by rating.
- Category-level price comparisons.
- Charts of the highest-priced and lowest-priced books.

### The BookScope Power BI Dashboard

The final dashboard brings key metrics and visualisations together in one interactive interface.

Its components include:

- KPI cards for total books, average price, average rating and price range.
- Number of books by star rating.
- Share of books by rating.
- Average book price by rating.
- Category comparisons.
- Book distribution by category.
- Book price distribution.
- Filters for category, rating and availability.

The filters allow users to explore the dataset from different perspectives without manually changing the underlying data.

## Key Significant Limitations

Several limitations should be considered when interpreting the findings.

- **Practice data:** The website is intended for scraping practice, so the results are not representative of verified real-world book-market conditions.
- **Missing categories:** Some records did not have reliably established category values.
- **Repeated titles:** A repeated title is not automatically an accidental duplicate; records require appropriate review.
- **Limited variables:** The dataset does not provide verified sales volumes, transaction histories or detailed customer-review information.
- **Descriptive analysis:** The findings identify distributions and relationships but do not establish causation.
- **Source dependence:** The analysis depends on the information available on the website and the quality of the extraction and enrichment process.

## Recommendations and Conclusion

BookScope demonstrates how web scraping, data cleaning, exploratory analysis and visualisation can be combined into a complete data analytics workflow.

For a real retail application, a similar approach could be extended to investigate pricing patterns, product availability, category performance and customer reviews using verified data.

Future improvements could include:

1. Collecting verified retail data from sources that permit its use.
2. Adding sales or transaction data where available.
3. Tracking prices over time.
4. Improving category coverage and documenting missing-value handling.
5. Comparing multiple data sources.
6. Validating dashboard calculations and aggregations against the underlying dataset.

The project reinforced the importance of checking data quality, selecting appropriate analytical methods and communicating findings within the limits of the available evidence.

## Final Summary

BookScope is an end-to-end data analytics project that combines web scraping, pandas preprocessing, exploratory data analysis, Python visualisation and Power BI dashboard development.

The project collected 1,000 book records and explored their prices, ratings and categories. The analysis found a mean price of £35.07, an average rating of 2.92 out of 5 and an almost negligible linear correlation between price and rating.

Beyond the numerical findings, the project provided practical experience in transforming raw web data into an organised dataset, analysing it systematically and presenting the results through an interactive dashboard.

## Tools and Technologies

- **Python** — programming and data collection.
- **Requests** — retrieving web pages.
- **BeautifulSoup** — parsing HTML and extracting information.
- **pandas** — data cleaning, transformation and analysis.
- **Matplotlib** — data visualisation.
- **Seaborn** — statistical visualisation.
- **Power BI** — interactive dashboard development.
- **Jupyter Notebook** — documenting and running the analysis.

## References and Appendices

### References

1. Books to Scrape — https://books.toscrape.com/
2. Requests documentation — https://requests.readthedocs.io/
3. Beautiful Soup documentation — https://www.crummy.com/software/BeautifulSoup/bs4/doc/
4. pandas documentation — https://pandas.pydata.org/docs/
5. Matplotlib documentation — https://matplotlib.org/stable/
6. Seaborn documentation — https://seaborn.pydata.org/
7. Microsoft Power BI documentation — https://learn.microsoft.com/power-bi/

### Appendices

Supporting project files attached include:

- Python web-scraping script.
- Jupyter Notebook.
- Raw dataset
- Cleaned dataset 
- Python-generated visualisations.
- Power BI dashboard file 
("C:\Users\HP\Downloads\Web_Scraping_Project")

These materials provide supporting evidence for the workflow and findings described in this README.
