# Data-Analytics-Tool-Analytics

## Youtube Dataset Analytics

We will be perform the following operations on the youtube dataset to learn more about sql and python connection:
- Step 1 - Read the youtube dataset and create a dataframe
- Step 1 - Create a  function to calculate the distributuion of channel type from the top 1000 records
- Step 2 Insert Top 1000 records inserted into a CSV file
- Step 3 - Create a Sql connection and perform the following steps:
    - Create a new database
    - Create a new table and import the csv file generated in Step 2 into it.
    - Read data from the table created in previous step and display it.


### Read the youtube dataset and create a dataframe
```
import pandas as pd
import numpy as np

data=pd.read_csv(r"Enter path to youtube_dataset.csv", encoding='cp1252')
data.head()  <!-- Display the top 5 records of the dataframe-->
```


### Function to calculate the distributuion of channel type from the top 1000 records
```
def subset_data_channeltype_distribution(df, no_of_rows):
  subset = df.head(no_of_rows)
  return subset.groupby('channeltype')['channeltype'].count()

<!-- Calling a function -->
subset_data_channeltype_distribution(data,1000)  <!-- Passing number of rows as a variable to make the function dynamic -->
```


    