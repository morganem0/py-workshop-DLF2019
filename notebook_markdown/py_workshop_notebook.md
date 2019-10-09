
# Practical Python Tools for Metadata Assessment: 55-minute workshop

## Welcome

Welcome to the workshop! This is meant to be a a fun and beginner-friendly introduction to a few useful Python tools, in the context of exploring and manipulating tabular metadata for digital collections.   

In this session, we will focus on some basic functions of Python's pandas data analysis library. We will use pandas for exploring, filtering, reshaping, and merging datasets. 

This notebook provides code that you can execute to see results and generate outputs in the notebook itself, as well as explanations for the examples and exercises we'll be working through together. 

At the end of the notebook, there is a bonus example about dealing with duplicates, and a list of recommended resources for further exploration on your own. 

### Table of Contents

* [Workshop Plan](#wplan)
* [Introduction](#intro)
* [Using this Jupyter Notebook](#usingjn)
    * [Exercise 1: Modify this notebook](#ex1)
    * [Exercise 2: Run code and markdown in cells](#ex2)
* [Example 1: Explore a dataset](#md1)
    * [Exercise 3: Try out pandas methods](#ex3)
* [Example 2: Compare a group of metadata files](#md2)
    * [Exercise 4: Evaluate subjects data in a collection](#ex4)
* [Example 3: Merge information from separate files](#md3)
    * [Exercise 5: Other ways to merge](#ex5)
* [Bonus Example: Find and remove duplicates](#md4)
* [Resources](#res)


## Workshop Plan <a name="wplan"></a>

We will start with a quick demo in using the jupyter notebook and a couple exercises to get familiar with notebook commands. 

Then we will walk through three examples of using Python/pandas with digital collections metadata files.  
After each example there will be an exercise you can try out on your own.  


----
  
**Intro, & using the jupyter notebook (10 mins)**
    * Exercises 1 & 2: how to add cells, execute code and markdown cells
    
**Example 1: Explore a dataset (12 mins)** 
    * Exercise 3: Evaluate subjects data from a collection
    
**Example 2: compare a group of metadata files (12 mins)**
    * Exercise 4: 
    
**Example 3: Merge info from separate files (12 mins)**
    * Exercise 5 : other merges  
    
**Wrap-up (5 mins)**
    * review resources, and info about installing python

----



## Introduction to Python and pandas<a name="intro"></a>
(basic info about Python)

(basic info about Pandas)

## Using this Jupyter Notebook <a name="usingjn"></a>

You can edit the notebook to run code cells and generate output, and/or to add markdown cells.  

All paths in the notebook refer to locations within the repository, to access example data and/or save output files. 

### Keyboard Shortcuts for Jupyter Notebook :

* `CTRL` + `SHIFT`+ `P` : show 'command palette'
* `esc` : command mode
* `enter` : edit mode
* `a` : insert cell above
* `b` : insert cell below
*  `SHIFT` + `enter`: run a code cell (or render a markdown cell)
* `d d`: delete a cell

###  Exercise 1: Modify this Notebook<a name="ex1"></a>

Follow the instructions below to try out some of the jupyter keyboard shortcuts and get familiar with working in this notebook.

**check out the 'command palette' to see all notebook actions and shortcuts**

From the command palette, you can search for any command, and run that action directly from the palette, as well as seeing the shortcut for that action if available. 

1. Press ``CTRL + SHIFT+ P`` to show the command palette. 
    * With the palette open, search for 'edit', to find the shortcut for `enter 'edit' mode`. Click on this action from the list. This cell will then switch into 'edit' mode. 

**Use shortcuts to switch between edit and command mode**

Edit mode: used for adding/editing content in cells = Blue cell border

Command mode: used for navigating and modifying cells = Green cell border    

* Double-click in this cell to switch the cell into 'Edit mode.' 
* When you double click inside the cell, the cell border will change from blue to green, and the markdown will switch from rendered to markup text.
* Press `Esc` to switch back to 'command' mode. The cell border switches back to blue and you can use navigation commands (such as adding cells below/above, switching from code/markdown.)  
* Practice switching back and forth between edit/command on a few cells. 


**Edit the text in a Markdown cell, execute (render) a Markdown cell**

* Switch this cell into 'edit mode'. 
* Add a bullet point below these lines of text and type something, for example: ``'DONE'``. (can copy/paste example below if easier!)
* Then use `CTRL` + `Enter` to "run" the cell/render the markdown.  
    * for example: `DONE`   



**Add more cells**

* With this cell in command mode (blue border), add a cell underneath it, then add some cells above the cells you added. 
    * press `b` to add a cell below an existing cell. 
    * You can keep pressing `b` to add more cells; it doesn't hurt anything to have empty cells in the notebook. 
    * press `a` to add a cell above an existing cell. 


```python

```

### Exercise 2: Add and run code and Markdown in cells <a name="ex2"></a>

Practice with creating cells, switching cells from code to Markdown, adding content to cells and running them. 

**Create a Markdown cell, add some text**

create a Markdown cell: 
* click on one of the empty cells you created in Exercise 1, or just create another one here. 
* A brand-new cell will be in command mode (blue cell border)  
* if there's an `In [ ]:` to the left of the cell, this means it's a code cell. Any text you type into the cell will be treated as code. 
* To convert the cell to a Markdown cell, press `m` to switch the cell to markdown.  
    * The `In [ ]:` to the left of the cell will disappear, indicating it is now a Markdown cell. Any test you type into the cell will now be treated as markdown. 
* If this did not work, make sure the cell is in command mode. Switch to Command mode by pressing `Esc`. The cell border will turn blue. 

add text in a Markdown cell: 
* Switch the cell to Edit mode by clicking inside it. 
* In the markdown cell, type a header, and then some regular text. For example: 

    ```
    #### here's an example header  
    and some regular paragraph text 
    ```


```python

```

#### here's an example header  
and some regular paragraph text 

**Execute/render a markdown cell**

* As you did in exercise 1, press `CTRL` + `Enter` to "run" the markdown cell/render the markdown that you just typed.  
* the text will display as a formatted version, and the cell border will switch from green to blue. 


**Add code to a code cell**

Work with a code cell: 
* Click on one of the empty cells you have created, or just create a new one here. 
* Look for the `In [ ]:` to the left of the cell, to make sure it's a code cell. 
* if there's no  `In [ ]:` to the left of the cell, switch into Command mode and convert the cell to Code by pressing `y`. 
* Switch the cell back to Edit mode by clicking inside it. The cell border will turn green. 

Add some code: 
* Type a line of simple python code. For example: 

     ```
     print("here's a line of python code output.")
     ```


**Run the code cell.**

* As you did with the markdown cells, press `CTRL` + `Enter` to run the cell and execute the code in it. 



```python
## note that in a code cell, hashtags indicate a comment, not a header as in a markdown cell

print("here's a line of python code output.")

```

    here's a line of python code output.



```python

```

## Metadata Example 1: Explore a Dataset with pandas<a name="md1"></a>

This example walks through getting oriented with using python/pandas for viewing and analysing descriptive metadata files.

In this scenario we are working with a small group of metadata files that have varied sets of inconsistently organized fields.   

We will import metadata from csv and tsv files, exclude empty and/or irrelevant fields from our dataframes, and identify a few relevant fields to focus on for assessment, selecting the same set of fields from each collection. 

**Learning objectives in this example:**

* reading a data file into a dataframe
* creating dataframes with differently delimited data
* assessing overall size and contents of the dataframe
* selecting relevant columns to include for a task
* identifying and changing datatypes


#### Import libraries for Python

Importing libraries loads them into memory so that Python can use them. 

Libraries provide specific methods for particular kinds of work. 

We are importing: 
* the pandas data analysis library
* `os` for working with files and directories  
* `matplotlib` for generating some basic graphs from data

Setting `%matplotlib inline` allows plots to render within the notebook. 



```python
# import pandas and os libraries 
import pandas as pd
import os
import matplotlib.pyplot as plt
%matplotlib inline
```

#### Next: check that we are in the right place!!

We'll do a couple quick checks to get oriented and make sure that we're in the right directory. 

This is not really necessary, because this notebook is located in/running from within the 'notebook_exercises' subfolder, so we already know that we will be running commands relative to that location, but it's always nice to take a look around to see where you are. 


```python
# os.getcwd() outputs the current working directory, similar to pwd in bash

os.getcwd()
```




    '/home/jovyan/notebook_exercises'




```python
# os.listdir() with no parameter returns a list of the files and directories in the current working directory

os.listdir()
```




    ['filesizes',
     'output',
     'py_workshop_notebook.ipynb',
     'exampleData',
     '.ipynb_checkpoints']




```python
# use os.listdir() plus a parameter to see what's in the exampleData subfolder

os.listdir('./exampleData/')
```




    ['03823_masters.csv',
     'coll_dupes_example.csv',
     'maps.csv',
     '60001.txt',
     '03823_metadata.txt',
     '03883.txt',
     '03823_access_images.csv']



#### Create a dataframe from example datasets

A dataframe is a Python object with rows and columns that can be selected for running calculations and manipulating the data in a lot of ways. 

You can read many different data formats into a dataframe, including csv, tsv, and even excel sheets. 

The command below uses the variable name 'maps' for creating a dataframe using the pandas `read_csv` function. 


```python
# create a dataframe: 'maps' from the example datasheet 

maps=pd.read_csv("./exampleData/maps.csv")
```

#### Inspect a dataframe

Next, we'll explore the maps dataframe with pandas attributes and methods, to get a sense of how large this datset is (how many rows and columns), what the column headers are and how many of them are empty, and what the datatypes are in each column. 

* shape
* columns 
* info() 


```python
# the shape attribute displays the number of rows and columns for the dataframe, to get a sense of its overall size

maps.shape
```




    (161, 36)




```python
# columns attribute displays column labels

maps.columns
```




    Index(['Title', 'Alternative Title', 'Creator', 'Contributor', 'Creation Date',
           'Date', 'Search by Decade', 'Description', 'Subject (tgm)',
           'Subject Topical', 'Subject Name', 'Subject Geographic', 'Title Note',
           'DCMI Type', 'Caption', 'Contributor Note', 'Notes', 'Original Form',
           'Resource Type', 'Geographic Location', 'Language Code', 'Language',
           'Physical Description of Original', 'Medium of Original',
           'Collection in Repository', 'Digital Collection', 'N.C. Ed. Standard',
           'URL', 'Local Identifier', 'Creator Identifier', 'filename',
           'Copyright', 'Usage Rights', 'Raw Scan Filename', 'Date created',
           'Date modified'],
          dtype='object')




```python
# the info method displays datatypes and numbers of values per column, and memory information

maps.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 161 entries, 0 to 160
    Data columns (total 36 columns):
    Title                               161 non-null object
    Alternative Title                   4 non-null object
    Creator                             161 non-null object
    Contributor                         51 non-null object
    Creation Date                       161 non-null object
    Date                                161 non-null object
    Search by Decade                    161 non-null object
    Description                         161 non-null object
    Subject (tgm)                       161 non-null object
    Subject Topical                     161 non-null object
    Subject Name                        161 non-null object
    Subject Geographic                  161 non-null object
    Title Note                          161 non-null object
    DCMI Type                           161 non-null object
    Caption                             7 non-null object
    Contributor Note                    50 non-null object
    Notes                               67 non-null object
    Original Form                       161 non-null object
    Resource Type                       161 non-null object
    Geographic Location                 150 non-null object
    Language Code                       161 non-null object
    Language                            161 non-null object
    Physical Description of Original    160 non-null object
    Medium of Original                  161 non-null object
    Collection in Repository            161 non-null object
    Digital Collection                  161 non-null object
    N.C. Ed. Standard                   0 non-null float64
    URL                                 0 non-null float64
    Local Identifier                    160 non-null object
    Creator Identifier                  154 non-null object
    filename                            161 non-null object
    Copyright                           161 non-null object
    Usage Rights                        0 non-null float64
    Raw Scan Filename                   158 non-null object
    Date created                        161 non-null object
    Date modified                       161 non-null object
    dtypes: float64(3), object(33)
    memory usage: 45.4+ KB


**Sorting dataframe columns**

Since the columns listed above are not ordered in a logical way, it's hard to look for a particular column label in the output. 

Dateaframes can be sorted by rows, columns, or values to present the data according to the order we specify. 

Below we'll display the column labels sorted alphabetically, which makes it easy to check if this collection has fields named  Title, Usage Rights, Date, etc. 



```python
# Sort the dataframe to order the output of column labels from the info() method

maps.sort_index(axis=1).info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 161 entries, 0 to 160
    Data columns (total 36 columns):
    Alternative Title                   4 non-null object
    Caption                             7 non-null object
    Collection in Repository            161 non-null object
    Contributor                         51 non-null object
    Contributor Note                    50 non-null object
    Copyright                           161 non-null object
    Creation Date                       161 non-null object
    Creator                             161 non-null object
    Creator Identifier                  154 non-null object
    DCMI Type                           161 non-null object
    Date                                161 non-null object
    Date created                        161 non-null object
    Date modified                       161 non-null object
    Description                         161 non-null object
    Digital Collection                  161 non-null object
    Geographic Location                 150 non-null object
    Language                            161 non-null object
    Language Code                       161 non-null object
    Local Identifier                    160 non-null object
    Medium of Original                  161 non-null object
    N.C. Ed. Standard                   0 non-null float64
    Notes                               67 non-null object
    Original Form                       161 non-null object
    Physical Description of Original    160 non-null object
    Raw Scan Filename                   158 non-null object
    Resource Type                       161 non-null object
    Search by Decade                    161 non-null object
    Subject (tgm)                       161 non-null object
    Subject Geographic                  161 non-null object
    Subject Name                        161 non-null object
    Subject Topical                     161 non-null object
    Title                               161 non-null object
    Title Note                          161 non-null object
    URL                                 0 non-null float64
    Usage Rights                        0 non-null float64
    filename                            161 non-null object
    dtypes: float64(3), object(33)
    memory usage: 45.4+ KB


#### View contents of the dataframe 

The head() and tail() methods in pandas display the first or last n rows of data. 

By default head or tails will display 5 rows; below we specify 3 to see fewer rows. 

Note that the column headers are no longer sorted alphabetically, because we did not apply the sort persistently.



```python
maps.head(3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Alternative Title</th>
      <th>Creator</th>
      <th>Contributor</th>
      <th>Creation Date</th>
      <th>Date</th>
      <th>Search by Decade</th>
      <th>Description</th>
      <th>Subject (tgm)</th>
      <th>Subject Topical</th>
      <th>...</th>
      <th>N.C. Ed. Standard</th>
      <th>URL</th>
      <th>Local Identifier</th>
      <th>Creator Identifier</th>
      <th>filename</th>
      <th>Copyright</th>
      <th>Usage Rights</th>
      <th>Raw Scan Filename</th>
      <th>Date created</th>
      <th>Date modified</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Redoubt C</td>
      <td>NaN</td>
      <td>Gilmer, Jeremy Francis, 1818-1883.</td>
      <td>Fitz, Newton.</td>
      <td>1861; 1862; 1863; 1864; 1865</td>
      <td>undated</td>
      <td>1860; 1861; 1862; 1863; 1864; 1865; 1866; 1867...</td>
      <td>A map of Redoubt C drawn under the direction o...</td>
      <td>Maps</td>
      <td>United States--History--Civil War, 1861-1865.;</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>276/182</td>
      <td>Gilmer Map Number 7</td>
      <td>276_182_E.tif</td>
      <td>Public Domain</td>
      <td>NaN</td>
      <td>276_182.tif</td>
      <td>2005-11-23</td>
      <td>2015-09-14</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Plan of Battery McIntosh</td>
      <td>NaN</td>
      <td>Gilmer, Jeremy Francis, 1818-1883.</td>
      <td>Fitz, Newton.</td>
      <td>1861; 1862; 1863; 1864; 1865</td>
      <td>undated</td>
      <td>1860; 1861; 1862; 1863; 1864; 1865; 1866; 1867...</td>
      <td>A map of the plan of Battery McIntosh, drawn u...</td>
      <td>Maps</td>
      <td>United States--History--Civil War, 1861-1865.;</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>276/183</td>
      <td>Gilmer Map Number 8</td>
      <td>276_183_E.tif</td>
      <td>Public Domain</td>
      <td>NaN</td>
      <td>276_183.tif</td>
      <td>2005-11-23</td>
      <td>2015-09-14</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Fort DeRussy on Red River, Louisiana</td>
      <td>NaN</td>
      <td>Gilmer, Jeremy Francis, 1818-1883.</td>
      <td>NaN</td>
      <td>1864</td>
      <td>1864</td>
      <td>1860; 1861; 1862; 1863; 1864; 1865; 1866; 1867...</td>
      <td>The plans of Fort DeRussy and obstructions of ...</td>
      <td>Maps</td>
      <td>United States--History--Civil War, 1861-1865.;</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>276/203</td>
      <td>Gilmer Map Number 196</td>
      <td>276_203_E.tif</td>
      <td>Public Domain</td>
      <td>NaN</td>
      <td>276_203.tif</td>
      <td>2005-12-08</td>
      <td>2015-09-14</td>
    </tr>
  </tbody>
</table>
<p>3 rows × 36 columns</p>
</div>



#### Explore a second dataset

You can also use the read_csv function for other kinds of delimiters. For example, you can specify tab-delimited as with the metadata file below. 



```python
# read in another example dataset as a separate dataframe. 
# use sep parameter to specify tab as delimiter

rev=pd.read_csv("./exampleData/60001.txt", sep='\t')
```

**View size and columns information for second dataset**

We'll again use shape and info() to get a basic sense of the second dataset. 

We can see that this data sheet has nearly twice as many column labels, and tons of empty fields.  


```python
rev.shape
```




    (538, 60)




```python
rev.sort_index(axis=1).info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 538 entries, 0 to 537
    Data columns (total 60 columns):
    Additional Display                         0 non-null float64
    Alternative Title                          0 non-null float64
    Author Chief Source                        0 non-null float64
    Caption                                    0 non-null float64
    Cataloging Agency                          0 non-null float64
    Collection Number                          538 non-null int64
    Collection in Repository                   538 non-null object
    Condition                                  0 non-null float64
    Container type                             538 non-null object
    Contributor                                0 non-null float64
    Contributor Note                           42 non-null object
    Coordinates                                0 non-null float64
    Copyright Holder                           0 non-null float64
    Creation Date                              538 non-null int64
    Creator                                    538 non-null object
    Creator Identifier                         538 non-null object
    Creator Nationality/Culture                0 non-null float64
    Current Location                           0 non-null float64
    Date                                       538 non-null object
    Date created                               538 non-null object
    Date modified                              538 non-null object
    Description                                504 non-null object
    Digital Collection                         538 non-null object
    Finding Aid                                538 non-null object
    Form                                       526 non-null object
    Has Part Of                                0 non-null float64
    Is Part Of                                 0 non-null float64
    Language                                   0 non-null float64
    Local Identifier                           0 non-null float64
    Location in Collection                     538 non-null object
    Map Details                                0 non-null float64
    Map Type                                   0 non-null float64
    Medium                                     0 non-null float64
    Notes                                      4 non-null object
    Object                                     538 non-null object
    Pagination                                 0 non-null float64
    Physical Description of Analog Original    0 non-null float64
    Place of Publication                       0 non-null float64
    Projection                                 0 non-null float64
    Publisher                                  0 non-null float64
    Related Resource                           0 non-null float64
    Resource Type                              526 non-null object
    Scale                                      0 non-null float64
    Search by Decade                           0 non-null float64
    Sort Me                                    0 non-null float64
    Sponsor                                    0 non-null float64
    StreamingFile                              0 non-null float64
    Style/Period                               0 non-null float64
    Subject (tgm)                              500 non-null object
    Subject Geographic                         538 non-null object
    Subject Name                               15 non-null object
    Subject Topical                            1 non-null object
    Subject Topical Other                      0 non-null float64
    Title                                      505 non-null object
    Title Note                                 0 non-null float64
    Transcription                              159 non-null object
    Usage Rights                               538 non-null object
    Volume/Issue                               0 non-null float64
    filename                                   538 non-null object
    geonamesid                                 0 non-null float64
    dtypes: float64(34), int64(2), object(24)
    memory usage: 252.3+ KB


#### Get rid of empty columns

Many of these columns are empty, so we will exclude them. 

Use the inplace attribute to apply this change to the dataframe we are currently working with.

Then check the columns again; our data is now more manageable. 



```python
# Drop empty columns. Inplace attribute overwrites the working dataframe. 
rev.dropna(axis = 1, how ='all', inplace = True)

# output updated dataframe
rev.sort_index(axis=1).info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 538 entries, 0 to 537
    Data columns (total 26 columns):
    Collection Number           538 non-null int64
    Collection in Repository    538 non-null object
    Container type              538 non-null object
    Contributor Note            42 non-null object
    Creation Date               538 non-null int64
    Creator                     538 non-null object
    Creator Identifier          538 non-null object
    Date                        538 non-null object
    Date created                538 non-null object
    Date modified               538 non-null object
    Description                 504 non-null object
    Digital Collection          538 non-null object
    Finding Aid                 538 non-null object
    Form                        526 non-null object
    Location in Collection      538 non-null object
    Notes                       4 non-null object
    Object                      538 non-null object
    Resource Type               526 non-null object
    Subject (tgm)               500 non-null object
    Subject Geographic          538 non-null object
    Subject Name                15 non-null object
    Subject Topical             1 non-null object
    Title                       505 non-null object
    Transcription               159 non-null object
    Usage Rights                538 non-null object
    filename                    538 non-null object
    dtypes: int64(2), object(24)
    memory usage: 109.4+ KB


#### Other ways to view and select data

The head() and tail() methods can also be applied to series as well as the whole dataframe. 

Use the head method to list the first twelve values in the Title field in our dataframe. 



```python
# View the first 12 rows of the Title column

rev.Title.head(12)
```




    0                                      Young protesters
    1                                 Yanukovych supporters
    2                                       Young protestor
    3                      Information van on a Kyiv street
    4      Protesters mingling outside the Central Terminal
    5                  Marching towards the Supreme Council
    6                                 Crazy orange hair day
    7                                 Young revolutionaries
    8     Yushchenko supporters rallying on Vokzal'na Sq...
    9                  Shevchenko and the Orange Revolution
    10                           Valenki for the protesters
    11         Orthodox procession in support of Yanukovych
    Name: Title, dtype: object



**Chaining methods**

You can chain methods together to apply another method to an object that has a method applied. 

For example, we can use the sort_values method to sort the Title series reverse-alphabetically (via the 'ascending' parameter set to false), then apply the head() method to view th first 12 values. 



```python
# View the first 12 values in the 'Title' series sorted alphabetically

rev.Title.sort_values(ascending=False).head(12)
```




    421                     [Duplicate: Folder 0007-Fashion]
    444                     [Duplicate: Folder 0007 Fashion]
    426                     [Duplicate- Folder 0007 Fashion]
    319           Zoomed out view of Maĭdan Nezalez︠h︡nosti
    322                             Zbigniew Bujak at Maidan
    295                   Zbigniew Bujak and his colleagues.
    28                                        Zbigniew Bujak
    356                   Yushchenko supporters with trident
    250            Yushchenko supporters showing peace signs
    8      Yushchenko supporters rallying on Vokzal'na Sq...
    506      Yushchenko supporters mingling behind barricade
    511                 Yushchenko supporter in front of bus
    Name: Title, dtype: object



**Specifying rows and columns**

The .loc method allows for selecting individual and multiple rows and columns. Below we'll focus on the ``'Title','Date', 'Usage Rights', and 'filename'`` columns, including all rows of the dataframe. 

We will use the tail() method to view the last n rows in these columns. 



```python
# specify multiple rows and columns by label with loc method 

rev.loc[:,['Title','Date', 'Usage Rights', 'filename']].tail(8)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Date</th>
      <th>Usage Rights</th>
      <th>filename</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>530</td>
      <td>NaN</td>
      <td>29 November 2004</td>
      <td>For copyright information or permissions quest...</td>
      <td>60001_df0005_023.tif</td>
    </tr>
    <tr>
      <td>531</td>
      <td>Maidan crowds</td>
      <td>29 November 2004</td>
      <td>For copyright information or permissions quest...</td>
      <td>60001_df0007_023.tif</td>
    </tr>
    <tr>
      <td>532</td>
      <td>Flags over Maidan</td>
      <td>27 November 2004</td>
      <td>For copyright information or permissions quest...</td>
      <td>60001_df0001_012.tif</td>
    </tr>
    <tr>
      <td>533</td>
      <td>NaN</td>
      <td>30 November 2004</td>
      <td>For copyright information or permissions quest...</td>
      <td>60001_df0005_050.tif</td>
    </tr>
    <tr>
      <td>534</td>
      <td>Women in the Orange Revolution</td>
      <td>29 November 2004</td>
      <td>For copyright information or permissions quest...</td>
      <td>60001_df0009_11.tif</td>
    </tr>
    <tr>
      <td>535</td>
      <td>Young protesters</td>
      <td>27 November 2004</td>
      <td>For copyright information or permissions quest...</td>
      <td>60001_df0003_021.tif</td>
    </tr>
    <tr>
      <td>536</td>
      <td>Protestor Vehicles</td>
      <td>10 December 2004</td>
      <td>For copyright information or permissions quest...</td>
      <td>60001_df0007_092.tif</td>
    </tr>
    <tr>
      <td>537</td>
      <td>NaN</td>
      <td>10 December 2004</td>
      <td>For copyright information or permissions quest...</td>
      <td>60001_df0009_33.tif</td>
    </tr>
  </tbody>
</table>
</div>



#### Working with dates 

Notice the format of the values in the 'Date' column above. Also, remember from the info() output that the datatype for 'Date' is currently 'object'. Right now python is viewing these dates as just strings, which limits what we can do with them. 

We can create a new column in the dataframe, using the `to_datetime` method to convert the 'Date' values to datatype 'datetime', which then has a lot of capabilities available to it. 



```python
# check the current datatype and values information for the `Date` column in the rev dataframe

rev.Date.describe()
```




    count                  538
    unique                  13
    top       10 December 2004
    freq                   196
    Name: Date, dtype: object




```python
# Create a new column 'datesformat', with the values from the Date column 
# Use to_datetime to convert the 'Date' values to the datetime datatype

rev['datesformat']=pd.to_datetime(rev['Date'])

rev.datesformat.head()
```




    0   2004-11-27
    1   2004-11-27
    2   2004-12-10
    3   2004-12-05
    4   2004-11-27
    Name: datesformat, dtype: datetime64[ns]




```python
# check the current datatype and values information for the new `datesformat` column in the rev dataframe

rev.datesformat.describe()

```




    count                     538
    unique                     13
    top       2004-12-10 00:00:00
    freq                      196
    first     2004-11-27 00:00:00
    last      2004-12-11 00:00:00
    Name: datesformat, dtype: object



**Inspect the dataframe with new column added**

Note that the new column will be added at the end of the dataframe. 



```python
# check the columns and dtypes in the rev dataframe

rev.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 538 entries, 0 to 537
    Data columns (total 27 columns):
    Title                       505 non-null object
    Description                 504 non-null object
    Transcription               159 non-null object
    Contributor Note            42 non-null object
    Notes                       4 non-null object
    Subject (tgm)               500 non-null object
    Subject Name                15 non-null object
    Subject Geographic          538 non-null object
    Subject Topical             1 non-null object
    Creator                     538 non-null object
    Finding Aid                 538 non-null object
    Collection in Repository    538 non-null object
    Collection Number           538 non-null int64
    Location in Collection      538 non-null object
    Object                      538 non-null object
    Container type              538 non-null object
    filename                    538 non-null object
    Creation Date               538 non-null int64
    Date                        538 non-null object
    Digital Collection          538 non-null object
    Usage Rights                538 non-null object
    Form                        526 non-null object
    Resource Type               526 non-null object
    Creator Identifier          538 non-null object
    Date created                538 non-null object
    Date modified               538 non-null object
    datesformat                 538 non-null datetime64[ns]
    dtypes: datetime64[ns](1), int64(2), object(24)
    memory usage: 113.6+ KB


**Apply the same columns to the maps dataframe**

Meanwhile, our maps dataframe is still available in working memory. 

Because the same column labels exist in the maps dataset, we can select out these columns from maps using .loc, the same way as we did with rev above.  



```python
# examine the same columns in the 'maps' dataframe
# tail method displays the last n rows

maps.loc[:,['Title','Date', 'Usage Rights', 'filename']].tail(8)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Date</th>
      <th>Usage Rights</th>
      <th>filename</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>153</td>
      <td>Part of Spotslyvania county</td>
      <td>undated</td>
      <td>NaN</td>
      <td>276_271_E.tif</td>
    </tr>
    <tr>
      <td>154</td>
      <td>Area around Culpepper courthouse, bounded sout...</td>
      <td>undated</td>
      <td>NaN</td>
      <td>276_272_E.tif</td>
    </tr>
    <tr>
      <td>155</td>
      <td>Area around Falmouth east to Potomac river</td>
      <td>undated</td>
      <td>NaN</td>
      <td>276_273_E.tif</td>
    </tr>
    <tr>
      <td>156</td>
      <td>Map of parts of Orange, Spotsylvania, Caroline...</td>
      <td>undated</td>
      <td>NaN</td>
      <td>276_274_E.tif</td>
    </tr>
    <tr>
      <td>157</td>
      <td>Military map of the country in the occupation ...</td>
      <td>undated</td>
      <td>NaN</td>
      <td>276_275_E.tif</td>
    </tr>
    <tr>
      <td>158</td>
      <td>Map of the Rappahannock River from Fredericksb...</td>
      <td>undated</td>
      <td>NaN</td>
      <td>276_276_E.tif</td>
    </tr>
    <tr>
      <td>159</td>
      <td>Incomplete and unidentified sketch of area in ...</td>
      <td>undated</td>
      <td>NaN</td>
      <td>276_330_E.tif</td>
    </tr>
    <tr>
      <td>160</td>
      <td>Pleasant Hill</td>
      <td>1864</td>
      <td>NaN</td>
      <td>276_207_E.tif</td>
    </tr>
  </tbody>
</table>
</div>



### Recap of Metadata Example 1

this example covered the following: 

* read data of different formats into a dataframe
* explore a dataframe as a whole, series within a dataframe, values in rows and columns
* filter datasets by sorting, selecting, and dropping columns
* work with multiple dataframes at once
* create a new column in a dataframe 
* format dates by converting column datatype with to_datetime




### Exercise 3: nameofexercise <a name="ex3"></a>


Try out some of the methods demonstrated above, with an example datasheet in this repository. 

Use the standard `df` variable name to create a dataframe from the '60001.txt' file.   

Note that this metadata file is not a csv, so you will need to specify the delimiter. 

The syntax for this is:
```
df=pd.read_csv('./exampleData/03883.txt', sep='\t')

```




```python
df=pd.read_csv('./exampleData/03883.txt', sep='\t')
```

View the shape and column labels of the dataframe. Then inspect the Title column, sorted alphabetically. 


```
df.shape  
```
```
df.info()  
```
```
df.Title.sort_values().head(12)  

```


```python
df.shape
```




    (899, 64)




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 899 entries, 0 to 898
    Data columns (total 64 columns):
    Collection in Repository                   899 non-null object
    Collection Number                          899 non-null int64
    Location in Collection                     899 non-null object
    Object                                     899 non-null object
    Container Type                             899 non-null object
    filename                                   899 non-null object
    Title                                      0 non-null float64
    Alternative Title                          0 non-null float64
    Creator                                    0 non-null float64
    Contributor                                0 non-null float64
    Creation Date                              0 non-null float64
    Date                                       0 non-null float64
    Description                                0 non-null float64
    Subject (tgm)                              0 non-null float64
    Subject Name                               0 non-null float64
    Subject Topical                            0 non-null float64
    Subject Geographic                         0 non-null float64
    Subject Topical Other                      0 non-null float64
    Coordinates                                0 non-null float64
    geonamesid                                 0 non-null float64
    Digital Collection                         0 non-null float64
    Repository                                 0 non-null float64
    Host                                       0 non-null float64
    Usage Rights                               899 non-null object
    Copyright Holder                           0 non-null float64
    Additional Display                         0 non-null float64
    Transcription                              0 non-null float64
    Caption                                    0 non-null float64
    Notes                                      0 non-null float64
    Title Note                                 0 non-null float64
    Contributor Note                           0 non-null float64
    Sponsor                                    0 non-null float64
    Related Resource                           0 non-null float64
    Author Chief Source                        0 non-null float64
    Publisher                                  0 non-null float64
    Place of Publication                       0 non-null float64
    Cataloging Agency                          0 non-null float64
    Is Part Of                                 0 non-null float64
    Has Part Of                                0 non-null float64
    Form                                       0 non-null float64
    Resource Type                              0 non-null float64
    Medium                                     0 non-null float64
    Condition                                  0 non-null float64
    Language                                   0 non-null float64
    Physical Description of Analog Original    0 non-null float64
    Creator Nationality/Culture                0 non-null float64
    Style/Period                               0 non-null float64
    Volume/Issue                               0 non-null float64
    Scale                                      0 non-null float64
    Projection                                 0 non-null float64
    Map Type                                   0 non-null float64
    Map Details                                0 non-null float64
    Current Location                           0 non-null float64
    path                                       0 non-null float64
    Local Identifier                           0 non-null float64
    Creator Identifier                         0 non-null float64
    Search by Decade                           0 non-null float64
    Pagination                                 0 non-null float64
    Sort Me                                    0 non-null float64
    StreamingFile                              0 non-null float64
    duracloudSpace                             0 non-null float64
    OCLC number                                0 non-null float64
    Date created                               899 non-null object
    Date modified                              899 non-null object
    dtypes: float64(55), int64(1), object(8)
    memory usage: 449.6+ KB



```python
df.Title.sort_values().head(12)  
```




    0    NaN
    1    NaN
    2    NaN
    3    NaN
    4    NaN
    5    NaN
    6    NaN
    7    NaN
    8    NaN
    9    NaN
    10   NaN
    11   NaN
    Name: Title, dtype: float64



###  Solution to Exercise 3: nameofexercise


```python

```

## Metadata Example 2: Compare a group of metadata files <a name="md2"></a>

This example continues where Example 1 left off. Having identified a set of fields to analyze in our group of collections, we will create new dataframes from the raw datasheets. This time we will include only the set of relevant columns from a group of collections. 

We will then concatenate the new dataframes into a single compiled dataset that makes it easy to compare completeness of metadata across the group as a whole. 

We will generate basic graphs to show comparisons between the collections. 



```python
# create a variable to store the column labels we want to select from each dataset

coltitles=['Title','Date','Usage Rights', 'Subject Geographic', 'Subject Name' , 'Subject Topical']
```


```python
# read in the same datasheets from the last example
# create a new column in each dataframe that contain a short Collection Name value

maps=pd.read_csv("./exampleData/maps.csv", usecols=coltitles)
maps['colname'] ='Civil War Maps'

rev=pd.read_csv("./exampleData/60001.txt", usecols=coltitles, sep='\t')
rev['colname'] ='Revolution Photographs'

rmb=pd.read_csv("./exampleData/03883.txt", sep='\t', usecols=coltitles)
rmb['colname'] ='Roy M Brown Papers'
```


```python
# show info for updated dataframes 

maps.sort_index(axis=1).info()
print('\n')

rev.sort_index(axis=1).info()
print('\n')

rmb.sort_index(axis=1).info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 161 entries, 0 to 160
    Data columns (total 7 columns):
    Date                  161 non-null object
    Subject Geographic    161 non-null object
    Subject Name          161 non-null object
    Subject Topical       161 non-null object
    Title                 161 non-null object
    Usage Rights          0 non-null float64
    colname               161 non-null object
    dtypes: float64(1), object(6)
    memory usage: 8.9+ KB
    
    
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 538 entries, 0 to 537
    Data columns (total 7 columns):
    Date                  538 non-null object
    Subject Geographic    538 non-null object
    Subject Name          15 non-null object
    Subject Topical       1 non-null object
    Title                 505 non-null object
    Usage Rights          538 non-null object
    colname               538 non-null object
    dtypes: object(7)
    memory usage: 29.5+ KB
    
    
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 899 entries, 0 to 898
    Data columns (total 7 columns):
    Date                  0 non-null float64
    Subject Geographic    0 non-null float64
    Subject Name          0 non-null float64
    Subject Topical       0 non-null float64
    Title                 0 non-null float64
    Usage Rights          899 non-null object
    colname               899 non-null object
    dtypes: float64(5), object(2)
    memory usage: 49.3+ KB



```python
# concatenate dataframes into a single dataframe

collstack = pd.concat([maps, rmb, rev], axis=0, sort=True)
```


```python
collstack.shape
```




    (1598, 7)




```python
collstack.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 1598 entries, 0 to 537
    Data columns (total 7 columns):
    Date                  699 non-null object
    Subject Geographic    699 non-null object
    Subject Name          176 non-null object
    Subject Topical       162 non-null object
    Title                 666 non-null object
    Usage Rights          1437 non-null object
    colname               1598 non-null object
    dtypes: object(7)
    memory usage: 99.9+ KB



```python
collstack.groupby('colname')['Title', 'Usage Rights'].count()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Usage Rights</th>
    </tr>
    <tr>
      <th>colname</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Civil War Maps</td>
      <td>161</td>
      <td>0</td>
    </tr>
    <tr>
      <td>Revolution Photographs</td>
      <td>505</td>
      <td>538</td>
    </tr>
    <tr>
      <td>Roy M Brown Papers</td>
      <td>0</td>
      <td>899</td>
    </tr>
  </tbody>
</table>
</div>




```python
collstack.groupby('colname')['Title', 'Usage Rights'].count().plot(kind='bar', figsize=(8,6),width=0.8, )
plt.ylabel('Count of items')
plt.xlabel('')
```




    Text(0.5, 0, '')




![png](output_77_1.png)



```python
collstack.groupby('colname')['Title', 'Subject Geographic', 'Subject Name', 'Subject Topical'].count()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Subject Geographic</th>
      <th>Subject Name</th>
      <th>Subject Topical</th>
    </tr>
    <tr>
      <th>colname</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Civil War Maps</td>
      <td>161</td>
      <td>161</td>
      <td>161</td>
      <td>161</td>
    </tr>
    <tr>
      <td>Revolution Photographs</td>
      <td>505</td>
      <td>538</td>
      <td>15</td>
      <td>1</td>
    </tr>
    <tr>
      <td>Roy M Brown Papers</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
collstack.groupby('colname')['Title', 'Subject Geographic', 'Subject Name', 'Subject Topical'].count().plot(kind='barh', figsize=(8,6), width=0.6)
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f0c1881e438>




![png](output_79_1.png)



```python
maps.groupby(['Subject Name']).Title.count().sort_values(ascending=False).plot(kind='barh')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f0c187938d0>




![png](output_80_1.png)



```python
maps.groupby(['Subject Name']).Title.count().sort_values(ascending=False).head().plot(kind='barh', figsize=(8,6))
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f0c1868ea90>




![png](output_81_1.png)



```python
maps.groupby(['Subject Name']).Title.count().sort_values(ascending=False).head().plot(kind='pie', figsize=(8,8),startangle=180)
plt.ylabel('')
#plt.title("Most Common Subject Names in Maps Collection")
```




    Text(0, 0.5, '')




![png](output_82_1.png)



```python
maps.groupby(['Subject Name']).Title.count().sort_values(ascending=False).head(10)
```




    Subject Name
    Gilmer, Jeremy Francis, 1818-1883.;                                                     104
    Blackford, B. L. (Benjamin Lewis); Gilmer, Jeremy Francis, 1818-1883.;                    9
    Gilmer, Jeremy Francis, 1818-1883.                                                        6
    Beauregard, G. T. (Gustave Toutant), 1818-1893.; Gilmer, Jeremy Francis, 1818-1883.;      4
    Fitz, Newton.; Gilmer, Jeremy Francis, 1818-1883.;                                        4
    Gilmer, Jeremy Francis, 1818-1883.; Turner, L. C.;                                        4
    Gilmer, Jeremy Francis, 1818-1883.; Turner, L. C.                                         3
    Gilmer, Jeremy Francis, 1818-1883.; Henderson, D. E.;                                     3
    Gilmer, Jeremy Francis, 1818-1883.; Liernur, Charles T.                                   2
    Gilmer, Jeremy Francis, 1818-1883.; Grant, John, Captain.;                                2
    Name: Title, dtype: int64




```python
# create a variable that specifies a range to examine
# exclude the most-common heading to focus on the next seven values

subcounts=maps['Subject Name'].value_counts()

totals=subcounts[(subcounts <= 103) & (subcounts>2)]

totals.sort_values(ascending=False).plot(kind='pie', figsize=(8,8),startangle=90)
plt.ylabel('')
```




    Text(0, 0.5, '')




![png](output_84_1.png)


### Recap of Example 2 

* select specific columns from multiple different datasets using a variable to store a list of fields
* concatenate multiple dataframes into a single dataframe
* use groupby to organize datasets for comparison
* create basic graphs to compare datasets
* explore different graph formats to represent data attributes


### Exercise 4: Evaluate Subjects data in a collection<a name="ex4"></a>


In this exercise, you will evaluate data in the 'Subject Topical' field in the Maps collection. 

Based on the output below from maps.info(), it looks like the Subject Topical field is fairly complete in this collection. 

```
maps.info()
```

```
RangeIndex: 161 entries, 0 to 160
Data columns (total 7 columns):
Title                 161 non-null object
Date                  161 non-null object
Subject Topical       161 non-null object
Subject Name          161 non-null object
Subject Geographic    161 non-null object
Usage Rights          0 non-null float64
colname               161 non-null object
```
Try using the describe() method to get more details about the values represented within the 'Subject Topical' field. 

Would plotting the maps titles according to 'Subject Topical' fields assigned to them make an interesting graph? 

To do this exercise, add code cells below this cell (or use the empty cells provided). Use those cells to check the output from describe() for the maps dataframe, and to generate a plot for numbers of maps titles grouped by Subject Topical. 

For reference, the solution is demonstrated in the next cells below. 



```python

```


```python

```

### Solution to Exercise 4: Evaluate Subjects data in a collection


```python
# use describe() to evaluate the contents of the 'Subject Topical' field

maps['Subject Topical'].describe()
```




    count                                                161
    unique                                                 1
    top       United States--History--Civil War, 1861-1865.;
    freq                                                 161
    Name: Subject Topical, dtype: object



The output from 'describe()' shows that although every item in this collection has a Subject Topical field, it is all the same value, which does not make a very interesting plot. 


```python
# generate a plot for the distribution of Subject Topical field across titles

maps.groupby(['Subject Topical']).Title.count().plot(kind='barh',color=['grey'])
plt.xlabel('item count')
```




    Text(0.5, 0, 'item count')




![png](output_92_1.png)



```python

```

## Metadata Example 3: Merge information from separate files <a name="md3"></a>

Another useful feature of pandas is that it allows you to do SQL-like joins with plain text files.  

In this exercise, we will create a merged dataframe from descriptive metadata and file sizes information in separate datasets. We will rename columns in the descriptive metadata dataframe to merge based on columns in our filesizes datasheets. (It's also possible to specify the columns to merge separately for the left and right dataframes if they are not named the same!)  

**Learning objectives for this example:**
* Review removing empty columns - the first dataset has a large number of columns, some of which have no data
* Datatypes can be complicated and lead to potential errors; you may need to specify datatypes for columns
* Renaming columns 
* Merging dataframes 
* Write a dataframe to a csv output file or other format 



markdown


```python
# uncomment the import statement below and run this cell if your notebook was reset and you need the libraries again

#import pandas as pd
```


```python
# read in collections metadata file as 'metadata' dataframe
metadata=pd.read_csv("./exampleData/03823_metadata.txt", sep='\t')
```

markdown



```python
# use pandas attributes and methods to examine the new dataframe. 
# Start with the shape attribute to summarize rows and columns.

print(metadata.shape)
```

    (5777, 60)


markdown


```python
# use the info method to see column names and item counts in each column

metadata.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 5777 entries, 0 to 5776
    Data columns (total 60 columns):
    Collection in Repository                   5777 non-null object
    Collection Number                          5777 non-null int64
    Location in Collection                     5777 non-null object
    Object                                     5777 non-null object
    Container Type                             5777 non-null object
    filename                                   5777 non-null object
    Title                                      0 non-null float64
    Alternative Title                          0 non-null float64
    Creator                                    0 non-null float64
    Contributor                                0 non-null float64
    Creation Date                              0 non-null float64
    Date                                       0 non-null float64
    Description                                0 non-null float64
    Subject (tgm)                              0 non-null float64
    Subject - Name                             0 non-null float64
    Subject - Topical                          0 non-null float64
    Subject - Geographic                       0 non-null float64
    Subject Topical Other                      0 non-null float64
    Coordinates                                0 non-null float64
    geonamesid                                 0 non-null float64
    Digital Collection                         0 non-null float64
    Repository                                 0 non-null float64
    Host                                       0 non-null float64
    Usage Rights                               5777 non-null object
    Copyright Holder                           0 non-null float64
    Additional Display                         0 non-null float64
    Transcription                              0 non-null float64
    Caption                                    0 non-null float64
    Notes                                      0 non-null float64
    Title Note                                 0 non-null float64
    Contributor Note                           0 non-null float64
    Sponsor                                    0 non-null float64
    Related Resource                           0 non-null float64
    Author Chief Source                        0 non-null float64
    Publisher                                  0 non-null float64
    Place of Publication                       0 non-null float64
    Cataloging Agency                          0 non-null float64
    Is Part Of                                 0 non-null float64
    Has Part Of                                0 non-null float64
    Form                                       0 non-null float64
    Resource Type                              0 non-null float64
    Medium                                     0 non-null float64
    Condition                                  0 non-null float64
    Language                                   0 non-null float64
    Physical Description of Analog Original    0 non-null float64
    Creator Nationality/Culture                0 non-null float64
    Style/Period                               0 non-null float64
    Volume/Issue                               0 non-null float64
    Scale                                      0 non-null float64
    Projection                                 0 non-null float64
    Map Type                                   0 non-null float64
    Map Details                                0 non-null float64
    Current Location                           0 non-null float64
    path                                       0 non-null float64
    Local Identifier                           0 non-null float64
    Creator Identifier                         0 non-null float64
    Date created                               5777 non-null object
    Date modified                              5777 non-null object
    Object number                              5777 non-null int64
    Object file name                           5777 non-null object
    dtypes: float64(49), int64(2), object(9)
    memory usage: 2.6+ MB


markdown



```python
#Remove the empty columns using dropna
# and re-check the column names and item counts by re-running the info method on the reshaped dataset.

metadata.dropna(axis = 1, how ='all', inplace = True)

metadata.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 5777 entries, 0 to 5776
    Data columns (total 11 columns):
    Collection in Repository    5777 non-null object
    Collection Number           5777 non-null int64
    Location in Collection      5777 non-null object
    Object                      5777 non-null object
    Container Type              5777 non-null object
    filename                    5777 non-null object
    Usage Rights                5777 non-null object
    Date created                5777 non-null object
    Date modified               5777 non-null object
    Object number               5777 non-null int64
    Object file name            5777 non-null object
    dtypes: int64(2), object(9)
    memory usage: 496.6+ KB


markdown



```python
metadata['Collection Number'].head(8)
```




    0    3823
    1    3823
    2    3823
    3    3823
    4    3823
    5    3823
    6    3823
    7    3823
    Name: Collection Number, dtype: int64




```python
metadata=pd.read_csv("./exampleData/03823_metadata.txt", sep='\t', dtype={'Collection Number':object})

metadata['Collection Number'].head(8)
```




    0    03823
    1    03823
    2    03823
    3    03823
    4    03823
    5    03823
    6    03823
    7    03823
    Name: Collection Number, dtype: object




```python
#Remove the empty columns using dropna

metadata.dropna(axis = 1, how ='all', inplace = True)
```

markdown



```python
#Use the head method to see the first n rows

metadata.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Collection in Repository</th>
      <th>Collection Number</th>
      <th>Location in Collection</th>
      <th>Object</th>
      <th>Container Type</th>
      <th>filename</th>
      <th>Usage Rights</th>
      <th>Date created</th>
      <th>Date modified</th>
      <th>Object number</th>
      <th>Object file name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 20: Correspondence, 1947-1948: Scan 9</td>
      <td>folder</td>
      <td>03823_0020_0009.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>0</td>
      <td>231.jp2</td>
    </tr>
    <tr>
      <td>1</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 21: Correspondence, 1947-1948: Scan 17</td>
      <td>folder</td>
      <td>03823_0021_0017.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>1</td>
      <td>430.jp2</td>
    </tr>
    <tr>
      <td>2</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 9: Correspondence, 1943: Scan 1</td>
      <td>folder</td>
      <td>03823_0009_0001.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>2</td>
      <td>909.jp2</td>
    </tr>
    <tr>
      <td>3</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 17: Correspondence, 1947-1948: Scan 16</td>
      <td>folder</td>
      <td>03823_0017_0016.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>3</td>
      <td>59.jp2</td>
    </tr>
    <tr>
      <td>4</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 12: Correspondence, 1944-May 1946: Scan 44</td>
      <td>folder</td>
      <td>03823_0012_0044.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>4</td>
      <td>152.jp2</td>
    </tr>
  </tbody>
</table>
</div>



markdown


```python
#Create the second dataframe with the filelist datasheet

sizelist=pd.read_csv("./exampleData/03823_access_images.csv")
```


```python
sizelist.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 11554 entries, 0 to 11553
    Data columns (total 6 columns):
    Name                    11554 non-null object
    Full Path               11554 non-null object
    Size                    11554 non-null object
    Files                   11554 non-null int64
    Dir Level (Relative)    11554 non-null int64
    Extension               11554 non-null object
    dtypes: int64(2), object(4)
    memory usage: 541.7+ KB



```python
#Create the second dataframe with the filelist datasheet

sizelist=pd.read_csv("./exampleData/03823_access_images.csv", usecols=['Name','Full Path', 'Size'])

sizelist.rename(columns={'Name':'AccessName', 'Full Path':'AccessFilePath', 'Size' : 'AccessFileSize'}, inplace=True)
```

markdown


```python
# Use shape and info to take a look at the sizelist dataframe.
print(sizelist.shape) 

sizelist.info()
```

    (11554, 3)
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 11554 entries, 0 to 11553
    Data columns (total 3 columns):
    AccessName        11554 non-null object
    AccessFilePath    11554 non-null object
    AccessFileSize    11554 non-null object
    dtypes: object(3)
    memory usage: 270.9+ KB


markdown


```python
#Use the head method to see the first n rows of a column

sizelist.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AccessName</th>
      <th>AccessFilePath</th>
      <th>AccessFileSize</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1.jp2</td>
      <td>Content/03823/image/1.jp2</td>
      <td>7207888 Bytes</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2.jp2</td>
      <td>Content/03823/image/2.jp2</td>
      <td>5707680 Bytes</td>
    </tr>
    <tr>
      <td>2</td>
      <td>3.jp2</td>
      <td>Content/03823/image/3.jp2</td>
      <td>1364563 Bytes</td>
    </tr>
    <tr>
      <td>3</td>
      <td>4.jp2</td>
      <td>Content/03823/image/4.jp2</td>
      <td>9339767 Bytes</td>
    </tr>
    <tr>
      <td>4</td>
      <td>5.jp2</td>
      <td>Content/03823/image/5.jp2</td>
      <td>9021190 Bytes</td>
    </tr>
  </tbody>
</table>
</div>



markdown

markdown


```python
# Rename a column 

metadata.rename(columns={'Object file name':'AccessName'}, inplace=True)
metadata.columns
```




    Index(['Collection in Repository', 'Collection Number',
           'Location in Collection', 'Object', 'Container Type', 'filename',
           'Usage Rights', 'Date created', 'Date modified', 'Object number',
           'AccessName'],
          dtype='object')



markdown


```python
# Join sizelist data onto the metadata dataframe
# and view info for the new, merged dataframe

combined = pd.merge(metadata, sizelist,on='AccessName', how='left')

combined.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 5777 entries, 0 to 5776
    Data columns (total 13 columns):
    Collection in Repository    5777 non-null object
    Collection Number           5777 non-null object
    Location in Collection      5777 non-null object
    Object                      5777 non-null object
    Container Type              5777 non-null object
    filename                    5777 non-null object
    Usage Rights                5777 non-null object
    Date created                5777 non-null object
    Date modified               5777 non-null object
    Object number               5777 non-null int64
    AccessName                  5777 non-null object
    AccessFilePath              5777 non-null object
    AccessFileSize              5777 non-null object
    dtypes: int64(1), object(12)
    memory usage: 631.9+ KB



```python
combined.AccessFileSize.head(8)

```




    0     8524803 Bytes
    1    10099338 Bytes
    2     5920711 Bytes
    3     5291542 Bytes
    4     1746399 Bytes
    5     7633196 Bytes
    6     4772963 Bytes
    7    10301523 Bytes
    Name: AccessFileSize, dtype: object




```python
combined['AccessSizeNum'] = combined.AccessFileSize.apply(lambda x: x.replace(' Bytes',''))

combined=combined.astype({'AccessSizeNum':'int64'})

combined.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 5777 entries, 0 to 5776
    Data columns (total 14 columns):
    Collection in Repository    5777 non-null object
    Collection Number           5777 non-null object
    Location in Collection      5777 non-null object
    Object                      5777 non-null object
    Container Type              5777 non-null object
    filename                    5777 non-null object
    Usage Rights                5777 non-null object
    Date created                5777 non-null object
    Date modified               5777 non-null object
    Object number               5777 non-null int64
    AccessName                  5777 non-null object
    AccessFilePath              5777 non-null object
    AccessFileSize              5777 non-null object
    AccessSizeNum               5777 non-null int64
    dtypes: int64(2), object(12)
    memory usage: 677.0+ KB



```python

```

markdown


```python
# Write the merged dataframe to a new csv

combined.to_csv('./output/accessfilesizes_metadata_03823.csv', index=False,encoding='utf-8-sig')
```

markdown


```python
#Create a third dataframe with the masters files datasheet

masters=pd.read_csv("./exampleData/03823_masters.csv", usecols=['Name','Full Path', 'Size'])

masters.rename(columns={'Name':'MastersName', 'Full Path':'MasterFilePath', 'Size' : 'MasterFileSize'}, inplace=True)

masters['MasterSizeNum'] = masters.MasterFileSize.apply(lambda x: x.replace(' Bytes',''))

masters=masters.astype({'MasterSizeNum':'int64'})
```


```python
masters.info()

```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 6044 entries, 0 to 6043
    Data columns (total 4 columns):
    MastersName       6044 non-null object
    MasterFilePath    6044 non-null object
    MasterFileSize    6044 non-null object
    MasterSizeNum     6044 non-null int64
    dtypes: int64(1), object(3)
    memory usage: 189.0+ KB



```python
masters.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MastersName</th>
      <th>MasterFilePath</th>
      <th>MasterFileSize</th>
      <th>MasterSizeNum</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>6039</td>
      <td>03823_0046_0005.tif</td>
      <td>bucket\03823_nccic\03823_0046\03823_0046_0005.tif</td>
      <td>10136638 Bytes</td>
      <td>10136638</td>
    </tr>
    <tr>
      <td>6040</td>
      <td>03823_0046_0006.tif</td>
      <td>bucket\03823_nccic\03823_0046\03823_0046_0006.tif</td>
      <td>9620175 Bytes</td>
      <td>9620175</td>
    </tr>
    <tr>
      <td>6041</td>
      <td>03823_0046_0007.tif</td>
      <td>bucket\03823_nccic\03823_0046\03823_0046_0007.tif</td>
      <td>9280681 Bytes</td>
      <td>9280681</td>
    </tr>
    <tr>
      <td>6042</td>
      <td>03823_0046_0008.tif</td>
      <td>bucket\03823_nccic\03823_0046\03823_0046_0008.tif</td>
      <td>8937930 Bytes</td>
      <td>8937930</td>
    </tr>
    <tr>
      <td>6043</td>
      <td>03823_0046_0009.tif</td>
      <td>bucket\03823_nccic\03823_0046\03823_0046_0009.tif</td>
      <td>8409261 Bytes</td>
      <td>8409261</td>
    </tr>
  </tbody>
</table>
</div>




```python
combined.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Collection in Repository</th>
      <th>Collection Number</th>
      <th>Location in Collection</th>
      <th>Object</th>
      <th>Container Type</th>
      <th>filename</th>
      <th>Usage Rights</th>
      <th>Date created</th>
      <th>Date modified</th>
      <th>Object number</th>
      <th>AccessName</th>
      <th>AccessFilePath</th>
      <th>AccessFileSize</th>
      <th>AccessSizeNum</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 20: Correspondence, 1947-1948: Scan 9</td>
      <td>folder</td>
      <td>03823_0020_0009.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>0</td>
      <td>231.jp2</td>
      <td>Content/03823/image/231.jp2</td>
      <td>8524803 Bytes</td>
      <td>8524803</td>
    </tr>
    <tr>
      <td>1</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 21: Correspondence, 1947-1948: Scan 17</td>
      <td>folder</td>
      <td>03823_0021_0017.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>1</td>
      <td>430.jp2</td>
      <td>Content/03823/image/430.jp2</td>
      <td>10099338 Bytes</td>
      <td>10099338</td>
    </tr>
    <tr>
      <td>2</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 9: Correspondence, 1943: Scan 1</td>
      <td>folder</td>
      <td>03823_0009_0001.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>2</td>
      <td>909.jp2</td>
      <td>Content/03823/image/909.jp2</td>
      <td>5920711 Bytes</td>
      <td>5920711</td>
    </tr>
    <tr>
      <td>3</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 17: Correspondence, 1947-1948: Scan 16</td>
      <td>folder</td>
      <td>03823_0017_0016.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>3</td>
      <td>59.jp2</td>
      <td>Content/03823/image/59.jp2</td>
      <td>5291542 Bytes</td>
      <td>5291542</td>
    </tr>
    <tr>
      <td>4</td>
      <td>North Carolina Commission on Interracial Coope...</td>
      <td>03823</td>
      <td>Series 1. Correspondence, 1922-1949. / Subseri...</td>
      <td>Folder 12: Correspondence, 1944-May 1946: Scan 44</td>
      <td>folder</td>
      <td>03823_0012_0044.tif</td>
      <td>For copyright information or permissions quest...</td>
      <td>2012-01-26</td>
      <td>2012-01-26</td>
      <td>4</td>
      <td>152.jp2</td>
      <td>Content/03823/image/152.jp2</td>
      <td>1746399 Bytes</td>
      <td>1746399</td>
    </tr>
  </tbody>
</table>
</div>




```python
combined.rename(columns={'filename':'MastersName'}, inplace=True)

combined.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 5777 entries, 0 to 5776
    Data columns (total 14 columns):
    Collection in Repository    5777 non-null object
    Collection Number           5777 non-null object
    Location in Collection      5777 non-null object
    Object                      5777 non-null object
    Container Type              5777 non-null object
    MastersName                 5777 non-null object
    Usage Rights                5777 non-null object
    Date created                5777 non-null object
    Date modified               5777 non-null object
    Object number               5777 non-null int64
    AccessName                  5777 non-null object
    AccessFilePath              5777 non-null object
    AccessFileSize              5777 non-null object
    AccessSizeNum               5777 non-null int64
    dtypes: int64(2), object(12)
    memory usage: 677.0+ KB



```python
all3 = pd.merge(combined, masters,on='MastersName', how='left')

all3.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 5777 entries, 0 to 5776
    Data columns (total 17 columns):
    Collection in Repository    5777 non-null object
    Collection Number           5777 non-null object
    Location in Collection      5777 non-null object
    Object                      5777 non-null object
    Container Type              5777 non-null object
    MastersName                 5777 non-null object
    Usage Rights                5777 non-null object
    Date created                5777 non-null object
    Date modified               5777 non-null object
    Object number               5777 non-null int64
    AccessName                  5777 non-null object
    AccessFilePath              5777 non-null object
    AccessFileSize              5777 non-null object
    AccessSizeNum               5777 non-null int64
    MasterFilePath              5777 non-null object
    MasterFileSize              5777 non-null object
    MasterSizeNum               5777 non-null int64
    dtypes: int64(3), object(14)
    memory usage: 812.4+ KB



```python
all3.loc[:,['Collection Number','Object', 'MastersName', 'AccessName', 'AccessSizeNum','MasterSizeNum']].head(12)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Collection Number</th>
      <th>Object</th>
      <th>MastersName</th>
      <th>AccessName</th>
      <th>AccessSizeNum</th>
      <th>MasterSizeNum</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>03823</td>
      <td>Folder 20: Correspondence, 1947-1948: Scan 9</td>
      <td>03823_0020_0009.tif</td>
      <td>231.jp2</td>
      <td>8524803</td>
      <td>23654901</td>
    </tr>
    <tr>
      <td>1</td>
      <td>03823</td>
      <td>Folder 21: Correspondence, 1947-1948: Scan 17</td>
      <td>03823_0021_0017.tif</td>
      <td>430.jp2</td>
      <td>10099338</td>
      <td>20547567</td>
    </tr>
    <tr>
      <td>2</td>
      <td>03823</td>
      <td>Folder 9: Correspondence, 1943: Scan 1</td>
      <td>03823_0009_0001.tif</td>
      <td>909.jp2</td>
      <td>5920711</td>
      <td>20210038</td>
    </tr>
    <tr>
      <td>3</td>
      <td>03823</td>
      <td>Folder 17: Correspondence, 1947-1948: Scan 16</td>
      <td>03823_0017_0016.tif</td>
      <td>59.jp2</td>
      <td>5291542</td>
      <td>19359544</td>
    </tr>
    <tr>
      <td>4</td>
      <td>03823</td>
      <td>Folder 12: Correspondence, 1944-May 1946: Scan 44</td>
      <td>03823_0012_0044.tif</td>
      <td>152.jp2</td>
      <td>1746399</td>
      <td>4526254</td>
    </tr>
    <tr>
      <td>5</td>
      <td>03823</td>
      <td>Folder 16: Correspondence, 1947-1948: Scan 15</td>
      <td>03823_0016_0015.tif</td>
      <td>360.jp2</td>
      <td>7633196</td>
      <td>22851671</td>
    </tr>
    <tr>
      <td>6</td>
      <td>03823</td>
      <td>Folder 9: Correspondence, 1943: Scan 15</td>
      <td>03823_0009_0015.tif</td>
      <td>503.jp2</td>
      <td>4772963</td>
      <td>18935044</td>
    </tr>
    <tr>
      <td>7</td>
      <td>03823</td>
      <td>Folder 19: Correspondence, 1947-1948: Scan 12</td>
      <td>03823_0019_0012.tif</td>
      <td>222.jp2</td>
      <td>10301523</td>
      <td>25278344</td>
    </tr>
    <tr>
      <td>8</td>
      <td>03823</td>
      <td>Folder 13: Correspondence, August-December 194...</td>
      <td>03823_0013_0006.tif</td>
      <td>408.jp2</td>
      <td>4544632</td>
      <td>18302170</td>
    </tr>
    <tr>
      <td>9</td>
      <td>03823</td>
      <td>Folder 7: Correspondence, 1942: Scan 34</td>
      <td>03823_0007_0034.tif</td>
      <td>411.jp2</td>
      <td>5646702</td>
      <td>19838143</td>
    </tr>
    <tr>
      <td>10</td>
      <td>03823</td>
      <td>Folder 7: Correspondence, 1942: Scan 32</td>
      <td>03823_0007_0032.tif</td>
      <td>543.jp2</td>
      <td>6539003</td>
      <td>20964250</td>
    </tr>
    <tr>
      <td>11</td>
      <td>03823</td>
      <td>Folder 18: Correspondence, 1947-1948: Scan 37</td>
      <td>03823_0018_0037.tif</td>
      <td>49.jp2</td>
      <td>4533313</td>
      <td>18280062</td>
    </tr>
  </tbody>
</table>
</div>



###  Exercise 5: Other ways to merge <a name="ex5"></a>


```python

```


```python
# Use the tail method to see the last n rows of a column
sizelist.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AccessName</th>
      <th>AccessFilePath</th>
      <th>AccessFileSize</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>11549</td>
      <td>icon5773.jpg</td>
      <td>Content/03823/image/icon5773.jpg</td>
      <td>2217 Bytes</td>
    </tr>
    <tr>
      <td>11550</td>
      <td>icon5774.jpg</td>
      <td>Content/03823/image/icon5774.jpg</td>
      <td>2706 Bytes</td>
    </tr>
    <tr>
      <td>11551</td>
      <td>icon5775.jpg</td>
      <td>Content/03823/image/icon5775.jpg</td>
      <td>2648 Bytes</td>
    </tr>
    <tr>
      <td>11552</td>
      <td>icon5776.jpg</td>
      <td>Content/03823/image/icon5776.jpg</td>
      <td>2895 Bytes</td>
    </tr>
    <tr>
      <td>11553</td>
      <td>icon5777.jpg</td>
      <td>Content/03823/image/icon5777.jpg</td>
      <td>3057 Bytes</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Use python string method to count instances of 'icon'

sizelist['AccessName'].str.count("icon").sum()
```




    5777




```python

```

###  Solution to Exercise 5: Other ways to merge


```python

```


```python

```

## Bonus Metadata Example: Find and remove duplicates <a name="md4"></a>




markdown


```python
coll=pd.read_csv('./exampleData/coll_dupes_example.csv')
```

markdown


```python
coll.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 39156 entries, 0 to 39155
    Data columns (total 17 columns):
    Collection Number         33851 non-null object
    Location in Collection    33837 non-null object
    Object                    39156 non-null object
    Container type            33845 non-null object
    filename                  33764 non-null object
    Alternative Title         0 non-null float64
    Creator                   1042 non-null object
    Contributor               0 non-null float64
    Creation Date             0 non-null float64
    Date                      7217 non-null object
    Description               319 non-null object
    Subject Name              20 non-null object
    Subject Geographic        8198 non-null object
    Subject Topical Other     200 non-null object
    Resource Type             6333 non-null object
    Date created              39156 non-null object
    Date modified             39156 non-null object
    dtypes: float64(3), object(14)
    memory usage: 5.1+ MB



```python
coll=pd.read_csv('./exampleData/coll_dupes_example.csv', usecols=['Collection Number','Object', 'filename', 'Date created', 'Date modified'])
```

markdown


```python
coll.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 39156 entries, 0 to 39155
    Data columns (total 5 columns):
    Collection Number    33851 non-null object
    Object               39156 non-null object
    filename             33764 non-null object
    Date created         39156 non-null object
    Date modified        39156 non-null object
    dtypes: object(5)
    memory usage: 1.5+ MB



```python

```


```python
coll.shape
```




    (39156, 5)




```python
coll.Object.duplicated().sum()
```




    31




```python
# remove duplicates with drop_duplicates method

deduped= coll.drop_duplicates(subset= 'Object', keep='first')
```


```python
deduped.shape

```




    (39125, 5)




```python
31+39125
```




    39156




```python
dupes_all=coll.loc[coll.Object.duplicated(keep=False), :]
```


```python

dupes_all.shape

```




    (40, 5)




```python
dupes_all.sort_values(['Collection Number','Object'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Collection Number</th>
      <th>Object</th>
      <th>filename</th>
      <th>Date created</th>
      <th>Date modified</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>29280</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0098: Steam engine 4501, Mi...</td>
      <td>P0032_2_0098_0001.tif</td>
      <td>2011-02-08</td>
      <td>2011-04-19</td>
    </tr>
    <tr>
      <td>29281</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0098: Steam engine 4501, Mi...</td>
      <td>P0032_2_0098_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29303</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0123: Mikado type steam eng...</td>
      <td>P0032_2_0123_0001.tif</td>
      <td>2011-02-08</td>
      <td>2011-04-19</td>
    </tr>
    <tr>
      <td>29304</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0123: Mikado type steam eng...</td>
      <td>P0032_2_0123_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29315</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0134: Green and gold-trimme...</td>
      <td>P0032_2_0134_0001.tif</td>
      <td>2011-02-08</td>
      <td>2011-04-19</td>
    </tr>
    <tr>
      <td>29316</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0134: Green and gold-trimme...</td>
      <td>P0032_2_0134_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29385</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0207_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29386</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0213_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29387</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0218_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29388</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0223_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29389</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0217_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29390</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0225_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29391</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0229_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29392</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0219_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29393</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0227_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29394</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0210_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29395</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0221_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29396</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0224_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29397</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0226_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29398</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0216_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29399</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0211_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29400</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0212_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29401</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0230_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29402</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0222_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29403</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0215_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29404</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0214_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29405</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0220_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29406</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0209_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29407</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0208_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29408</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0228_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29990</td>
      <td>P0044</td>
      <td>Folder 0044: A Connoisseur (Unidentified man),...</td>
      <td>P0044_0044_0001.tif</td>
      <td>2014-07-14</td>
      <td>2014-07-14</td>
    </tr>
    <tr>
      <td>29991</td>
      <td>P0044</td>
      <td>Folder 0044: A Connoisseur (Unidentified man),...</td>
      <td>P0044_0044_0001.tif</td>
      <td>2016-03-08</td>
      <td>2016-03-08</td>
    </tr>
    <tr>
      <td>29992</td>
      <td>P0044</td>
      <td>Folder 0044: A Connoisseur (Unidentified man),...</td>
      <td>P0044_0044_0002.tif</td>
      <td>2014-07-14</td>
      <td>2014-07-14</td>
    </tr>
    <tr>
      <td>29993</td>
      <td>P0044</td>
      <td>Folder 0044: A Connoisseur (Unidentified man),...</td>
      <td>P0044_0044_0002.tif</td>
      <td>2016-03-08</td>
      <td>2016-03-08</td>
    </tr>
    <tr>
      <td>30050</td>
      <td>P0044</td>
      <td>Folder 0088: Innocence (Unidentified girl), 1906</td>
      <td>P0044_0088_0001.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>30051</td>
      <td>P0044</td>
      <td>Folder 0088: Innocence (Unidentified girl), 1906</td>
      <td>P0044_0088_0002.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>30139</td>
      <td>P0044</td>
      <td>Folder 0151: Virginia</td>
      <td>P0044_0151_A.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>30140</td>
      <td>P0044</td>
      <td>Folder 0151: Virginia</td>
      <td>P0044_0151_B.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>30340</td>
      <td>P0044</td>
      <td>Folder 0259: Return of the Sheep, circa 1899</td>
      <td>P0044_0259_Large.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>30341</td>
      <td>P0044</td>
      <td>Folder 0259: Return of the Sheep, circa 1899</td>
      <td>P0044_0259_Small.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
  </tbody>
</table>
</div>




```python
# write duplicates dataframe to a csv, sorted by Collection number then by Object field

dupes_all.sort_values(['Collection Number','Object']).to_csv('./output/coll_dupes_all_sorted.csv', index=False, encoding='utf-8')
```


```python
# can look at new datasheet as a dataframe, or open it in an external spreadsheet program

da=pd.read_csv('./output/coll_dupes_all_sorted.csv')
```


```python
da
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Collection Number</th>
      <th>Object</th>
      <th>filename</th>
      <th>Date created</th>
      <th>Date modified</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0098: Steam engine 4501, Mi...</td>
      <td>P0032_2_0098_0001.tif</td>
      <td>2011-02-08</td>
      <td>2011-04-19</td>
    </tr>
    <tr>
      <td>1</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0098: Steam engine 4501, Mi...</td>
      <td>P0032_2_0098_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>2</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0123: Mikado type steam eng...</td>
      <td>P0032_2_0123_0001.tif</td>
      <td>2011-02-08</td>
      <td>2011-04-19</td>
    </tr>
    <tr>
      <td>3</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0123: Mikado type steam eng...</td>
      <td>P0032_2_0123_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>4</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0134: Green and gold-trimme...</td>
      <td>P0032_2_0134_0001.tif</td>
      <td>2011-02-08</td>
      <td>2011-04-19</td>
    </tr>
    <tr>
      <td>5</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0134: Green and gold-trimme...</td>
      <td>P0032_2_0134_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>6</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0207_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>7</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0213_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>8</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0218_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>9</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0223_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>10</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0217_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>11</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0225_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>12</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0229_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>13</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0219_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>14</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0227_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>15</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0210_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>16</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0221_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>17</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0224_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>18</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0226_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>19</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0216_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>20</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0211_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>21</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0212_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>22</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0230_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>23</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0222_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>24</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0215_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>25</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0214_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>26</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0220_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>27</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0209_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>28</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0208_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>29</td>
      <td>P0032</td>
      <td>Color 35mm Slide 2_0207: A collection of pictu...</td>
      <td>P0032_2_0228_0001.tif</td>
      <td>2011-05-12</td>
      <td>2011-05-12</td>
    </tr>
    <tr>
      <td>30</td>
      <td>P0044</td>
      <td>Folder 0044: A Connoisseur (Unidentified man),...</td>
      <td>P0044_0044_0001.tif</td>
      <td>2014-07-14</td>
      <td>2014-07-14</td>
    </tr>
    <tr>
      <td>31</td>
      <td>P0044</td>
      <td>Folder 0044: A Connoisseur (Unidentified man),...</td>
      <td>P0044_0044_0001.tif</td>
      <td>2016-03-08</td>
      <td>2016-03-08</td>
    </tr>
    <tr>
      <td>32</td>
      <td>P0044</td>
      <td>Folder 0044: A Connoisseur (Unidentified man),...</td>
      <td>P0044_0044_0002.tif</td>
      <td>2014-07-14</td>
      <td>2014-07-14</td>
    </tr>
    <tr>
      <td>33</td>
      <td>P0044</td>
      <td>Folder 0044: A Connoisseur (Unidentified man),...</td>
      <td>P0044_0044_0002.tif</td>
      <td>2016-03-08</td>
      <td>2016-03-08</td>
    </tr>
    <tr>
      <td>34</td>
      <td>P0044</td>
      <td>Folder 0088: Innocence (Unidentified girl), 1906</td>
      <td>P0044_0088_0001.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>35</td>
      <td>P0044</td>
      <td>Folder 0088: Innocence (Unidentified girl), 1906</td>
      <td>P0044_0088_0002.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>36</td>
      <td>P0044</td>
      <td>Folder 0151: Virginia</td>
      <td>P0044_0151_A.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>37</td>
      <td>P0044</td>
      <td>Folder 0151: Virginia</td>
      <td>P0044_0151_B.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>38</td>
      <td>P0044</td>
      <td>Folder 0259: Return of the Sheep, circa 1899</td>
      <td>P0044_0259_Large.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
    <tr>
      <td>39</td>
      <td>P0044</td>
      <td>Folder 0259: Return of the Sheep, circa 1899</td>
      <td>P0044_0259_Small.tif</td>
      <td>2013-03-28</td>
      <td>2013-03-28</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python

```


```python

```


```python

```

markdown

## Resources <a name="res"></a>






