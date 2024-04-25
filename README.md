# WikiDataBreachAnalysis

The compiled dataset can be found at: https://data.world/davdoan/wiki-list-of-data-breaches
OR under the CleanData.csv file

This project scrapes the Wikipedia page "List of data breaches" (https://en.wikipedia.org/wiki/List_of_data_breaches) and compiles the tabled contents into a pandas object for statistical analysis. Because the sourced data is from Wikipedia, many entries have unconventional descriptions, so many entries will be removed during the transformation phase (about 50). A reference link describing where these entries originated from is included within the table, derived from the same Wikipedia page. The Wikipedia page includes 390 data entries total, each with 5 attributes for analysis (the company name, the year of the incident, the number of user records affected, the type of organization, and why the company was compromised). Later, I will analyze these attributes to gain deeper insight.
