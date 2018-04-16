# datasci-kickstarter-boardgames
Regression analysis of what factors make a kickstarter boardgame project raise more money. 

## Summary
This is my second Metis (data science bootcamp) project focusing on regression. 

The goal is to predict how much money projects in the “Tabletop Games” category on Kickstarter will raise, and infer ways for a project creator to increase likelihood of success. 

The project includes a data scraper, linear regression models with varying features, and some inferential analysis.

## Files
* Kickstarter_Scraper.ipynb - BeautifulSoup scraper for Kickstarter.com. Two stages: collect project URLs from the search page, then scrape data from each project URL.
  * kick_urls.txt - Output file of scraped URLs
  * kick_data.csv - Output file of scraped project data
* Cleaning_EDA_Regression.ipynb - Data cleaning, exploratory analysis, and model + feature selection
* Kickstart_Board_Game_Pres.pdf - Project presentation slides
* Kickstart_Board_Game_Writeup.pdf - Outline of project & process

## Results
Best model includes all features + 2nd degree interaction terms without regularization. Validation results ~.6 R-square (i.e. ~60% variance explained). 

Key features in the regressions:
* FAQ and Update activity (lesson: post often!)
* Funding goal (lesson: set an ambitious target!)
* Min Reward Price (lesson: limit freebies)
* "Base" Reward Price (lesson: set a reasonable per-unit cost)
