# Working on your data with CSVKit

CSVKit is a nice tool to manipulate, organize, analise and work with data. It is very light and fast, and is designed for people who don’t like working with Excel or GoogleSheets all the time. It is built in the Python programming language.

To access it, you will need to use the `command line`. Open the Terminal  in Mac OSX or Command Prompt in Windows for that. 

This tutorial is simple and explanatory, and it is based on the great documentation in the [CSVKit tutorial page](https://csvkit.readthedocs.io/en/540/tutorial.html), which has a lot more things, many of which you might not use right away.

## Installation 

There are several ways to install CSVKit in your machine. 

You will need to have the most recent release of Python in your computer. [Download it here](https://www.python.org/downloads/). 

A lot of people like to use `pip` to [install stuff](https://www.python.org/downloads/) in their computers, which comes with the Python package. Journalist and coder Amanda Bee has [wrote about installing CSVKit](https://github.com/amandabee/CUNY-data-storytelling/wiki/Tutorial:-Installing-CSVKit) in her CUNY data storytelling class, for Mac (OSX) users. The bullets are from her: 

* Use sudo `easy_install` csvkit to install CSVkit. Then [read a bit](http://csvkit.readthedocs.org/) about what it does. If you secretly think you'll never touch the terminal again after this semester, this is your best route.
* Install [Homebrew](http://brew.sh/). Then do `pip install csvkit` at the command line. If you get an error that suggests you don't have permission to install it, try `sudo pip install csvkit to install` with root privileges. Try `man sudo` if you want to understand what the command does. If you want to explore more programming, this is probably your best option.
* Alternatively, you can install pip with easy_install (using sudo easy_install pip) and then install CSVkit with sudo pip install csvkit. Choosing this option won't mean you can't install Homebrew later.

For Windows users as well, `pip` is already installed if you're using Python 2 >=2.7.9 or Python 3 >=3.4 downloaded from [Python.org](python.org), but you'll need to [upgrade pip](https://pip.pypa.io/en/stable/installing/#upgrading-pip).

Here is the message when your are done: 

			Installing collected packages: xlrd, sqlalchemy, openpyxl, six, dbf, csvkit
		  Running setup.py install for xlrd ... done
		  Running setup.py install for sqlalchemy ... done
		  Found existing installation: openpyxl 2.2.0
		    Uninstalling openpyxl-2.2.0:
		      Successfully uninstalled openpyxl-2.2.0
		  Running setup.py install for openpyxl ... done
		  Found existing installation: six 1.5.2
		    Uninstalling six-1.5.2:
		      Successfully uninstalled six-1.5.2
		  Running setup.py install for dbf ... done
		  Running setup.py install for csvkit ... done
		Successfully installed csvkit-0.9.1 dbf-0.94.3 openpyxl-2.2.0b1 six-1.10.0 sqlalchemy-1.0.13 xlrd-0.9.4

—

## Basics of CSVKit

After you are done installing it, now it is time to use it!

First, lets create a new directory to store the data you will be working with. I recommend calling it `csvkit_data`. 

So run this in the command line: 

			mkdir csvkit_data

Now, go to that directory:

			cd csvkit_data

And then, lets fetch some data to use, analyze, manipulate and play with. We prepared some data for you (csv format) about the GDP per capita all over the work, according to the IMF database. [Access the data here:](https://raw.githubusercontent.com/miguelpaz/jlab/master/data/csvkit_example_data.csv)

Now lets load it to that directory:

			curl -L -O https://raw.githubusercontent.com/miguelpaz/jlab/master/data/csvkit_example_data.csv

Finally, lets take a look at the data with the command `csvlook`, to see what we will analyze.

			csvlook csvkit_example_data.csv

The data will look messy, and it is way visually better to see it in an Excel or Google Sheets, but this is just to have a general outlook, not to really read it. 

Another command you may use is `csvcut`, which lets you see and cut the columns of you data files. 

Lets look at the column headers, to see what we will need. Run: 

			csvcut -n csvkit_example_data.csv
			  1: country
			  2: 2001
			  3: 2002
			  4: 2003
			  5: 2004
			  6: 2005
			  7: 2006
			  8: 2007
			  9: 2008
			 10: 2009
			 11: 2010
			 12: 2011
			 13: 2012
			 14: 2013
			 15: 2014

So now you see that the GDP data is organized with one columns with the country names, and the rest with the years, while the respective rows will carry the information. 

Lets say there is too much data, and you only want to know how was the GDP per capita in those countries during the 2008/2009 financial crisis, and a couple of years later just to see how the wealth grew. 

For that, lets use the `csvcut` again. 

				csvcut -c 1,9,10,11,12 csvkit_example_data.csv

*If you are using non-numbered columns, you might as well just write their names instead of the assigned numbers*

CSVKit allows you what they call “pipe” actions, which basically means to write in the same line, to save time, several functions, separated by a | bar. Try this: 

				csvcut -c 1,9,10,11,12 csvkit_example_data.csv | csvlook | head

___

## Playing with the numbers

CSVKit has a command called `csvstat`, which basically lets you to get a succinct analysis out of your data, before you can really dig into it you want. 

It gives you the minimum of a certain column, the maximum, the average, the median and even standard deviation. 

				csvcut -c 1,9,10,11,12 csvkit_example_data.csv | csvstat

You will get something like this:

				csvcut -c 1,9,10,11,12 csvkit_example_data.csv | csvstat
				  1. country
					<type 'unicode'>
					Nulls: False
					Unique values: 199
					Max length: 30
					
				  2. 2008
					<type 'float'>
					Nulls: False
					Min: 0.0
					Max: 193648.1
					Sum: 3156734.6
					Mean: 15862.9879397
					Median: 4912.3
					Standard Deviation: 25667.7567268
					Unique values: 197
					5 most frequent values:
						0.0:	3
						7112.4:	1
						3920.0:	1
						9999.1:	1
						4342.8:	1

You can see, for instance, that in 2009, after the financial crash, the median of the GDP per capital was lower than in 2008, but it grew back in 2010 and 2011. 

Another great function of this is to “query” the data to find what you want. Lets say you only need to look for the the numbers about Brazil.

				csvcut -c 1,9,10,11,12 csvkit_example_data.csv | csvgrep -c country -m Brazil | csvlook

Please be advised that the query is case sensitive, *BRAZIL* or *brazil* won’t find anything. 

Now, in case you haven’t noticed, the csv is alphabetical order. If you want you want to sort it out differently, lets say in reverse, use the following code.  

				 csvkit_example_data.csv | csvsort -c country  -r | csvlook  

The `-r` actually means `reverse`. If you want to know all the sorting functionalities, [check this page](https://csvkit.readthedocs.io/en/540/scripts/csvsort.html). 

