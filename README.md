# datasci-kickstarter-boardgames
Regression analysis of what factors make a kickstarter boardgame project raise more money. 

## Summary
This is my second project at Metis (a data sci bootcamp), focusing on regression. 

The goal is to predict how much money projects in the “Tabletop Games” category on Kickstarter will raise, and infer ways for a project creator to increase likelihood of success. 

The project includes a data scraper using BeautifulSoup, and linear regressions with varying features + cross validation. The key concepts I learned were bias-variance tradeoff and validation vs. testing.

## Files
#### Code
* **Kickstarter_Scraper.ipynb** - BeautifulSoup scraper for Kickstarter.com. Two stages: collect project URLs from the search page, then scrape data from each project URL.
  * kick_urls.txt - Output file of scraped URLs
  * kick_data.csv - Output file of scraped project data
* **Kickstarter_EDA_Regression.ipynb** - Data cleaning, exploratory analysis, and model + feature selection
#### Docs
* **Kickstart_Board_Game_Pres.pdf** - Project presentation slides
* **Kickstart_Board_Game_Writeup.pdf** - Bullet point outline of project process

## Results
Best model includes all features + 2nd degree interaction terms without regularization. Validation results ~.6 R-square (in other words ~60% variance explained). 

However, test r-square was negative! I discovered this was due to some outliers in the data which were assigned to the test set. Easily fixable, but I decided to leave them in as an illustrative example.

Key features in the regressions:
* FAQ and Update activity (lesson: post & interact often)
* Funding goal (lesson: set a more ambitious target)
* Min Reward Price (lesson: limit freebies)
* "Base" Reward Price (lesson: set a reasonable per-unit cost)
