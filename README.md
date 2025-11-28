
# Airbnb Listings EDA Project: New York 2024

![image alt](https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/airbnb%20logo.png?raw=true)


## Table Of Contents

- [Project Overview](#project-overview)
- [Objective](#objective)
- [Dataset](#dataset)
- [Tools](#tools)
- [Steps And Workflow](#steps-and-workflow)
- [Key Findings and Insights](#key-findings-and-insights)
- [ How to Run This Project](#how-to-run-this-project)
- [Recommendations](#recommendations)
- [Future Work](#future-work)
- [Conclusion](#conclusion)
- [Contact](#contact)

## Project Overview
This project performs Exploratory Data Analysis (EDA) on New York Airbnb data to uncover trends and patterns in rental listings. We use libraries like Pandas, Numpy, Matplotlib, Seaborn for cleaning, visualization and analysis.
## Objective
The goal of this project is to:

Analyze room types, prices, and availability across different neighborhoods.
Understand host behavior and listing patterns.
Detect potential outliers in prices.
Provide recommendations for guests and hosts based on insights.
## Dataset
The dataset contains 20,765 entries and 22 features, including:

* id: Unique identifier for each listing  
* name: Title of the Airbnb listing  
* host_name: Name of the host  
* neighborhood_group: Group (borough) where the listing is located  
* latitude/longitude: Geolocation of listings  
* price: Nightly rental price  
* room_type: Type of accommodation (e.g., entire home, private room)  
* reviews_per_month: Average monthly reviews for the listing  
* availability_365: Number of available days in the year

## Tools
* Jupiter Notebook: Python
* Python libraries:
   * Pandas
   * Numpy
   * Matplotlib
   * Seaborn
## Steps And Workflow
**1. Data Cleaning**
* Handle missing data: price, neighborhood, and beds columns had null values.
* Fix data types: Converted last_review to a datetime object.
* Remove outliers: Listings with prices > $1,000 were capped to avoid skewed visualizations.
  
**2. EDA (Exploratory Data Analysis)**
* Room type distribution:
Visualized the count of each room type using bar plots.
Identified Entire home/apt as the most common room type.
* Neighborhood group insights:
Analyzed price variations by boroughs.
Manhattan had the highest average prices.
* Availability trends:
Used heatmaps to show correlations among price, availability_365, number_of_reviews, and beds.
* Price distribution:
Used histograms to show the distribution of prices.
Majority of the listings were priced between $50 - $300.
* Host listings:
Analyzed hosts with multiple listings using boxplots to identify key contributors.
* Review behavior:
Used pair plots to show relationships between number of reviews, price, and availability.

**3. Data Visualization**
* Pairplot: To see correlations among price, availability, and number of reviews.
* Heatmap: Showing correlations among numerical features.
* Histograms and Boxplots: To detect outliers in price.
* Bar Charts: Displaying room types and neighborhood group distributions.
  
## Key Findings and Insights
**1. Availability_365 Distribution (Histogram)**

![image alt](https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/Availability_365%20Distribution.png)

There are two major peaks in availability:

* Very low availability (0–30 days) which indicates highly booked or highly demanded listings.

* Very high availability (350–365 days) representing listings that remain mostly unbooked—possibly overpriced or newly created listings.

* Mid-range availability (100–250 days) has a moderate distribution, suggesting average demand.

* This uneven distribution highlights a bimodal trend: some listings are extremely popular, while others get very few bookings.


**2. Geographical Distribution of Airbnb Listings (Scatter Plot)**

![image alt](https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/Geographical%20Representation%20Of%20Airbnb%20Listings.png)

* Listings are heavily concentrated in Manhattan and Brooklyn, confirming these boroughs as prime Airbnb zones.

* Manhattan has a higher density of Entire home/apartment listings, likely due to tourism-driven demand.

* Brooklyn shows a more balanced mix of private rooms and entire homes, appealing to both tourists and budget travelers.

* Queens, Bronx, and Staten Island have fewer listings and more scattered distributions.

* High-density clusters correspond to major tourist locations such as Lower Manhattan, Midtown, Williamsburg, and Harlem.


**3. Correlation Heatmap**

![image alt](https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/Heatmap.png)

* Price has a positive correlation with number of beds (0.42) — more beds generally mean higher prices.

* Number of reviews and reviews per month are strongly correlated (0.63), meaning listings that get reviews tend to get them consistently.
 
* Price shows almost no correlation with:

  -minimum nights

  -number of reviews

  -latitude/longitude
* This suggests price is more influenced by room type and neighborhood, not number of reviews or location coordinates.

* Overall, the dataset shows weak correlations, implying Airbnb listing characteristics are diverse and not linearly related.


**4. Locality and Review Dependency (Scatter Plot: Reviews vs Price)**

![image alt](https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/Locality%20And%20Review%20Dependency.png)

* Most listings fall within 0–300 reviews and prices below $200.

* Manhattan listings dominate the high-price region—even low reviewed Manhattan listings are priced higher than other boroughs.

* A negative trend appears: as number of reviews increases, prices tend to decrease slightly — lower-priced listings attract more guests and reviews.

* Outliers exist with 1,000+ reviews, mostly lower-priced Manhattan or Brooklyn rooms.


**5. Pairplot (Multivariable Relationship)**

![image alt](https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/Pairplot.png)

* Price shows right-skewness — many low-priced listings, fewer extremely high-priced ones.

* Minimum nights appears heavily right-skewed with occasional extreme values (e.g., long-term stays).

* Room type patterns:

  -Entire home/apartment tends to have higher prices and availability variation.

  -Private rooms cluster in the low-price and low-minimum-nights region.

* The combination of variables reveals clear clustering by room type, especially for:

  -price

  -number of reviews

  -availability


**6. Price Distribution by Neighbourhood Group & Room Type (Bar Plot)**

![image alt](https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/Price%20Distribution%20By%20Neighbourhood%20Group.png)

* Manhattan is the most expensive borough across all room types.

  -Entire home/apartment: ~$250

  -Hotel room: ~$300

* Brooklyn is the second-priciest but significantly cheaper than Manhattan.

* Queens, Bronx, and Staten Island have moderate to low prices, making them suitable for budget-friendly travel.

* Hotel rooms are consistently the costliest category across regions.

* Shared rooms remain the cheapest option everywhere.


**7. Price Distribution (Histogram)**

![image alt](https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/Price%20Distribution.png)

* Most listings are priced between $50–$200, forming the main distribution peak.

* Very few listings exceed $500+, confirming these as luxury or premium properties.

* The long right tail indicates high price outliers, typical for Manhattan penthouses or luxury stays.

* The distribution shows clear price skewness, suggesting a few expensive listings pull up the average.

## How to Run This Project
* Clone the repository:
git clone https://github.com/Rohitshinde14/New-York-AirBnb-Listing-2024-Python/blob/main/new_york_airbnb_project.ipynb
* Install the required libraries:
pip install pandas numpy matplotlib seaborn
* Run the Jupyter notebook:
jupyter notebook new_york_airbnb_project


## Recommendations
* Adjust prices for listings with very high availability (350+ days).

* Improve listing quality with better photos and more guest reviews.

* Offer flexible/shorter minimum-night stays to increase bookings.

* Guests can choose outer area for cheaper stays.

* Platform/analysts should flag overpriced or underperforming listings.
 
## Future Work
* Perform sentiment analysis on reviews to better understand guest experiences.
* Create an interactive dashboard using Plotly or PowerBi for live monitoring.

## Conclusion
NYC Airbnb data shows Manhattan is the most expensive and busiest market, while outer boroughs offer affordable options. Most listings fall within $50–$200, with some high-price outliers. Availability patterns show some listings are extremely popular while others stay unbooked, highlighting the need for better pricing and listing optimization.

## Contact
Rohit Shinde  
Data Analyst
* Email: shinde.rohit005@gmail.com
* LinkedIn: www.linkedin.com/in/rohitshinde14
* GitHub: https://github.com/Rohitshinde14
