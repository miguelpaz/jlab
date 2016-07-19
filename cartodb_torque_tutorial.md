
# Making an animated torque chart in Carto 

Making charts is one of the coolest things in data journalism. It is really a good way to visualize data about places, that sometimes it just won’t fit a normal type of chart. 

[Carto](https://voltdatalab.cartodb.com) is one of the best tools out there to do that. You can make interactive maps, download static image files and customize colors and points. And it is free if you are OK with using their more basic resources (which are good by most standards).

Torque is a resource that animates your map when using time series data.

This tutorial will teach how to use addresses and geolocation with Carto to animate your graphic. 

For this tutorial you will need: 

1. [This dataset about mass shootings in the US](https://github.com/miguelpaz/jlab/blob/master/data/cartodb_mass_shootings_US.csv)
2. An account in [Carto](https://voltdatalab.cartodb.com)

___

## Understanding the dataset

The dataset we will use contains information about mass shootings in the United States during 2016, and it has nine columns: 1. Date 2. State 3. City 4. Short address designation 5. Address 6. Latitude 7. Longitude 8. People killed and 9. People injured. The data comes from the [Gun Violence Archive](http://www.gunviolencearchive.org/reports/mass-shooting).

For this tutorial, we have added the Address column and the LAT/LONG columns. 

Our goal will be to create an animated map. 

> **TIP:** If this is your first time learning about using Carto, I recommend you to to start with the [Carto Basics Tutorial](https://github.com/miguelpaz/jlab/blob/master/cartodb_basics_tutorial.md) and then follow with [How to create a Carto map with geolocation data](https://github.com/miguelpaz/jlab/blob/master/cartodb_geolocation_tutorial.md). It wont take you more than 1 hour to create 2 maps using the step by step instructions.

Load the data in your Carto.

After you upload the .csv file, you will be brought to the `Map View` screen of your map, and you likely see orange dots, displaying the LAT/LONG information of your dataset. 

![](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_advanced_2.png?raw=true)

Give a name to your map in the `Untitled` area in the upper left corner and that go to the `Data View`. 

Notice that the `geometry` field in the table displays the information you pointed out in the `LATITUDE` and `LONGITUDE` columns.

> **TIP:** In case you only have the address and not the LAT/LONG information, Carto can retrieve the information for you for free for up to 100 columns. For anything bigger than that, you will have to pay. If the number of addresses is not too large you can split the file into batches of 100 and then ensamble it all back together. If you don’t want to pay anything, [this awesome website](http://www.findlatitudeandlongitude.com/batch-geocode) will get the LAT/LONG in a batch for you. [This site](http://stevemorse.org/jcal/latlon.php) by Stephen P. Morse will also help you with batch geocoding (it also has a nice FAQ about address data). You can go also to [http://www.latlong.net](http://www.latlong.net/) to get the LAT/LONG information one address at a time.

Your dataset will probably already be georreferenced. But, more importantly, you will need to change the designation of the dates in your dataset, by going to the `Incident_Date` column and changing the data type to “Date”. Carto will do it for you automatically.   

![](https://github.com/miguelpaz/jlab/blob/master/images/cartodb_data%20type.png?raw=true)

This is very important because it will animate your map based on the dates over time you have in the dataset. If the Carto tool doesn’t recognize a date there, it will choose other data, if any, to serve as time reference. 

## Visualizing the information

Proceed to the `Map View` tab, and then to the `Wizards` window on the right tab (*I assume you already know that basic stuff based on the last tutorials*). 

One of the options right on the top is `Torque`. This will allow your data to pop in the screen based on their dates. Also in this window, don’t forget to change the `Time Column` to `Incident_date`, or else it will show incorrect data as the date. 

Also, check the `Cumulative` box to accumulate all the dots to have a bigger notion about mass shootings in the country, and putting everything into 10 seconds. I am also setting the trails to 1, so the dots will blend, but not so much.

I am changing the color to red, since I will use a dark basemap, for stronger impact.

This is the general outlook of the map:

![](https://github.com/miguelpaz/jlab/blob/master/images/cartodb_torque2.png?raw=true)

[You can find the interactive version here.](https://voltdatalab.cartodb.com/viz/783c9b64-3d4e-11e6-94da-0e8c56e2ffdb/public_map)

## Be a Pro

Try making a *heatmap* with cumulative effects over 30 seconds, with even more trails. 

#### How you can contribute 

*Do you have suggestions on how to improve this tutorial? Are there any broken links, typos or something else not working? You can contribute by opening a new issue.* 
