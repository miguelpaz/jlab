# Excel Basics: Introduction to structuring data, calculations, functions, pivot tables, and CSV 

Excel is one of the most used software's to work with data for storytelling. There are many others, with different capabilities and characteristics. However, to learn Excel is a excellent first step into getting acquainted with **how to organize and analyze information** to find and produce stories. 

A few reasons to do this:
><div class="align-left">"Becoming knowledgeable in searching, cleaning, and visualizing data is transformative for the profession of information gathering, too. Journalists who master this will experience that building articles on facts and insights is a relief. Less guessing, less looking for quotes — instead, a journalist can build a strong position supported by data and this can affect the role of journalism greatly".</div>**[Introduction to the Data Journalism Handbook](http://datajournalismhandbook.org/1.0/en/introduction_1.html)**

In this tutorial we will use small sets of data to: 

 - Understand how data is structured in spreadsheets.
 - Learn how to use basic formulas, functions and do calculations.
 - Visualize data with Pivot Tables. 
 - Work with data in .CSV format. 

Everything you will learn here, can be applied with slight differences in Google Spreadsheets.

For this introduction to Excel, you will need to: 

1. Have Excel installed in your computer
2. [Download the example data]**(PENDING LINK)** 
___


----------

#### Data formats: Unstructured v/s Structured

When we write something, by default, we are organizing information. We give it a title and write paragraphs. This is what we call "unstructured" data. And it's important to know the difference between "unstructured" and "structured" data, to get started in working with Excel, Google Spreadsheets and, further down the line, databases. 

 - [**"Unstructured data"**](http://www.webopedia.com/TERM/U/unstructured_data.html) is information such as text and multimedia files (word documents, images, videos, audios, emails...) that is not organized in rows and columns within a spreadsheet and/or a database.

**Example:** 
Hello, my name is John Doe, I am 40 years old, I am a male, I have blonde hair, I am 5,9 feet tall and I weight 220 pounds.
 
 - [**"Structured data"**](http://www.webopedia.com/TERM/S/structured_data.html) is information that is organized in fixed fields in spreadsheet files and databases that we can interview or make questions to (query). To do so, we must define "what fields of data will be stored and how that data will be stored: data type (numeric, currency, alphabetic, name, date, address) and any restrictions on the data input (number of characters; restricted to certain terms...)". 

**Example:**



**Note about columns, rows and cells:** A spreadsheet is made of columns and rows. Columns are identified with letters (A to Z) and rows are numbered (from 1 to...). The intersection of a column and a row is a cell. Every cell in a spreadsheet has its own identifier made of a `column letter + row number`. The upper left first cell of a spreadsheet, for example, is `column A + row 1 = cell A1`, the next is `B1`, `C1`, etc. Following the logic, the cells in the row below are `A2`, `B2`, `C2`, etc.  If you are ever lost, select a cell and look at the upper left side of your spreadsheet for a box with it:

![cell id](https://github.com/miguelpaz/jlab/blob/master/images/excel_cell_id.png)

