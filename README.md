# Jocelyn Morrison's Portfolio

Hello World! Welcome to my professional coding portfolio.

Any Questions? Please email me at [jc208691@dal.ca](mailto:jc208691@dal.ca)

## Reading in Data
Below is how I read in raw data from an experimental study to clean up and use for data analysis.
First using the glob function I created a list called "files" containing each file starting with 'spid' and ending with 'data.txt'.

files = glob ('spid*/*_data.txt')

This is how I would create a list where each index of the list was an individual dataframe for each subject in the study, using the list comphrension technique.

dataframes = [pd.read_csv(x, sep='\t') for x in files]

## Cleaning multiple DataFrames using a For Loop
Here is an example of code using a for loop to [iterate our cleaning code over a list of dataframes](Portfolio_Cleaning_Loop.md).

## Slicing Columns in a DataFrame
Here is an example of some code I wrote demonstrating how to read in a CSV file, create a DataFrame, and [slice the dataframe for certain columns using the groupby function](Portfolio_groupby.md).

## Data Visualization
Here is an example of [some code I wrote to generate a histogram using matplotlib.pyplot](Portfolio_data_visualization.md).

## Demo on Creating a Notebook on CoCalc
Below is an exerpt of a demo I created on using CoCalc to create your own Data Science class notebook.

How to create an Interactive Notebook for NESC 3505 using CoCalc!

As I worked through the first DataCamp lesson, I found learning the coding concepts by doing them was a great method, however if I moved on to the next part of the module, I often forgot the syntax of a given command that I used previously. 

I know I am the type of learner who really benefits from having worked out example problems to look back on to remember how I used certain skill, whether it was math or chemistry. Now I believe the same strategy will serve me well while learning Python. 

Upon completing Assignment 1 and familiarizing myself with using Markdown in a Jupyter Notebook on CoCalc, I realized this is a perfect space to create a notebook for this class. Using Markdown, you can write your basic notes that you normally would, and then you can follow it up with some code to complement your written notes!

Tutorial:

Step 1: Create a new file on CoCalc for your notebook. Do this by clicking “New” in the top left corner. 

Step 2: Name your file and select Jupyter notebook. 

Step 3: Select the Kernel Python 3 (system wide) 

Step 4: Start your Notebook with a Heading by changing the cell type from “Code” to “Markdown”  

Step 5: Begin typing in your cell. To execute the Markdown command, press Shift + Enter on your Keyboard. Then the Markdown cells will appear in a clean, easy to read text. To create a heading for your Notebook, add “#” before your Markdown text.

Step 6: New cells should appear when you execute the one previous to it. If not, click “Insert” > “Insert Cell Below” in the top left corner to insert a cell below your Markdown cell to add some code to go with your text.

Here is an excerpt from the above photo where I created examples on how the indexing works with lists when you are trying to select certain elements from it: 

List Slicing 

List slicing is a way to only print some items in the list. You do this using by specifying the range. The first item in the list ("hello") is index 0, the second item ("how") is index 1, and so on. To print "how are you" slice you code; list[1:4]. The syntax is list[start:end] where the start is inclusive and the end is exclusive (item 4 will not be in the slice)." 

In[10]: print(list) 

Out[10]: ['hello', 'how', 'are', 'you', 'this', 'fine', 'day'] 

In[11]: list[1:4] 

Out[11]: ['how', 'are', 'you'] 

As you can probably appreciate, a Jupyter notebook on CoCalc is a great way to store some examples of what you have learned to code. This is a great resource to look back on what you have learned. I hope you found this Demo helpful!

