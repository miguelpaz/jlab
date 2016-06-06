# Making a chart in CartoDB without geolocation data 

Making charts is one of the coolest things in data journalism. It is really a good way to visualize data about places, that sometimes it just won’t fit a normal type of chart. 

[CartoDB](https://voltdatalab.cartodb.com) is one of the best tools out there to do that. You can make interactive maps, download static image files and customize colors and points. And it is free if you are OK with using their more basic resources (which are good by most standards).

However, there are a few tricks in both better representing your data and making your map look good. 

This tutorial will teach how to use the most basic CartoDB tools, and that, even when you have few data points to show, it is still a good visual approach to use. 

For this tutorial you will need: 

1. [This example dataset](https://raw.githubusercontent.com/miguelpaz/jlab/master/data/cartodb_example_1_countries.csv)
2. An account in [CartoDB](https://voltdatalab.cartodb.com)

___

## Using the dataset

The example dataset bears no mystery at all. It shows countries where same-sex marriage is legally allowed, and holds only three columns of information: country, year and source. Data is from the [Pew Research Center](http://www.pewresearch.org/topics/gay-marriage-and-homosexuality/).

However, with only two of those columns, it is possible to have a good, descriptive graphic about same sex-marriage in the world. 

Lets load the data. 

If you already have an account in CartoDB website, login and right away click on the green button *New Map*. 

![CartoDB - New Map](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic.png?raw=true)

This will take you to a screen so you can *Add a Dataset*. 

There are dozens of ways you can upload your data into the CartoDB server. It accepts several kinds of data formats (like CSV, XLS, ZIP, KML, GPX), and you can use their data library, connect your data from Dropbox, Twitter, Google Drive or upload a data file that you have in your computer.

In our case, we will use a .csv file from a URL. [This is the dataset you will use for this tutorial](https://raw.githubusercontent.com/miguelpaz/jlab/master/data/cartodb_example_1_countries.csv).

Click on the *Data File* tab and paste the URL above in the white input field, than click *Submit* and then in the green button on the bottom *Connect Dataset*.

![CartoDB - data](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_data.png?raw=true)

This will lead you to a map canvas with some orange polygons in it. Polygons are the shapes and color fill of all geographic borders of countries (ou regions or cities). Great, you basically have a map now.

CartoDB is a good tool and, when working with a more general kind of information - like country names - it can geocode your data by itself, without any settings from you, just from your column containing country names. 

> WARNING: if you have repeated or wrongly spelled country names, or that somehow miss the standards adopted by CartoDB data, this resource could not work. 

You could just put a title like “Countries in the World Where Same-sex Marriage is Allowed” and publish it, but you can make it even better. Lets see how to do that. 

![CartoDB - map with no customization](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_no_custom.png?raw=true)

In the *Data View* tab, you can see how the data was automatically parsed by CartoDB when you uploaded from the URL. 

![CartoDB - parsed data](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_data_view.png?raw=true)

## Customizing your map

Now that you have successfully uploaded your data, lets add a title and some metadata, in the upper left corner of your screen, by clicking in *Edit Metadata*. This is not necessary, but it is a good practice.

Now, lets adjust the look of the map. In the right side of your screen, there will be a tab with several options - *Sql*, *Wizards*, *Infowindow*, *Cartocss*, *Legends* and *Filters*. For this tutorial, we will only focus in the *Wizards*. 

Click on the *Wizards* tab. You will see some options that you can configure on your map. 

1. Simple - plain color fill of a polygon or point
2. Choropleth - used to describe intensity of the data in certain areas
3. Category - color the polygons according to an assigned category
4. Bubble - shows the size of the data in certain areas

We are already by default using the *simple* type and, as the *Category* and the *Bubble* are meant to show sizes, intensity and dimensions of certain values (which we don’t have in this dataset), so we will check the *Category* type - just so you know how it looks like. It may want to proceed with the *simple* or the *category* option.

Remember: this example dataset only contains country name, year and source, not other data point. 

You map should look like this: 

![CartoDB - Wizards](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_category.png?raw=true)

## Change the map background

CartoDB offers a series of *basemaps*, or the background maps you will use. This option is in the lower left corner of the screen.

Click there and choose a basemap. This tutorial chooses *CartoDB World Eco*. You may choose the one you want.

![CartoDB - basemap](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_basemap.png?raw=true)

Now we have a category-colored, background-customized map with year labels in it. We are just missing a proper title and the source. 

On the upper left corner, go to `Add element -> Add title item` and put the title you think it is best. If you don’t know where to put the title box, you can go to `Options -> Fixed-title` and it will automatically add an upper bar with the title you gave your map earlier, in the metadata section. That is what this tutorial will do.

To add a source or annotation items, go to `Add element -> Add text item`. We are adding that the data comes from Pew Research Center, and then change the text size to 14px.

Now we are settled. Click export image or publish your map!

It should look like this:

![CartoDB - Final](https://github.com/miguelpaz/jlab/blob/master/images/map_cartodb_basic_finalmap.png?raw=true)

## Be a pro

Change the custom colors in the *CartoCSS editor* tab, add interactivity functionalities, publish the map and share the live link. 
