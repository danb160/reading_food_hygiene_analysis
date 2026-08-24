# Reading Food Hygiene Data Analysis - README

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

* **VS Code** Integrated Development Environment (IDE)

* **Python** Our core programming language (Version 3.12.8).

* **Pandas and Numpy** Used for cleaning, filtering, and organising data.

* **Matplotlib, Seaborn and Plotly** Used for building visualisations and charts

* **Jupyter Notebooks** Used as our interactive working environment

* **Google Gemini/Github Copilot** Generative AI tools were integrated into the workflow to assist with debugging, structuring Pandas operations, and branstorming ideas.

---
## How the project is organised

`data`: Data files used for the project:
- [UK Food Standards Agency - Open Data CSV](https://safhrsprodstorage.blob.core.windows.net/opendatafileblobstorage/FHRS_All_en-GB.csv) (This has been omitted due to github max file size)
- `data/reading_food_hygiene_data.csv` - Filtered Reading dataset
- `data/rfh_clean.csv` - Cleaned Reading dataset
- `data/target_list_RG1.csv` - Target dataset for RG1 (See below in Conclusion)

`jupyter_notebooks`: Notebooks used for the project:
- `jupyter_notebooks/reading_food_hygiene_prep.ipynb` - Data preparation and cleaning
- `jupyter_notebooks/rfh_analysis_and_visualisations.ipynb` - Data analysis and visualisation

---
## Methodology and Data Management

- **Data Reduction:** The FSA national dataset was taken and filtered down specifically to records for the Reading local authority.

- **Handling Missing Data:** Dropped rows missing required ratings, imputed missing values (addresses and postcodes) with Unknown to protect valid hygiene records.

**Feature Engineering:** Extracted postcode districts from full postcodes (e.g., RG1, RG2, RG30) to enable regional categorisation of businesses across Reading.

---

## Answers to our Key Analytical Questions:

1. **Target Volume:** How many food businesses in Reading are compliant versus non-compliant ones (ratings 0-2)?

**The Compliance Split:** Whilst the vast majority of food businesses have been rated as compliant (93.6%), there are a small target of 85 (which equate to the remaining 6.4%) businesses that are non-compliant which create our target establishments.

2. **Rating Breakdown:** Within the non-compliant businesses, what is the exact distribution of each rating (0, 1, 2)?

**Rating Severity:** Severe (*0 rated*) businesses are rare (5 of them), they are all situated in the RG1 area (4) and the RG2 area (1). Overall we can also identify, the rating scores of both *1 rating* (41) and *2 rating* (39) make up the bulk of the non-compliant businesses.

3. **Struggling Businesses:** Is there a specific type of business (such as takeaways, restaurants, pubs or retail) that account for the lowest ratings?

**Struggling Business Sectors** Retail shops, takeaways/sandwich shops, and restaurants/cafes experience the highest volume of failing scores.

4. **Geographic Distribution** Are low-rated businesses situated in specific areas across reading?

**Failure Rate** With only 54 food businesses in the RG6 area (Earley), and 10 being non-compliant the RG6 area has the highest failure rate at 18.52%.

**Geographic Hotspots:** The RG1 area (Katesgrove, Newtown, Reading (central)), contains the highest overall food business volume, and also the highest number of failing businesses overall (over double the total number of any other).

---
## Conclusion

Due to the results above, the commercial cleaning, pest control, and maintenance company would be best to target their resources into the RG1 (Katesgrove, Newtown, Reading (central)) areas.

While their approach could vary, taking the above in mind they could target their resources towards:

* **The RG1 Area** Specifically where there are the most non-compliant businesses

* **Business Types** Retail shops, takeaways/sandwich shops, and restaurants/cafes

* **Specific Businesses** Non-compliant businesses in the RG1 area saved to `data/target_list_RG1.csv`

---
## Recognised Limitations

- **Point-in-time Snapshot** - The food standards agency dataset that has been used for this project represents a specific snapshot in time when this project has been completed August 2026. Due to the raw file being dynamic (a live working document), it is subject to monthly change and updates.

- **Lack of Qualitative Context** - While low ratings indicate a need for improvement the data does not explicitly tell us the exact cause of the failure of the businesses.

---
## Data Compliance and Legal Use

The dataset used is publicly available open data published under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/) by the UK Food Standards Agency. As these records pertain to commercial businesses, they are exempt from standard GDPR restrictions permitting lawful use for use for research and commercial outreach.

---
## How to Run This Project

1. Clone this repository to your local machine
2. Install the required Python packages using your terminal:
```bash
pip install -r requirements.txt
