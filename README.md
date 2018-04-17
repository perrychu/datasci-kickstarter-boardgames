# datasci-kickstarter-boardgames
Regression analysis of what factors make a kickstarter boardgame project raise more money. 

## Summary
This is my regression project for Metis (a data science bootcamp). It includes a web scraper and a pipeline for fitting linear regressions.

The goal is to predict total dollars raised for "Tabletop Games" project on Kickstarter. A good model could help highlight projects for backers and help creators estimate the potential of a project. I also look at important features to infer levers that creators can use to increase how much they raise. 

The key concepts I explored were bias-variance tradeoff and validation vs. testing.

## Files
#### Code
* **Kickstarter_Scraper.ipynb** - BeautifulSoup scraper for Kickstarter.com. Two stages: collect project URLs from the search page, then scrape data from each project URL.
  * kick_urls.txt - Output file of scraped URLs
  * kick_data.csv - Output file of scraped project data
* **Kickstarter_EDA_Regression.ipynb** - Data cleaning, exploratory analysis, and model + feature selection. Includes a pipeline for model evaluation using cross validation, which I used to explore feature combinations and regularization.
#### Docs
* **Kickstart_Board_Game_Pres.pdf** - Project presentation slides
* **Kickstart_Board_Game_Writeup.pdf** - Bullet point outline of project process

## Results
Best model includes all features + 2nd degree interaction terms. Regularization only has a slight benefit, so I excluded it for interpretability. Validation showed ~60% variance explained (0.6 R^2). 

However, test r-square was negative! This was due to some outliers in the data which were assigned to the test set. Easily fixable, but I decided to leave them in as an illustrative example.

Top features in a simple linear regression:

Importance* |Feature | Coefficient | Takeaway  
:-------:| ----- | -----------:| --------  
1 | Update activity | $2296.90 | Give frequent updates
2 | FAQ activity | $5454.67 |Interact with backers
3 | Funding goal | $0.80 | Set a more ambitious target  
4 | Min Reward Price | $557.13 | Limit freebies  
5 | % US Backers | -$54,594.52 | Market to US and non-US audiences
6 | "Base" Reward Price | $200.61 | Set a reasonable per-unit cost - don't discount heavily  

\*Ranked by absolute value of coefficients from regression on standardized features
