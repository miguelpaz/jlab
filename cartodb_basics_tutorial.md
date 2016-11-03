# Making a map in Carto without geolocation data 

Maps are a good way to visualize data about places, geographic patterns, show change over time and obviosuly when a story is completely based on geography.

You can use Maps to show comparisons, proportions, relationships, hierarchy, parts to a whole, distribution of elements, patterns and
<a href="http://www.ericson.net/content/2011/06/mapping-the-news/" target="_blank">more</a>. Always beware, as Matthew Ericson writes in <a href="http://www.ericson.net/content/2011/10/when-maps-shouldnt-be-maps/" target="_blank">"When Maps Shouldn't be Maps"</a>: **just because something can be mapped, it does not mean it should be mapped**. Avoid creating maps “when the interesting patterns aren’t geographic patterns” and “when the geographic data is more effective for analysis”. And always <a href="https://source.opennews.org/en-US/learning/distrust-your-data/" target="_blank">distrust your data</a> (specially when it has <a href="http://fusion.net/story/287592/internet-mapping-glitch-kansas-farm/" target="_blank">IP addresses</a> in <a href="http://fusion.net/story/290772/ip-mapping-maxmind-new-us-default-location/" target="_blank">it</a>).

With that said, in this short tutorial, we will create a Map with data from a .CSV file with <a href="https://www.carto.com" target="_blank">Carto</a>. 

Carto (kwon before July 2016 as CartoDB) is one of the best tools out there to create web maps. You can make interactive maps, download static image files and customize colors and points. And it is free if you are OK with using the basic features plan (which includes enough resources by most standards).

However, there are a few tricks in both better representing your data and making your map look good. 

This brief tutorial will teach how to use the most basic Carto tools to create a map that tells one simple clear story, with few data points.

You will need: 

1. <a href="https://raw.githubusercontent.com/miguelpaz/jlab/master/data/cartodb_example_1_countries.csv" target="_blank">This example .csv dataset</a>
2. An account in <a href="https://www.carto.com" target="_blank">Carto</a>
3. Bookmark the <a href="https://carto.com/docs/carto-editor/" target="_blank">Carto Editor</a> documentation. It includes every detail about working with the Carto maps editor.

___

## Using the dataset

The example dataset bears no mystery at all. It shows countries where same-sex marriage is legally allowed, and holds only three columns of information: country, year and source. The data is from the <a href="http://www.pewresearch.org/topics/gay-marriage-and-homosexuality/" target="_blank">Pew Research Center</a>.

With only two of those columns it is possible to have a good, descriptive graphic representation about same sex-marriage in the world. 
Lets load the data. 

If you already have an account in Carto, login and right away click on the green button *New Map*. 

![Carto - New Map](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic.png?raw=true)

This will take you to a screen so you can *Add a Dataset*. 

There are dozens of ways you can upload your data into the Carto server. One of it's great features is that it accepts several kinds of data formats (like CSV, XLS, ZIP, KML, GPX), and you can use their data library, connect your data from Dropbox, Twitter, Google Drive or upload a data file that you have in your computer.

In our case, we will use a .csv file from a URL. [This is the dataset you will use for this tutorial](https://raw.githubusercontent.com/miguelpaz/jlab/master/data/cartodb_example_1_countries.csv).

Copy the URL of the dataset, then click on the *Data File* tab and paste the URL, above in the white input field, then click *Submit* and then in the green button on the bottom *Connect Dataset*.

![Carto - data](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_data.png?raw=true)

This will lead you to a map canvas with some orange polygons in it. Polygons are the shapes and color fill of all geographic borders of countries (or regions, cities, neighborhoods, etc.). Great, you basically have a map now.

Carto has powerful geocoding features and it will understand things like country names (instead of lat/long, for example) and geocode them from your column containing country names. 

> WARNING: if you have repeated or misspelled country names, or somehow does not comply with the standards adopted by Carto, it may not work. Be sure to always check how your data is formatted. 

You could just put a title like “Countries in the World Where Same-sex Marriage is Allowed” and publish it, but you can make it even better. Lets see how to do that. 

![Carto - map with no customization](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_no_custom.png?raw=true)

In the *Data View* tab, you can see how the data was automatically parsed by CartoDB when you uploaded from the URL. 

![Carto - parsed data](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_data_view.png?raw=true)

## Customizing your map

Now that you have successfully uploaded your data, lets add a title and some metadata, in the upper left corner of your screen, by clicking in *Edit Metadata*. This is not necessary, but it is a good practice.

Now, lets adjust the look of the map. In the right side of your screen, there will be a tab with several options - *Sql*, *Wizards*, *Infowindow*, *Cartocss*, *Legends* and *Filters*. For this tutorial, we will only focus in the *Wizards*. 

Click on the *Wizards* tab. You will see some options that you can configure on your map. 

1. Simple - plain color fill of a polygon or point
2. Choropleth - used to describe intensity of the data in certain areas
3. Category - color the polygons according to an assigned category
4. Bubble - shows the size of the data in certain areas

We are already by default using the *simple* type and, as the *Category* and the *Bubble* are meant to show sizes, intensity and dimensions of certain values (which we don’t have in this dataset), we will choose the *Category* type - just so you know how it looks like. It may want to proceed with the *simple* or the *category* option.

Remember: this example dataset only contains country name, year and source, not other data points. 

You map should look like this: 

![Carto - Wizards](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_category.png?raw=true)

## Change the map background

Carto offers a series of *basemaps*, or the background maps you will use. This option is in the lower left corner of the screen under *Change basemap*.

Click there and choose a basemap. Let's pick *CartoDB World Eco* (you may choose another one if you want).

![Carto - basemap](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_basemap.png?raw=true)

Now we have a category-colored, background-customized map with year labels in it. We are just missing a proper title and the source. 

On the upper left corner, go to `Add element -> Add title item` and put the title you think it is best. If you don’t know where to put the title box, you can go to `Options -> Fixed-title` and it will automatically add an upper bar with the title you gave your map earlier, in the metadata section. That is what we will do for this tutorial.

To add a source or annotation items, go to `Add element -> Add text item`. In this case we want to credit Pew Research Center as the source of the data, and then change the text size to 14px.

Now we are settled. Click export image or publish your map!

It should look something like this:

![Carto - Final](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_finalmap.png?raw=true)

Here is the <a href="https://miguelpaz.carto.com/viz/089e3328-4acb-11e6-b760-0ee66e2c9693/public_map" target="_blank">published map</a>.

## Be a pro

Change the custom colors in the <a href="https://carto.com/docs/carto-editor/maps/#cartocss" target="_blank">*CartoCSS editor*</a> tab, add interactivity functionalities, publish the map and share the link.  

#### How you can contribute 

*Do you have suggestions on how to improve this tutorial? Are there any broken links, typos or something else not working? You can contribute by opening a new issue.* 

