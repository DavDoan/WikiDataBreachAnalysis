# WikiDataBreachAnalysis

The compiled dataset can be found under the CleanData.csv file

Source of data: https://en.wikipedia.org/wiki/List_of_data_breaches
License: Creative Commons Attribution-ShareAlike License 4.0 (More details can be found here: https://creativecommons.org/licenses/by-sa/4.0/deed.en)

This project scrapes the Wikipedia page "List of data breaches" (https://en.wikipedia.org/wiki/List_of_data_breaches) and compiles the tabled contents into a pandas object for statistical analysis.

The goal of this project is to analyze the open-sourced Wikipedia page and see if there are any trends found within publicly available data. How often are companies being compromised and how large is the impact?

The project has some issues in data collection and analysis. First, because the data source is Wikipedia and there is no standard unit to input data, many entries have unconventional descriptions that cannot be analyzed, so many entries will be removed during the transformation phase (about 50). Second, these data entries come from public articles that people know about, but hundreds more data breaches occur privately outside the public eye. Because of this, the impact of data breaches may be much higher and occur much more frequently than suggested by the table in Wikipedia. In the dataset, a reference link describing where these entries originated from is included within the table, derived from the same Wikipedia page. The Wikipedia page includes 390 data entries total, each with 5 attributes for analysis (the company name, the year of the incident, the number of user records affected, the type of organization, and why the company was compromised). Later, I will analyze these attributes to gain deeper insight.

Data dictionary:

raw_yield_data.csv
- index (integer) - A column used to index data by the pandas library in Python.
- company (string) - The name of an organization/entity that experienced a data breach.
- year (string) - This column includes the range of years a data breach occurred like "2014 - 2015"
- number_of_records_affected (string) - This column has many descriptions of records like "tens of thousands" or "250 locations" mixed with numerical values with comma separators like "3,000,000,000"
- organization_type (string) - This column includes a word that describes what kind of sector/field and organization works in, like "healthcare" or "military"
- reasons_for_breach (string) - This column includes the reasons for a company's breach, like "ransomware" or "accidentally published"
- reference_link_s (string) - This column includes bracketed numbers that refer to the corresponding reference hyperlink within the Wikipedia page, like "[3][4]"

clean_yield_data.csv
- index (integer) - A column used to index data by the pandas library in Python.
- company (string) - The name of an organization/entity that experienced a data breach.
- year (string) - The year a data breach incident was initiated, like "2004"
- number_of_records_affected (decimal) - The number of records that were exposed as a result of a data breach, like 3000000000
- organization_type (list of strings) - A list of string values that describe what kind of sector/field and organization works in, like ['tech', 'retail']
- reasons_for_breach (list of strings) - A list of string values that describe the reasons for a company's breach, like ['improper setting', 'hacked']
- reference_link_s (list of strings) - A list of string values that include the actual hyperlinks that point towards the articles that describe the data entry, provided on the Wikipedia page.

Dependencies: Libraries utilized are mentioned at the beginning of the CompanyBreachAnalysis.ipynb file
