#### PS239T - An Introduction to Computational Tools and Techniques for Social Science Research
#### Henriette Ruhrmann
#### Final Project
#### April 25, 2018

## Short Description

Information and communications technology (ICT), and in particular web-based content, play an increasingly significant role in government transparency, communication, and service delivery. This developing digital public infrastructure is often referred to as “e-government,” defined by Fang (2002) as the employment of ICTs to provide access to government information and services, improve service quality, and expand opportunities for democratic engagement.

However, given the U.S.’ diverse population and persistent digital divide, the expansion of e-government risks perpetuating the marginalization of vulnerable population groups if government-sponsored web content is not fully accessible. In particular, temporary or permanent physical and sensory impairments may prevent individuals from using keyboard and screen or viewing web-based content. Moreover, the abundance of information available in natural text format may challenge individuals with low literacy levels. According to the latest survey of the National Center for Education Statistics (NCES), 23% of the adults in the U.S. demonstrate literacy skills at the lowest level, including individuals with low levels of education or disabilities, seniors, or immigrants with limited English proficiency.

In my final project, I assessed the accessibility of federal government websites for audiences with special needs across two dimensions, (a) their structural design and (b) their content readability. The structural design of a website refers to the logic of the code and markup that determines the organization and presentation of natural information such as text, images, or sound. My frame of reference for code-based website accessibility are the U.S. Section 508 standard and the international WCAG 2.0 standard. Content readability is the degree to which natural language text is accessible to audiences with literacy challenges based on five commonly used readability indices (Flesch Kincaid Reading Ease, Flesch Kincaid Grade Level, Gunning Fog Score, SMOG Index, Coleman Liau Index, and Automated Readability Index). The objective of the analysis is to gain a comprehensive understanding of the current state of government accessibility online. An in-depth understanding of current successes and challenges is crucial to develop strategies aimed at achieving fully inclusive e-government institutions and services.

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

#### References
AChecker. “IDI Web Accessibility Checker : Web Service API.” Accessed March 4, 2018. https://achecker.ca/documentation/web_service_api.php.

Dawes, Sharon S. “Stewardship and Usefulness: Policy Principles for Information-Based Transparency.” Government Information Quarterly, Special Issue: Open/Transparent Government, 27, no. 4 (October 1, 2010): 377–83. https://doi.org/10.1016/j.giq.2010.07.001.

Fang, Zhiyuan. E-Government in Digital Era: Concept, Practice, and Development, 2002.

Monica Anderson. “Digital Divide Persists Even as Lower-Income Americans Make Gains in Tech Adoption.” Pew Research Center (blog), March 22, 2017. http://www.pewresearch.org/fact-tank/2017/03/22/digital-divide-persists-even-as-lower-income-americans-make-gains-in-tech-adoption/.

National Center for Education Statistics (NCES). “Adult Literacy in America - A First Look at the Findings of the National Adult Literacy Survey,” April 2002. https://nces.ed.gov/pubs93/93275.pdf.

United Nations, ed. E-Government in Support of Sustainable Development. United Nations E-Government Survey 2016. New York, 2016. http://workspace.unpan.org/sites/Internet/Documents/UNPAN97453.pdf.

U.S. General Services Administration. “Section 508 Law and Related Laws and Policies.” GSA Government-wide Section 508 Accessibility Program. Accessed March 4, 2018. https://section508.gov/content/learn/laws-and-policies.

World Wide Web Consortium (W3C). “Web Content Accessibility Guidelines (WCAG) 2.0 - W3C Recommendation 11 December 2008,” December 11, 2008. https://www.w3.org/TR/WCAG20/.

