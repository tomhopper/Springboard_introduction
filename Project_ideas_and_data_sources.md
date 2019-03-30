<style scoped> @import url("rmd_doc_suffix.css"); </style>
# Foundations Capstone Project Ideas and Data Sources

## Examples

Springboard provides [videos of past capstone project presentations](https://www.youtube.com/playlist?list=PLjKxfZpleE6B-e6hDQ4m7Yrs7s9HIoZZs) via Office Hours Thursdays. 

I did a simple R interactive data exploration of [crime in Michigan](https://tomhopper.shinyapps.io/MI_50_Safest_cities/). Not quite at the level of a capstone project, but it contains most of the elements of a good project.

## Project ideas (entry level):

These pre-packaged projects are good for the Foundations capstone project, and come with defined goals, scope and available data.

* [Five data science projects to learn data science](http://www.analyticsvidhya.com/blog/2014/11/data-science-projects-learn/)
* [Crowdanalytix](https://www.crowdanalytix.com/), One platform for crowdsourcing & deploying AI at scale
* [Kaggle](https://www.kaggle.com) Your home for data science
* [Data Sources for Cool Data Science Projects: Part 1](http://blog.thedataincubator.com/2014/10/data-sources-for-cool-data-science-projects-part-1/)
* [Data Sources for Cool Data Science Projects: Part 2](http://blog.thedataincubator.com/2014/10/data-sources-for-cool-data-science-projects-part-2/)

## Data-access packages:

> (See [These R packages import sports weather stock data and more](http://www.computerworld.com/article/3109890/data-analytics/these-r-packages-import-sports-weather-stock-data-and-more.html) for explanation of some of these packages.)

Unless otherwise noted, packages are available from CRAN.

* See the list of packages at [ROpenSci](https://ropensci.org/packages/)
* See also the list at 
* **blscrapeR**: Scrapes various data from the Bureau of Labor Statistics, which is the statistical branch of the United States Department of Labor. The package has additional functions to help parse, analyze and visualize the data.
* **[FredR](https://github.com/jcizel/FredR)**: R Interface to Federal Reserve Economic Data API. `devtools::install_github("jcizel/FredR")`
* **Quandl**: Get millions of financial and economic datasets from hundreds of publishers directly into R.
* **quantmod**: Specify, build, trade, and analyse quantitative financial trading strategies.
* **tidycensus**: retrieve Census data and metadata via API, with tidy data output.
* **RSocrata**: Provides easier interaction with Socrata open data portals
* **[forbesListR](https://github.com/abresler/forbesListR)**: R wrapper for the Forbes list API. `devtools::install_github("abresler/forbesListR")`
* **Lahman**: Provides the tables from the 'Sean Lahman Baseball Database' as a set of R data.frames.
* **pvsR**: facilitates API retrieval of data from Project Vote Smart's online database on U.S. politics. Available on CRAN [development version on GitHub](https://github.com/umatter/pvsR).

### Packages available on GitHub

Install using _devtools_:

    devtools::install_github(package_location)

* **[stattleshipR](https://github.com/stattleship/stattleship-r)**: Stattleship R Wrapper. Install with `devtools::install_github("stattleship/stattleship-r")`
* [github.com/ozagordi/weatherdata](https://github.com/ozagordi/weatherdata)
* [github.com/hadley/data-movies](https://github.com/hadley/data-movies)
* [github.com/hadley/nycflights13](https://github.com/hadley/nycflights13)
* [github.com/hadley/data-baby-names](https://github.com/hadley/data-baby-names)
* [github.com/hadley/neiss](https://github.com/hadley/neiss)
* [github.com/NYTimes/gunsales](https://github.com/NYTimes/gunsales)
* [github.com/hadley/yummlyr](https://github.com/hadley/yummlyr)
* [github.com/hadley/usdanutrients](https://github.com/hadley/usdanutrients)
* [github.com/hadley/fueleconomy](https://github.com/hadley/fueleconomy)
* [github.com/tomhopper/eiaenergy](https://github.com/tomhopper/eiaenergy)

## Raw data sources:

[comment]: # (* [Registry of Open Data on AWS](https://registry.opendata.aws))

* Google provides a [dataset search](https://toolbox.google.com/datasetsearch) from which you can locate datasets from many sources
* [Free public data sets for your first data science project](https://www.springboard.com/blog/free-public-data-sets-data-science-project/)
* Free data sets [https://r-dir.com/reference/datasets.html](https://r-dir.com/reference/datasets.html)
* [NFL Data API](http://www.armchairanalysis.com/data-api.php)
* [U.S. government data sets](https://www.data.gov)
* [U.S. Census Bureau data](http://www.census.gov/data.html)
* [FBI crime statistics](https://www.fbi.gov/stats-services/crimestats/)
* [Bureau of Labor Statistics data](http://www.bls.gov/data/)
* [U.S. National Institutes of Health data](https://www.nlm.nih.gov/hsrinfo/datasites.html)
* [Data at KD Nuggets](http://www.kdnuggets.com/datasets/index.html)
* [U.S. Energy Information Agency data sets](https://www.eia.gov/tools/)
* [U.S. Environmental Protection Agency datasets](https://developer.epa.gov/category/data/)
* U.S. Department of Energy's Office of Energy Efficiency and Renewable Energy's [datasets on vehicle fuel efficiency](https://www.fueleconomy.gov/feg/ws/)
* Intergovernmental Panel on Climate Change [Data Distribution Centre](http://www.ipcc-data.org/)
* [U.S. National Oceanographic and Atmospheric Administration datasets](https://www.ncdc.noaa.gov/data-access)
* [NASA's Goddard Institute for Space Studies data](http://data.giss.nasa.gov/)
* [IRI/LDEO Climate Data Library](http://iridl.ldeo.columbia.edu/)
* [The World Bank datasets](http://data.worldbank.org/)
* [Financial data from Quandl](https://www.quandl.com/) (see also the _Quandl_ R package)
* International [Financial Inclusion Insights data](http://finclusion.org/data_fiinder/)
* University of Michigan's [ICPSR social research database](https://www.icpsr.umich.edu/icpsrweb/ICPSR/), containing data from more than 10,000 studies.
* [Yelp's data](https://www.yelp.com/developers/documentation/v2/overview)
* [Twitter's data](https://dev.twitter.com/overview/documentation)

## Real-world problems (challenging):

These projects are for the more ambitious student, and may require developing skills beyond the Foundations course material.

* [National Institute of Justice 2014 Data Visualization Challenge](http://nij.gov/funding/Pages/fy14-data-visualization-challenge.aspx)
* [U.S. Obesity Data Challenge 2015](https://www.challenge.gov/challenge/u-s-obesity-data-challenge/): stem the obesity epidemic.
* [Data science competitions to save the world](https://www.drivendata.org/)
* [U.S. government data science challenges](https://www.challenge.gov/list/)

## Inspiration for project ideas:

* http://vizwiz.blogspot.com/p/makeover-monday-challenges.html
* http://www.datavizchallenge.org/
* http://flowingdata.com/
* http://www.calculatedriskblog.com/
* http://economistsview.typepad.com/economistsview/
* http://www.economist.com/
* http://www.ft.com/home/uk
* http://www.nytimes.com/blogs/krugman/

…or most any news source. Just ask "how do we know that? What data exists on this, and what does it say?"

