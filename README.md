# Reading Food Hygiene Data Analysis

This is an exploratory data analysis project of food ratings using publicly available Food Standards Agency data.
It will document a real-life business scenario, and answer some key analytical questions using both the data and data analysis tools, to lead us to an overall data-led conclusion.


## Business Context

A commercial cleaning, pest control, and maintenance company is looking to generate new business by targeting low performing food businesses in Reading, Berkshire, UK.

The initial realisation is that the national raw data file is extremely large with 611521 rows of data, 23 columns, and 140mb of data. This will need to be reduced by extracting only the columns needed for anaysis, for the Reading area specifically.
* **Data Source:** [UK Food Standards Agency - Open Data CSV](https://safhrsprodstorage.blob.core.windows.net/opendatafileblobstorage/FHRS_All_en-GB.csv)

Instead of targeting every food business blindly, the plan is to narrow down the national dataset, to the 1320 food business situated in Reading, and then to a smaller targeted number which can be targeted for advertising or face-to-face visits to offer business services.

The goal will be to narrow down the total number of businesses to those with a food rating of 0, 1 or 2 (which the [Food Standards Agency indicates 'Improvement is Necessary'](https://www.gov.uk/government/publications/food-hygiene-rating-scheme-fhrs-guidance-for-businesses/food-hygiene-rating-scheme-fhrs-guidance-for-businesses)).

While a low rating does not explicitly pinpoint a specific failure, it is a strong indicator that these businesses are a prime target for cleaning, pest control, or maintenance services to be offered.

---
## Key Analytical Questions

1. **Target Volume:** How many food businesses in Reading are compliant versus non-compliant ones (ratings 0-2)?

2. **Rating Breakdown:** Within the non-compliant businesses, what is the exact distribution of each rating (0, 1, 2)?

3. **Struggling Businesses:** Is there a specific type of business (such as takeaways, restaurants, pubs or retail) that account for the lowest ratings?

4. **Geographic Distribution** Are low-rated businesses situated in specific areas across reading?

---
## Tools and Technology Used

**VS Code** Integrated Development Environment (IDE)
**Python** Our core programming language (Version 3.12.8).
**Pandas and Numpy** Used for cleaning, filtering, and organising data.
**Matplotlib, Seaborn and Plotly** Used for building visualisations and charts
**Jupyter Notebooks** Used as our interactive working environment

---
## How the project is organised

`data`: Data files used for the project.
- [UK Food Standards Agency - Open Data CSV](https://safhrsprodstorage.blob.core.windows.net/opendatafileblobstorage/FHRS_All_en-GB.csv) (This has been omitted due to github max file size)
- `data/reading_food_hygiene_data.csv` - Filtered Reading dataset
- `data/rfh_clean.csv` - Cleaned Reading dataset

---
**Methodology and Data Management**

- **Data Reduction:** The FSA national dataset was taken and filtered down specifically to records for the Reading local authority.

- **Handling Missing Data:** Dropped rows missing required ratings, imputed missing values (addresses and postcodes) with Unknown to protect valid hygiene records.

**Feature Engineering:** Extracted postcode districts from full postcodes (e.g., RG1, RG2, RG30) to enable regional categorisation of businesses across Reading.

---
**Using the analysis and a variety of different chart types, they show:**

* **The Compliance Split:** Whilst the vast majority of food businesses have been rated as compliant (93.6%), there are a small target of 85 (which equate to the remaining 6.4%) businesses that are non-compliant which create our target establishments.

* **Struggling Sectors** Retail shops, takeaways/sandwich shops, and restaurants/cafes experience the highest volume of failing scores.

* **Rating Severity:** Severe (0 rated) businesses are rare (5 of them), they are all situated in the RG1 area (4) and the RG2 area (1). Overall we can also identify, the rating scores of both 1 and 2 make up the bulk of the non-compliant businesses.

* **Failure Rate** With only 54 food businesses in the RG6 area (Earley), and 10 being non-compliant the RG6 area has the highest failure rate at 18.52%.

* **Geographic Hotspots:** The RG1 area (Katesgrove, Newtown, Reading (central)), contains the highest overall food business volume, and also the highest number of failing businesses overall (over double the total number of any other).

