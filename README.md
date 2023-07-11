# project1team1-1
​
## Project Overview
​
We want to analyze hurricane, droughts and daily temperatures to test commonly held climate change claims. We will be using the hurricanes data for the Atlantic Ocean, the droughts data for the United States and temperature date from British Columbia to test the climate change hypotheses. During the data collection we faced some challenges around collecting data which inhibited us from determining relationships from the available data, considering we want to use time-variant data to test most of these claims.
​
## Hypothesis
​
Climate change is a hotly contested partisan issue where its proponents prophesize catastrophic calamity, whereas it's detractors dismiss its relevance entirely. We wish to analyze extreme weather events to explore what a cursory analysis reveals in affirming the correlation between these events and the climate change claims. 
​
## Questions of Interest
​
1. Can we use historical climate change data to test the climate change claims?
​
A. We were able to find useful data from different sources. However we wanted to pull data from sources that were free of cost and had large data extraction limits.
​
2. Which events can we use to test these claims in a reliable manner?
​
A. We initially had many other types of events identified such as floods, earthquakes etc - however we settled on 3 types: hurricanes, droughts, temperature highs. As these were the primary indicators needed to prove climate change claims.
​
3. What timeframe should we use for the events datasets? Is 50 years long enough or do we need more?
​
A. In order to make climate related claims the more data the better. However technology in this space was highly unreliable the further back you go so in order to get clean data we settled on a max historical dataset of 50 years.
​
4. If we were limited by data could we use smaller datasets over shorter periods to test the hypothesis reliably?
​
A. We had to do so for the temperature and wildfires data but the analysis showed that the correlations were weaker for smaller data sets. Except in the scenario where there was expected to be a strong correlation, for example in the case of seasonal high temps and the occurrence of wildfires.
​
5. How will we cross-reference datasets from different sources?
​
A. This is what the bulk of the source code was developed to support. We needed a lot of data wrangling and had to construct logic to be able to generate the correct plots.
​
6. What visualization libraries are the most relevant to show meaninful data relationships?
​
A. For our purposes we found geoviews, folium and hvplot to be the most relevant libraries. Folium allowed us to generate really interesting chloropleth visualizations on the map, in a convenient way.
​
7. How would we need to re-structure and wrangle the data to convert it into a useable format?
​
We needed to reset indicies, parse data to make it understandble by the packages we were consuming and to render data visualizations.
​
8. What logical relationships would we need to construct to support our data story?
​
A. The data for weather events is often collected using standardized parameters such as latitude/longitude, wind speed, precipitation, dryness indices etc. In order for us to convert it into an easily readable format, over relevant timeframes (such as annual or decade long periods) we had to construct logical functions. An easy instance of that is when took the droughts data and came up with our categerizations that combined the climatologist taxonomies. We also had to use windspeeds to create categories for the hurricanes. 
​
## Data Exploration & CLeanup
​
### Hurricanes
​
We read hurricane data for east cost from the csv into a dataframe and reset its index. Determine the name of the hurricane for each record.
​
Define function that reads from hurricane df to show the number of hurricanes reported by year for last 50 years. should pull the hurricane name, location it made landfall, date, highest category reached and store in new df.
​
Select only records of landfall (crossing a coastal line). We then defined the Hurricane Category. Add the country each hurricane landed in to the visualization dataset. The visualizations give a geographical plot for the hurricanes by landfall and a separate plot where each hurricane can be selected by name to show its progression on its journey.
​
Get the frequency of hurricanes each year for each country. Group by US State and name to determine unique landings of each hurricane. Finally group by decade and category to generate a frequency bar plot for the data.
​
### Droughts
​
Define function that reads from droughts_df to map the duration, location in US, severity
calculate percentage of US states that experienced drought per year per severity store in new df. Group the data to get the yearly average and yearly average per state. 
​
Plot annaul average drought percent over the last 25 years by state. Plot chloropleths for extreme and abnormally dry datasets for the US.
​
### Daily Temperatures
​
Get max and min temperatures from a locally stored CSV (given in resources in repository).
​
Get the yearly maximum and minimum temperature and Plot the maximum and minimum temperature. 
​
Group the temperature data by season and use the dataset.
​
Read wildfire data from csv into a DataFrame. Clean and plot the wildfires data for last 10 years.
​
Plot Total Wildfires in last 10 years. PLot heatmap of Total Fires vs Year for past 10 showing area affected.
​
Combine the temperature and wildfire DataFrames to create a df depicting the number of fires per year for the last 10 years.
​
To see if there's a releationship between gas prices and the occurrence of hurricanes, read Florida Gas Price data from the csv into a dataframe. Get the price per gallon for every week and compare against the hurricane occurrence to see if there is a positive correlation between the occurrence of hurricanes and the price per gallon.
​
​
To identify a correlation between wildfires and the prices of different types of commodity prices, read price data for different types of commodities. Create a function to allow users to select from the available commodities and based on their input create the relevant plot to cross-reference the the average stock closing price with the occurrence of wildfires each year. 
​
## Limitations
​
We faced a few different limitations when looking for and using the data which are listed below:
​
1. Data became less available the further back we go.
​
2. A lot of sites have limitations around the consumption of data which means we would need to pay to get good data.
​
3. When cross-referencing datasets from different sources because of discrepancies we ended up losing data.
​
4. It was difficult to find commodity price data for the regions we pulled the weather data for.
​
## Conclusions
​
We were able to show a number of meaningful relationships from our data manipulation and visualizations. 
​
We were able to show that hurricane frequency is steadily increasing over the last 50 years and most likely will continue to increase if the temperatures increase. We were also able to show that the intensity of hurricanes has increased over the past 40 years with more category 1, 2 and 3 storms occurring.
​
We were able to see that there large parts of the US are affected by droughts in the US, and that the intensity of these droughts are increasing. However the occurrences of droughts overall remain consistent, with the exception of a recent spike in 2020. The reason why this correlation isn't obvious is because we were unable to find 50 years worth of data to test the claim that drought occurrence has increased for the US.
​
In terms of the claim that temperatures in BC are rising - we were not able to show a meaningful relationship once again because 10 years of data isn't sufficient to show a trend to that effect. However we are able to show a moderate positive correlation between wildfires and rising temperatures. We are also able to show that the area of impact of wildfires has increased over the last 10 years. In addition to that we were able to show some changes in higher temperatures by seasons, which could be used to support a weaker claim that temperatures may be rising in BC over time.
​
In terms of the effects of these events on commodity prices, no meaningful relationship could be inferred from the data analysis.