# Visualizations


This is a collection of multiple projects in which I use python for data cleaning and initial analysis, then use tableau to create
visualizations. Currently, the following projects are included: 

## NYT bestsellers

In this project, I analyzed the collected New York Times (NYT) bestseller list data from 2008 - 2018.  
These data are available from the NYT API website, I used a file that was made available at https://www.kaggle.com/cmenca/new-york-times-hardcover-fiction-best-sellers/version/1

Short summary of the preprocessing:

The data consist of entries on the bestseller list, with book titles, author names, publishers and relative ranks. They are presumably manually entered, and some fields, particularly the publisher, have a number of spelling variants. I used an approach based on Levenshtein string distance to flag likely variant spellings, then replaced these with the most common spelling as appropriate. 
The books also have short descriptions, and I used keyword detection to try to infer the genre/theme of books from these descriptions. 
Finally, I collapsed the multiple entries per week on the bestseller list into a single entry per unique book.

After preprocessing, I visualized the data using Tableau. The visualization can be found at https://public.tableau.com/profile/cjstoneking#!/vizhome/NYT_bestsellers/Dashboard1

here is a preview image:


![NYT_bestsellers](NYT_bestsellers/NYT_bestsellers_image.png?raw=true)


## USA manufacturing

In this project, I take a large dataset from the 2012 US Census and use it to get a better understanding of how different manufacturing areas are represented in different US states. This involves several steps of preprocessing in Python, followed by visualization in Tableau.  The finished visualization can be found at https://public.tableau.com/profile/cjstoneking#!/vizhome/US_manufacturing_2012/Dashboard1, 

here is a preview image:

![tableau_USA_manufacturing](USA_manufacturing/usa_manufacturing_small.png?raw=true)



The dataset consists of numbers of manufacturing businesses (called "Establishments" in census terminology),  
which are broken down by:  

a) the US state they are in\
b) the sector they are in\
c) the approximate number of employees they have

The original datafile is available from https://www.census.gov/data/datasets/2012/econ/census/2012-manufacturing.html, link under "State". The download has multiple files, the main datafile is ECN_2012_US_31SA1_with_ann.csv

I also use the 2012 census estimates of the state populations, which can be found under https://www.governing.com/gov-data/state-census-population-migration-births-deaths-estimates.html, or in the .csv which I added to this project.

I ran some preprocessing on the ECN_2012_US_31SA1_with_ann.csv file to get numbers of businesses and estimated numbers of employees in different sectors for each state, then normalized by the estimates of the state population. The code for this is in the .ipynb notebook. The resulting file is US_Census_2012_manufacturing_per_10000_residents.csv.  This served as the input dataset for the Tableau workbook.



## European football transfers

For this project, I first scraped data on player transfers within european football from https://www.soccernews.com.  
I ran some preprocessing to convert the team names to geographic coordinates, then visualized the web of transfers using Tableau. I also analyzed to what extent 

The visualization can be found at:

https://public.tableau.com/profile/cjstoneking#!/vizhome/european_football_transfers/Dashboard1

here is a preview image:

![tableau_euro_football](european_football_transfers/euro_football_small.png?raw=true)



