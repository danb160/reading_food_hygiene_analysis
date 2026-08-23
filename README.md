# Reading Food Hygiene Data Analysis

This is an exploratory data analysis project of food ratings using publicly available Food Standards Agency data.
It will document a real-life business scenario, and answer some key analytical questions using both the data and data analysis tools, to lead us to an overall data-led conclusion.

---

## Business Context
A commercial cleaning, pest control, and maintenance company is looking to generate new business by targeting low performing food businesses in Reading, Berkshire, UK.

The initial realisation is that the national raw data file is extremely large with 611521 rows of data, 23 columns, and 140mb of data. This will need to be reduced by extracting only the columns needed for anaysis, for the Reading area specifically.
* **Data Source:** [UK Food Standards Agency - Open Data CSV](https://safhrsprodstorage.blob.core.windows.net/opendatafileblobstorage/FHRS_All_en-GB.csv)

Instead of targeting every food business blindly, the plan is to narrow down the national dataset, to the 1320 food business situated in Reading, and then to a smaller targeted number which can be targeted for advertising or face-to-face visits to offer business services.

The goal will be to narrow down the total number of businesses to those with a food rating of 0, 1 or 2 (which the [Food Standards Agency indicates 'Improvement is Necessary'](https://www.gov.uk/government/publications/food-hygiene-rating-scheme-fhrs-guidance-for-businesses/food-hygiene-rating-scheme-fhrs-guidance-for-businesses)).

While a low rating does not explicitly pinpoint a specific failure, it is a strong indicator that these businesses are a prime target for cleaning, pest control, or maintenance services to be offered.

---

### Key Analytical Questions
1. **Target Volume:** How many food businesses in Reading are compliant versus non-compliant ones (ratings 0-2)?
2. **Rating Breakdown:** Within the non-compliant businesses, what is the exact distribution of each rating (0, 1, 2)?
3. **Struggling Businesses:** Is there a specific type of business (such as takeaways, restaurants, pubs or retail) that account for the lowest ratings?
4. **Geographic Distribution** Are low-rated businesses situated in specific areas across reading?