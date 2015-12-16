# Summary

Taxi data from NYC is available for some time now (see http://chriswhong.com/open-data/foil_nyc_taxi/). The visualization I created allows the user to get aggregated information on the taxi trips and detailed insights into the origin/destination of the trips simultaneously. After a short overview into some findings in the data the reader or user can analyze the data in various ways.

# Design

The visualization has two components. On the left side there is a chart showing the results of data aggregation. On the right side there is a map showing trip origins/destinations. The user will have the possibility to filter the data for both of the visualization components.

The components are designed in a way that they could be changed „in place“. This minimizes the need to build new components on the page. Also, the code is flexible and modular. It allows to easily change the story told independent of the visualization code itself. 

- index1.html is the first version of the visualization that has an automated story that goes through some findings I had in the data. When the story is finished the uses has the possibility to evaluate the data on his/her own.
Link: http://wilhoge.github.io/NYC-taxi-viz/index1.html

- One point in the feedback for the first version was that the loading time is too long and that the data points on the map are not giving good indication of how the taxi rides distribute over the city. Therefore I decided to aggregate the data on geographical basis and normalize it to the number of rides at the current filter settings. This improves the load time significantly (it was slow due to the number of points to draw on the map) and gives a clearer indication how the taxi rides distribute. 
I also changed the story from automatic to user driven. The story now leads through the data and shows some findings before the user can analyze on his/her own.
I also changed the y-axis to a fixed value to make it easier to compare values between different filters.
The second version that has these changes is index2.html.
Link: http://wilhoge.github.io/NYC-taxi-viz/index2.html

- The feedback for the second version shows that the visualization has indeed improved. What was mentioned though is that it would be great to see additional metrics also. So I extended the free analysis part of the visualization. It now gives features more values to analyze. Besides passenger count that was also available in the first and second version it now also offers, average trip, average fare, average speed and average fare per mile. 
I also added more descriptive text to explain the filters, metrics and data.
Although there are still ideas how to improve the visualization even further with additional metrics, more data and more filters this is the final version (index_final.html).
Link: http://wilhoge.github.io/NYC-taxi-viz/index_final.html

# Feedback

## Feedback for first version of visualization (index1.html)

### The first feedback I got was through the Udacity forum from Uirá:

Hi @wilfried_29181078645,

Very nice dataset. About your y-axis, when you say „Average passenger count per day“, is It the average passengers for the period of the day? I’m asking that because the number of rides look too low for me, considering your map.

Some suggestions:

- Do not rescale your y-axis. Would be easier to compare the different filters you have done.
- Maybe you could create a separate file pre-processing the statistics used in your visualization. So, you could include much more data in your measurements
- As you are showing the data on a map, would be nice see a histogram of the distances of the trips. Or relate it to the time per mile. I bet that the time per mile at 18:00 on Friday is the worst of all =)

Uirá

### The second feedback is from my friend Stephan

- What do you notice in the visualization?
I get an idea about taxi usage behavior in NYC on different days based on passenger numbers and taxi rides (pick up and drop off). The visualization is animated on the timeline (day of week) which provides a simple way to get an idea of changing behavior based on day of week

- What questions do you have about the data?
How has the sample data set been selected? 
Is the sample data set representative for the entire population?
What are the definitions of morning, midday, … etc?

- What relationships do you notice?
Selecting on the bar chart also changes the visualization on the map, but not vice versa.
Hence the bar chart seems to be the master view and the map provides additional details.

- What do you think is the main takeaway from this visualization?
Knowing the demand of taxis in NYC depending on day of week and time of day plus the “hot spots” where taxi rides usually start and end.

- Is there something you don’t understand in the graphic?
It is hard to understand the hot spots in the map due to the high number of points.
When I switch between day of week on the bar chart, the scale of the avg passengers (y-axis) changes, which makes it hard to compare absolutely, may be  a normalization would be a good idea

### The third feedback is from my colleague Jochen

Within the description Drop-Off Pickup … is not mentioned - should be there

- What do you notice in the visualization?
it is a little bit crowded - a lot of data point - probably there  should be an aggregation of the data

- What questions do you have about the data?
no

- What relationships do you notice?
different workload on the days and on day times

- What do you think is the main takeaway from this visualization?
no sure

- Is there something you don’t understand in the graphic?
what is the business question which wants to be solved here?


## Feedback for second version of visualization (index2.html)

### Feedback through the Udacity forum from Uirá:

Hi @wilfried_29181078645,

Your story is clear now, and you pointed out some interesting facts. Also, your visualization is loading much faster.

By „pre-processing of data“ I mean exactly that: pre-aggregate data to the graph, maybe creating a file with all filters that you want and the numbers already aggregated.

Even if you don’t show all the data points on your map, you can use them to calculate the statistics. But the way that you decided to do now is much better.

Uirá

### Feedback from my colleague Jochen

- What do you notice in the visualization?
good intro about the data and what is all about - then own analysis possible

- What questions do you have about the data?
no

- What relationships do you notice?
relationships mentioned in the intro

- What do you think is the main takeaway from this visualization?
insight for planning my taxi routes - I assume that if a lot of taxis are on the way the time of the taxi drive goes up -> would be great to have the average time for pertained distances - would be more useful then the number of taxi count

# Resources

NYC taxi analysis is based on data found here: http://www.andresmh.com/nyctaxitrips/. Only a small subset of the data is used for this visualization to demonstrate the concept.

The subsets to choose from have 1.000, 10.000 and 100.000 taxi trips and are a statistical sample of 3 month of data in 2013.

- taxi-av1000.csv
- taxi-av10000.csv
- taxi-av100000.csv

The final version of the visualization is based on the largest data set.

The documentation of dimplejs, d3, leaflet and also the Udacity forum about „Make effective data visualization“ was very helpful to complete this exercise.