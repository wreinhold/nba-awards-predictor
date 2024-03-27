# nba-awards-predictor
This repository contains the final project for the UNC Data Science. It was completed in its entirety by myself. The challenge was to use machine learning to solve a problem. I decided to build models that could predict the end of season awards for the NBA. 

# Data Gathering, Cleaning, and Storage
I utilized data that I downloaded from [kaggle.com](https://www.kaggle.com/datasets/sumitrodatta/nba-aba-baa-stats?resource=download), a website that allows users to share large data sets for use in machine learning projects among other things. The link above contains the data set that I used. Ultimately, I whittled the provided CSV files down to 4.

To store this data, I created a PostgreSQL database that can be recreated using the SQL file in the repository.

As I imported the data into my Jupyter Notebook file, I had to perform various cleaning activities. There were multiple columns that I did not need or were too similar and would lead to model overfitting. There was also a plethora of null values in the data set that I had to account for. After cleaning, I merged the 4 data sets into one Pandas DataFrame. 

# Building the models
To begin the models, I first created dummy variables for the awards. I then split the data for the models, mapped the Yes or No boolean values to 1s and 0s, and dropped any further columns and rows that I did not need. This part was crucial as the awards needed different data sets. For example, the All-Rookie teams needed only players who were in their first year. All-Defense teams did not need to account for offensive stats. There was also a lack of data on the 2023 and 2024 awards, so those stats were removed.

After the additional cleaning, I split the data sets into training and testing, and scaled the X data. This was important as the statistics have changed throughout NBA history as the game has evolved. What might've been impressive statistically in the 1980s would not stack up with the outburst of scoring in the current NBA. 

I then built the four different neural network models using TensorFlow. After playing around with different numbers of hidden layers and nodes, I ultimately created 4 models that had a minimum of 95% accuracy. These were exported into the h5 files in the repository.
