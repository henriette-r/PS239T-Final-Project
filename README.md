#### PS239T - An Introduction to Computational Tools and Techniques for Social Science Research
#### Henriette Ruhrmann
#### Final Project
#### April 25, 2018

## Short Description

In my final project, I assessed the accessibility of federal government websites for audiences with special needs across two dimensions, (a) their structural design and (b) their content readability. The structural design of a website refers to the logic of the code and markup that determines the organization and presentation of natural information such as text, images, or sound. My frame of reference for code-based website accessibility are the U.S. Section 508 standard and the international WCAG 2.0 standard. Content readability is the degree to which natural language text is accessible to audiences with literacy challenges based on five commonly used readability indices. The objective of the analysis is to gain a comprehensive understanding of the current state of government accessibility online. An in-depth understanding of current successes and challenges is crucial to develop strategies aimed at achieving fully inclusive e-government institutions and services.

To realize my research plan, I selected the sample of the 100 most relevant federal government websites (based on the number of users) to be analyzed. My data collection, organization, analysis, and visualization process included the following steps:

1. Generate an error summary report for each website through the AChecker Web Accessibility _API_
2. Obtain a natural language text sample of around 150 words from each website through _webscraping_
3. Calculate readability scores for each website based on the five most commonly used readability indices using _text analysis_
5. Creating a variety of different graphs illustrating my results through _data visualization_


## Dependencies (Software)

* R                               (Version 3.4.3 (2017-11-30) _Kite-Eating Tree_)
* AChecker Web Accessibility API (https://achecker.ca/documentation/web_service_api.php)


## Files
List of all files contained in the repo:


#### Data
* _popular-gov-sites.csv_: The base dataset of the 100 federal government website with the highest number of users in the 30 days prior to April 11, 2018 (downloaded from https://analytics.usa.gov/data, main variables of interest: domain, users, url, scraper_url (manually added), category (manually added))

* _ipums.csv_: The IPUMS dataset containing observations from the 2015 American Communities Survey (downloaded from https://usa.ipums.org/usa/, main variable of interest: EDUC)

* _01_api_gov_sites_df.csv_: The base dataset augmented with the summary error report collected through the web accessibility API

* _02_webscraping_gov_sites_df.csv_: The dataset created in step (1) augmented with the 150-word natural language text sample obtained through webscraping

* _03_text_analysis_gov_sites_df.csv_: The dataset created in step (1) and (2) augmented with the readability scores calculated for each website through text analysis


#### Code
* _01_data_collection_api.Rmd (+html)_: Collects data through the web accessibility API to the file _01_api_gov_sites_df.csv_
* _02_data_collection_web_scraping.Rmd (+html)_: Collects data through the webscraping to the file _02_webscraping_gov_sites_df.csv_
* _03_text_analysis.Rmd (+html)_: Analyzes collected data and exports to the file _03_text_analysis_gov_sites_df.csv_
* _04_data_visualizations.Rmd (+html)_: Visualizes collected and analyzed data and exports PNG files to Results


#### Results
* _bar_ws.png_: Illustrates the number of users of websites assigned to each of 10 categories
* _hist_ed.png_: Illustrates the distribution of the levels of literacy required to read website content
* _hist_ws.png_: Illustrates the distribution of the levels of literacy in the U.S. population
* _pie_categories.png_: Illustrates the share of websites in each of 10 categories
* _pie_errors.png_: Illustrates the share of websites with a certain number of structural accessibility errors
* _violin_sc_an.png_: Compares the distribution of readability scores across five readability indices (annotated)
* _violin_sc.png_: Compares the distribution of readability scores across five readability indices
* _violin_ws.png_: Illustrates the distribution of readability scores by website category
* _waffle.png_: Illustrates the results of the structural accessibility test

