# Exercises with 🐍
In this repository, I will show tpandas basics including importing datasets, exploratory analysis, and basic plotting.


### :arrow_forward:`Step 1` - Importing the dataset

#### :arrow_right: Exercise 1

In this exercise, I will begin by importing **Pandas**, **Matplotlib** and the marketing dataset into my environment.
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

**channel_code**: represents the numeric value of the subscribing channel
**is_correct_lang**: conveys whether the ad was shown to the user in their preferred language

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






