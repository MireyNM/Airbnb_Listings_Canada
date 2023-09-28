# Airbnb_Listings_Canada

Visualized Airbnb Listings Prices across the 13 Canadian provinces and North Territories.

## Table of Contents 
* [Overview](#overview)
* [Aim](#aim)
* [Technologies](#technologies)
* [Data](#data)
* [Analysis and Visualization](#analysis-and-visualization)
* [Challenges](#challenges)
* [Summary](#summary)

## Overview 
In this project, we study Airbnb listings data extracted on August 21st, 2023, from the 13 Canadian provinces and North Territories to visualize their prices. 

## Aim
The aim of our study is to help travelers make smarter and budget-friendly travel decisions. 

## Technologies 
* Python 3.7.13
* Jupyter Notebook 
* HTML/CSS 
* BeautifulSoup
* Python Dash

## Data
### Data Scraping 
The data was scraped on August 21st, 2023, from [airbnb.ca](https://www.airbnb.ca/) using `BeautifulSoup`. Two major cities were scraped for each of the 13 Canadian provinces. The only exception here is for Northwest Territories and Nunavut as they only have 1 major available city. The total number of raw dataframes is therefore 24. The initial dataframe for each province is as follows (See Fig.1). 

<p align="center">
  <img width="911" alt="Img1" src="https://github.com/MireyNM/Airbnb_Listings_Canada/assets/109363759/de131329-4a7c-4683-ae93-7a836e10f795">
</p>
<p align="center">
  Fig.1 - Raw dataframe for Ottawa listings. 
</p>

### Data Cleaning 
A few cleaning steps were needed:
- Remove extra-long hyphens and replace them with regular hyphens.
- The initial data has rating and the number of reviews in the same column. For example: 4.82(140), where 4.82 is the rating, and 140 is the number of reviews. This column was transformed into two separate ones, `rating` and `nb_reviews`, and then deleted. 
- The data range suggested by Airbnb was cleaned and separated into two columns: `start_date` and `end_date` as the starting and ending dates for availability. 
- For each dataframe, two columns were added: one for the city's name and the second for the province's name.

## Analysis and Visualization
### Preprocessing Data  
All 24 dataframes were merged into one dataframe, containing 6048 listings across Canada, the average, minimum, and maximum listing prices were calculated per province.

### Visualizing Data  
The listings' prices across Canada were then visualized by creating:
- A choropleth map and a horizontal bar chart to visualize the average, minimum, and maximum listing prices per Canadian province.
- A bar chart to visualize the average, the minimum, and the maximum listing prices per bed type for each Canadian province.

Finally, an interactive web application dashboard was developed using `Python Dash` and `Plotly` to consolidate all the visualizations.

https://github.com/MireyNM/Airbnb_Listings_Canada/assets/109363759/d86338a0-6043-4aa7-a08f-ce2c91224b21

## Challenges
Multiple challenges were encountered during this project:
* Updating the scraping code: With each Airbnb update, the scraping code needs to be adjusted to extract the exact data.
* Building the choropleth map for Canada: By default, the choropleth map is designed for the USA. Creating this map for Canada was challenging. The first step was to locate the GeoJSON data for Canada, and the second step was to create and add an ID column to the final dataframe, with province names matching the GeoJSON and the exact ID numbers.
* Managing project goals: As I have mentioned on my LinkedIn, a data analyst should recognize that a project is never truly finished. Adjusting to the idea of 'good enough' versus perfection posed a significant challenge.

## Summary 
At the end of this project, an interactive web application dashboard was created to visualize:
- The average, maximum, and minimum listing prices across the Canadian provinces. 
- The price of Airbnb listings per bed type for each Canadian province.
