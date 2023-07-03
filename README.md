# Final-Project-Statistical-Modelling-with-Python

## Project/Goals

My primary goal for this project was to learn how to get data from an API, parse through that data and create a data base from which i can perform EDA and data analysis on. Within that main goal i had smaller goals such as learning how to efficiently parse json data from an HTTP GET request, learn how to create the best visual to describe the data at hand and fine tune a linear regression model that I applied to my data

## Process

Part 1:

1. My first step was to create a simple API request from the city bikes API to see what the response data looked like. Once i established an understanding of what the data looked like i parsed through the data to return the desired columns, namely the longitude and latitude.
2. I used an f string to format the url to allow for greater flexibility if needed

3) To make my code more flexible i created a function that allowed the user to input any city they could think of and return the city_id if it existed which could then be used in a subsequent API request to get the bike stations for the particular city
4) Once i was able to select the data for the city of my choice, i parsed the results and created a database
5) I saved that database as a csv file so that it could be read into the notebook for part 2

Part 2:

1. As in part 1, my first step was to create a simple API request from the four square API to see what the response data looked like. Once i established an understanding of what the data looked like. I then added required fields and formatted the url so that it was more flexible
2. I created a function to make the API requests so that the function could be called in later code cells and added error checking to help my understanding of how the requests were working

3) I then paresed through the response data to return the desired results and printed the results as a sanity check
4) I then used the parsed data and looped through it to create each row of the database
5) I used steps 1-4 for the Yelp API as well
6) I saved both databases as csv files so that it could be read into the notebook for part 3

Part 3:

1. I started by reading in the data that i had saved as a csv file and cleaning any data that did not make empiracle sense, i also adjusted the data types of a few columns to better reflect the data within. additionally i removed a column that was unnecessary.
2. I then used impiutation to fill in NaN values
   1. for the addresses i used reverse geocoding to generate addresses from their latitude and longitude
   2. for categories i set a default value of "Restaurant" and created a "Bike Stations" category
   3. I provided a unique category ID for the bike stations as well
3. I then created a few visualizations
   1. first of which is a histogram of the ratings for the POI's. I was forced to split the data into two graphs because i used imputation to give a mean rating to all of the POI's that had NaN ratings values which was quite a lot and skewed the visualiation.
   2. I also created a heatmap of the correlation between rating and category ID which I found was basically uncorrolated.
   3. I created a scatterplot of the longitude and latitude of the POI's and used their ratings as a hue, this was to help visualize of ratings were semi-dependent on geographical location
   4. My final visualization is a colour-coded interactive map of the locations of all the POI's and bike stations overlayed on a map of the city of my choice..
4. I then created 3 seperate tables from my data using sqlite3 and inserted the data from my joined data frame into the tables

Part 4:

## Results

(fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model.)

## Challenges

The main challenge I faced was retrieving the correct information from the Yelp API without going over my daily call limit of 500. That made testing my code incredibly difficult while still trying to have a database that is robust enough to perform interesting analysis on. Additionally, parsing through the data was very time consuming as was the data cleaning process.

## Future Goals

The two main things i would like to do given more time would be to tune my model and to fine tune the interactive map that i created to make the visualization both more visually apealing and easier to understand. I would add custom icons for each category a long with colour coordination which would improve clarity, i would also add a legend.

For my linear model i would have fine tuned the model to increase its accuracy to better represent the story I wanted to tell with the data
