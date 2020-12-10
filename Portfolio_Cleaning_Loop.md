#### Below is a for loop that was used in a group project I was a part of to iterate our cleaning code over each dataframe corresponding to each participant.


```python
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
```
