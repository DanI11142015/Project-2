# Project-2
ETL project 
---
## Project Proposal
**Data source 1: 17K Mobile Strategy Games**

**Description** data on 17K strategy games from the apple app store collected in August 2019

link [17K Mobile Strategy Games](https://www.kaggle.com/datasets/tristan581/17k-apple-app-store-strategy-games)

**Data source 2: iOS App Store**

**Description** over 7k apple iod mobile application data details collected 2018

link [iOS App Store](https://www.kaggle.com/code/gloriousc/ios-app-store/data)

**Data source 3: Google Play Store Apps**

**Description: over 9k apps from the google play store collected in 2018**
Link [Google Play Store Apps](https://www.kaggle.com/datasets/lava18/google-play-store-apps)

Initial findings in data sources (2-3 sentences)
1. 1st data source 
  - the columns are as follows: name, avg user rating, user rating count, in app purchases, price,
	- subtitle column has 69% null values and In-app Purchases has 55% null values. 
  - the price ranges are from $0.00 to $9.00
  - the peak of the distribution of user ratings is between 4.2 and 4.6
  
  2. 2nd data source
   - the columns are as following: name, currency, price, file size, rating count total, user rating
   - the price ranges are from $0.00 to $30.00
   - The peak of the distribution of user ratings is 4.5 to 5.00
    
   3. 3rd data source
   -  the columns are as following: Name, category, rating, reviews, size, installs, type (paid or free), price, content rating and genres. 
   - 93% of the apps are free
   - the peak of the distribution of ratings is 2.8 to 4.6
   - 80% of the content rating is for everyone
---
## Extract
1. 1st Data Source
  - Columns: URL, ID, Name, Subtitle, Icon URL, Average User Rating, Price, In-app Purchases, Description,  Developer, Age Rating, Languages, Size, Primary Genre, Genres, Original Release Date, Current Version Release Date
  - Observations on initial state of data
  	- Subtitle and In-app Purchases columns have many NaN values, Languages has list of two-letter country codes, and Date columns are in D/M/Y format
2. 2nd Data Source
  - Columns: Unnamed, ID, Name, Size, Currency, Price, Total Rating Count, Rating Count Latest Version, Total Average User Rating, Average User Rating Latest Version, Latest Version, Content Rating, Primary Genre

## Transform
1. 1st Data Source
  - Columns dropped: 
  	- Subtitle and In-app Purchases, because of the NaN values 
	- Icon URL, because it is irrelevant to analysis
	- Genres, because these are subgenres of games, and the other datasets are of mixed primary genre without subgenres
  - Drop Na rows
  - Converted dates to M/D/Y format
  - Aggregated Language country codes to a count of languages

## Load
Describe the final database’s tables/collections
ERD Diagram
![ERD Diagram](QuickDBD-Project%202%20ERD.png)
Our client asked for us to extract all avilable Kaggle data on apps from both Google and Apple app stores, and to clean this data so that as many apps as had complete data in both stores could be compared with one another.
