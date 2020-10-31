# Jocelyn Morrison's Portfolio

Hello World! Welcome to my professional coding portfolio.

Any Questions? Please email me at [jc208691@dal.ca](mailto:jc208691@dal.ca)

## Reading in Data
Below is how I read in raw data from an experimental study to clean up and use for data analysis.
First using the glob function I created a list called "files" containing each file starting with 'spid' and ending with 'data.txt'.

files = glob ('spid*/*_data.txt')

This is how I would create a list called where each index of the list was an individual dataframe for each subject in the study, using the list comphrension technique.

dataframes = [pd.read_csv(x, sep='\t') for x in files]

## Cleaning multiple DataFrames using a For Loop
Below is a for loop that was used in a group project I was a part of to iterate our cleaning code over each dataframe corresponding to each participant.

