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
processed_dataframes = []
fast_list = []
slow_list = []
for file in files:
    stats_dict = {}
    unprocessed_dataframe = pd.read_csv(file, sep='\t')
    # Drop null values
    unprocessed_dataframe = unprocessed_dataframe.dropna()
    # Removing duplicates
    unprocessed_dataframe = unprocessed_dataframe.drop_duplicates(subset=['rt'])
    # Removing practice trials
    unprocessed_dataframe = unprocessed_dataframe[unprocessed_dataframe.block != 'practice']
    std_rt = unprocessed_dataframe['rt'].std()
    mean_rt = unprocessed_dataframe['rt'].mean()
    # Defining an upper outlier
    upperoutlier = mean_rt + std_rt*2
    # Defining an lower outlier
    loweroutlier = mean_rt - std_rt*2
    # Setting parameters for slow rt outliers 
    slow = unprocessed_dataframe.loc[unprocessed_dataframe['rt'] > upperoutlier]
    # Replacing upper outliers with mean
    unprocessed_dataframe.loc[slow.index, 'rt'] = mean_rt
    # Setting parameters for fast rt outliers
    fast = unprocessed_dataframe.loc[unprocessed_dataframe['rt'] < loweroutlier]
    # Replacing lower outliers with mean
    unprocessed_dataframe.loc[fast.index, 'rt'] = mean_rt
    processed_dataframes.append(unprocessed_dataframe)
    fast_list.append(fast)
    slow_list.append(slow)
