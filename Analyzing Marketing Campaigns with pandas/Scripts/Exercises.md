# Exercises with 🐍
In this repository, I will show pandas basics including importing datasets, exploratory analysis, and basic plotting.


### :arrow_forward:`Step 1` - Importing the dataset

#### :arrow_right: Exercise 1

In this exercise, I will begin by importing pandas, matplotlib and the marketing dataset into my environment.
```python
#Write your code below this line 👇
import pandas as pd
import matplotlib.pyplot as plt
marketing = pd.read_csv('Analyzing Marketing Campaigns with Pandas\DataSets\marketing.csv')
```

### :arrow_forward:`Step 2` - Examining the data

#### :arrow_right: Exercise 2
In this exercise, I will examinie the data to ensure it is valid.

Write a program that prints the first five rows of the DataFrame.

```python
#Write your code below this line 👇
print(marketing.head())
```

Write a program that prints the summary statistics of all columns in the marketing DataFrame.

```python
#Write your code below this line 👇
print(marketing.describe())
```


Write a program that checks column data types and non-missing values

```python
#Write your code below this line 👇
print(marketing.info())
```

### :arrow_forward:`Step 3` - Updating the data type of a column

#### :arrow_right: Exercise 3
Write a program that converts **is_retained** to a **boolean**

```python
#Write your code below this line 👇
marketing['is_retained'] = marketing['is_retained'].astype('bool')
```


Check the data type of is_retained, again

```python
#Write your code below this line 👇
print(marketing['is_retained'].dtype)
```

### :arrow_forward:`Step 4` - Adding new columns

#### :arrow_right: Exercise 4
Write a program that will add two columns to **marketing**:

1-**channel_code**: represents the numeric value of the subscribing channel
2-**is_correct_lang**: conveys whether the ad was shown to the user in their preferred language

Mapping for channels
```python
#Write your code below this line 👇
channel_dict = {"House Ads": 1, "Instagram": 2, 
                "Facebook": 3, "Email": 4, "Push": 5}
```

Map the channel to a channel code
```python
#Write your code below this line 👇
marketing['channel_code'] = marketing['subscribing_channel'].map(channel_dict)
```

### :arrow_forward:`Step 5` - Date columns

#### :arrow_right: Exercise 5
In this exercise, I will practice reading the CSV with proper date columns and create a day of the week column.

```python
#Write your code below this line 👇
# Import pandas into the environment
import pandas as pd

# Import marketing.csv with date columns
marketing = pd.read_csv('Analyzing Marketing Campaigns with Pandas\DataSets\marketing.csv', 
                        parse_dates = ['date_served', 'date_subscribed', 'date_canceled'])

# Add a DoW column
marketing['DoW'] = marketing['date_subscribed'].dt.dayofweek
```

### :arrow_forward:`Step 6` - Daily marketing reach by channel

#### :arrow_right: Exercise 6
In this exercise, I'll determine how many users are seeing the marketing assets each day. This is crucial to understand how effective our marketing efforts have been over the past month.


```python
#Write your code below this line 👇
# Group by date_served and count number of unique user_id's
daily_users = marketing.groupby(['date_served'])['user_id'].nunique()

# Print head of daily_users
print(daily_users.head())
```

### :arrow_forward:`Step 7` - Daily marketing reach by channel

#### :arrow_right: Exercise 7
In the previous exercise, I created a **daily_subscribers** DataFrame, which contained the number of users who subscribed each day. While this was a great first step, it is challenging to interpret daily trends by looking at a table. To make it easier for me and business stakeholders to notice subscriber trends, I will visualize my results using a line plot.


```python
#Write your code below this line 👇
# Plot daily_subscribers
daily_users.plot()

# Include a title and y-axis label
plt.title('Daily users')
plt.ylabel('Number of users')

# Rotate the x-axis labels by 45 degrees
plt.xticks(rotation = 45)

# Display the plot
plt.show()
```

#### :dart: Visualizing daily marketing reach
![image](https://github.com/erisaxhelilaj/Python_Projects/blob/master/Analyzing%20Marketing%20Campaigns%20with%20pandas/DataSets/Figure_1.png)




