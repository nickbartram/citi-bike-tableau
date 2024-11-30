# Citibike Story Written Analysis (Module 18 Challenge: citi-bike-tableau)

The is a written analysis of a Tableau presentation. This written analysis mostly describes slides in a Tableau presentation, and a large amount of the written analysis here comes from those slides.  This written analysis is complimentary to the Tableau Public workbook accessed here: [link to Tableau Public](https://public.tableau.com/views/citibike_tableau_final/CitibikeStory?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## **The Map with Everything**:

The presensation starts with a map of every bike station in the dataset. This map shows all the of Citibike station locations that were used between August and October 2024. This includes all the the start locations, and all of the end locations. The zipcode boundaries are provided but at also available in the tooltip of this location points.

It's clear even from this overview that the most popular Citibike stations are in New Jersey, at least during this time frame. The map should show a filter to choose between any combination of the three months studied in this analysis. From looking at the map, it might be helpful to know more about when bike are being used. The next slide will look at the time of rides on the dataset.

## **When Rides Happen Most:**

To know more about when the most rides are happening, ride times are broken down by: hour, day of the week, and day of the month. We can see a predictable increase around the morning and evening rush hours. The rides gradually increase throughout the day until after evening rush hour, where they steadily decrease.

This shows a pretty clear and maybe obvious observation: there are more rides at rush hour or busy times. It's encouraging that the data seems realistic here. It means that at least some of the data is behaving normally. The next slide will examine typical distance and duration of rides.

## **Distance Traveled and Duration:**

The are some odd numbers here as the most common distance traveled is 0km. This could be for several reasons:

1. It could be because of the way we're calulating distance traveled here. It simply a measure of the distance between the start location and the end location. This could give a total distance traveled of 0km if the bike is returned to the same station is started from. We should look at the most popular start and end stations, and see if they can account for this phenomena.
2. It could be that the data has been skewed somehow. Maybe by server or GPS errors. There are other abnormalities in the data, and we should look into why and if certain stations, zipcodes, or states are over-represented in the data.
3. Because there are many rides whose duration is 0 or almost zero, there may also be an issue with people returning bikes immediately, canceling them, or perhaps some kind of issues with tracking software.

## **Start/End Recap:**

This slide looks at the most common start and end locations of Citibikes. A very strange phenomena is happening here: there are not any points starting in New York over three months (August, September, October 2024).

This was checked and re-checked to confirm. Zero start points are appearing in New York and a shockingly low number of rides are ending there as well. This points to potential issues with data collection. Could there be an outage in New York stations? Has Cititbike moved away from New York and phasing out there stations there?

### State Difference Recap:

We can see that not only is the data skewed heavily towards New Jersey, it's specifically skewed heavily towards two zipcodes in New Jersey (07302, 07030). These two zipcodes make up the vast majority of  rides, whether starting or stopping at these stations. Something is skewing the data in that direction.

## Hoboken Terminal: The Most Popular

The most popular Citibike station, for both start and ending rides, was Hoboken Terminal. The data from that part of New Jersey makes up most the the dataset.

It's possible the data from Hoboken or that area somehow overwrote the data from New York City (NYC). Looking at previous years data, it's clear that Citibikes had a massive presence in NYC. Given the all-around traffic in New York City, it's bizarre that there isn't much more activity with Citibikes during this three month period.

## Conclusion:

The previous dashboard showed rides coming and going from Hoboken Terminal. It demonstrates a sample of the traffic for the busiests bike station in the dataset.

This Citibike ride dataset is skewed towards Hoboken Terminal but, also New Jersey in general. However, the New Jersey data is believable. The NJ traffic is centered around busy hubs near public transit and NYC.

All the rides starting and ending at Hoboken Terminal could explain the prevalance of 0km trips. People could be traveling to Hoboken Terminal on public transit, using a Citibike to ride around the area, and then returning back to Hoboken Terminal.

It is the New York City data that is harder to understand. There are a few ideas for why this is happening.

First:

- Citibike may be phasing out stations in New York City. There's a chance that right now there are only drop-off stations in New York City but, no pick-up stations.

Second:

- The connection to the bike stations is malfunctioning. There seems to be some inconsistencies with the data that could be explained by issues with data collection. If bike stations in NYC were not transmitting data properly, it could explain the lack of data from there.

Third:

- Limitations in data entry (Citibike issue) or loading (issue with process of this analysis). These three months were chosen because they crossed seasons and were very recent. It possible a mistake was made while downloading or processing the data. Repeated testing has shown that the data was loaded properly.  A file being overwritten in data entry, perhaps a faulty join, could have happened on Citibike's end. If a dataset from Hoboken did an improper join with a dataset from New York City, it might look like the data in the visualizations we have seen so far.

Ulitmately, it's clear what's happening here. The files that were used for this analysis were specifically from the Jersey City area. The file names all start with JC(e.g. [JC-202410-citibike-tripdata.csv.zip](https://s3.amazonaws.com/tripdata/JC-202410-citibike-tripdata.csv.zip)), but only at the end of all this work do I see what that means. A terrible oversight, but it at least explains the weight towards Jersey City.
