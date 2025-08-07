# Google-Play-Store-Apps
Google Play Store Apps of Exploratory Data Analysis. Analyze all listed apps and reorganize data using Python and its Library pandas, numpy, seaborn , ML, SQL and Excel  these tools and Making sentiment analysis.


![playstore1](https://github.com/nihalshaikh-analyst/Google-Play-Store-Apps/blob/main/playstore1.png)


## About Dataset

While many public datasets (on Kaggle and the like) provide Apple App Store data, there are not many
counterpart datasets available for Google Play Store apps anywhere on the web. On digging deeper, I found
out that the iTunes App Store page deploys a nicely indexed appendix-like structure to allow for simple and
easy web scraping. On the other hand, Google Play Store uses sophisticated modern-day techniques (like
dynamic page load) using JQuery making scraping more challenging.


[Dirty Dataset](https://github.com/nihalshaikh-analyst/Google-Play-Store-Apps/blob/main/googleplaystore_user_reviews.csv)

---------------------------------------------------------------------------------------------------------------

[Clean Dataset](https://github.com/nihalshaikh-analyst/Google-Play-Store-Apps/blob/main/googleplaystore.csv)



### The Play Store apps data has enormous potential to drive app-making businesses to success. Actionable insights can be drawn for developers to work on and capture the Android market. This information is scraped from the Google Play Store. This app information would not be available without it. Each app (row) has values for catergory, rating, size, and more.



## Exploratory Data Analysis of Google Play Store Apps

![playstore2](https://github.com/nihalshaikh-analyst/Google-Play-Store-Apps/blob/main/playstore2.png)


## Project Objective

#### The goal of this project is to analyze the characteristics of apps on the Google Play Store, including their ratings, reviews, sizes, installation counts, and more. The analysis will help identify trends, outliers, and patterns in the app market.


## Key insights

**"The "Art and Design" category has the highest number of installs.
Developing apps within the "Family" and "Lifestyle" categories may result in higher revenue.
Approximately 61% of users have a positive sentiment, while only around 15% express negative sentiment.
Free apps account for 92.12% of the dataset, while paid apps constitute 7.81%.
The "Everyone" content rating category dominates, representing 81.80% of all apps.
The most prevalent categories on the Play Store are "Family," "Game," and "Tools."
"Game" category presents potential opportunities for developers due to its high number of installs.
Popular genres for app downloads include "Tools," "Entertainment," "Education," "Business," and "Medical."
The average rating of apps on the Play Store is 4.17, indicating a satisfactory overall quality.
Users prefer lightweight apps and may be hesitant to download larger, paid apps.
Apps reviewed by a larger number of people tend to be downloaded more frequently.
Users tend to leave harsher reviews for paid apps.
A positive correlation exists between installs and rating.
Developing an app with a high rating requires timely updates and optimal app size.
Developing free apps with a content rating suitable for everyone is beneficial.
The dataset holds immense potential for improving business value and making a positive impact. 
It extends beyond the specific problem addressed in this project, with numerous other interesting possibilities waiting to be explored through further analysis."**




## Step by Step Process

- Importing Libraries
  
- Data Loading and exploration and cleaning
c Load the csv file with the pandas
↪ creating the dataframe and understanding the data present in the dataset using pandas
↪ Dealing with the missing data, outliers and the incorrect records

- Checking the tail of the column

- Set the option maximum of rows and column

- Checking the shape of the columns

- Checking the info of the dataset

- Removing this row from the data because this is causing some problem 10472

- Taking size column and make it numeric

- Checking the number of values in three different categories in Size

- Convert the whole size of the column into bytes

- Observations¶
● Remove + sign
● Remove , from the values
● Convert the column in to integers

Observations:
● Now, we have only 6 columns as numeric data type.
● We can observe their descriptive statistics. and make tons of observations as per our hypotheses.
● We can see that the Rating column has a minimum value of 1 and a maximum value of 5, which is the
range of rating, and the mean is 4.19 which is a good rating. On an average people give this rating.
● We can see that the Reviews column has a minimum value of 0 and a maximum value of 78,158,306
78+ Millions, which is the range of reviews, and the mean is 444,111.93 which is a good number of
reviews. On an average people give this number of reviews to the apps. But it does not make sense to us,
as we have different categories of apps.
● Similarly, we can observe the other columns as well.
Therefore, the most important thing is to classify as app based on the correlation matrix and then observe the
descriptive statistics of the app category and number of installs, reviews, ratings, etc.
But even before that we have to think about the missing values in the dataset.

- Observations:
● We have 1695 missing values in the 'Size_in_bytes' and 'Size_in_Mb' columns, which is 15.6%
of the total values in the column.
● We have 1474 missing values in the 'Rating' column, which is 13.6% of the total values in the column.
● We have 8 missing value in the 'Current Ver' column, which is 0.07% of the total values in the
column.
● We have 2 missing values in the 'Android Ver' column, which is 0.01% of the total values in the
column.
● We have only 1 missing value in Category, Type and Genres columns, which is 0.009% of the total
values in the column.
2.3. Dealing with the missing values
- We can not impute the Rating column as is is directly linked with the installation
column. To test this Hypothesis we need to plot the Rating column with the
Installs and Size columns and statistically test it using pearson correlation test.


- ● Lighter color shows the high correlation and darker color shows the low correlation
● We can see that the Reviews column has a high correlation with the Installs column, which is 0.64
according to corr(). Which is quite good.
■ This shows that the more the reviews the more the installs are for one app. If in any case we need
to impute reviews we have to think of number of install.
○ If we have an ap with 2 installs and we imputer the reviews with 1000 or via average
reviews then it will be wrong.
● Installs is slightly correlated with Size_in_Mb or Size_in_bytes , which is 0.16, this also shows us
the importance of size and Installs. But we can not depend on it as the Peason correlation is very low.
● Before going ahead, let's remove the rows with missing values in the Current Ver, Android Ver

- Observations
● Only Rating and Size_in_bytes or Size_in_Mb columns are left with missing values.
■ We know that we have to be carefull while deadling with Rating column, as it is directly linked
with the Installs column.
■ In Size columns we already know about Varies with device values, which we have
converted into null values, we do not need to impute at the moment, as every app has different
size and nobody can predict that as nearly as possible.

● It doesn't show any trend, because, you should know that Rating is a categorical variable (Ordinal) and
Reviews is a continuous variable, therefore, we can not plot them together.
● Let's try with Reviews and Installs

● Now we see a slight trend but still the issue is installs were given in a factorial manner, as 10+, 20+,
1000+ etc, and these are not continuous number but Discreet one, therefore, we can only see a slight
trends here. Let's plot a line plot to see the trend.

● Here, we can see a nice trend, which shows that number of Reviews increases with the number of
Installs, which is quite obvious.

- Observation
-We can see that most of the null values from Rating column are no - Moderate Installation apps, which make
sense that if the app has less installations, it has less Rating and review.
● But wait, we have to check for the duplicates as well, as they can affect our analysis.
2.3. Duplicates
● Removing duplicates is one of the most important part of the data wrangling process, we must remove the
duplicates in order to get the correct insights from the data.
● If you do not remove duplicates from a dataset, it can lead to incorrect insights and analysis.
● Duplicates can skew statistical measures such as mean, median, and standard deviation, and can also
lead to over-representation of certain data points.
● It is important to remove duplicates to ensure the accuracy and reliability of your data analysis

## Conclusion

- In addition, the Family and Lifestyle categories present a promising opportunity for maximizing profitability and generating high revenue. By identifying specific niches within these categories and developing tailored apps that cater to the needs and preferences of the target audience, we can position ourselves for success.

- To ensure positive sentiment and maintain a good reputation, it is crucial to encourage users to leave reviews and ratings. Positive reviews not only enhance our app's credibility but also influence the download frequency. We must also address negative feedback promptly to improve user satisfaction and continually enhance the quality of our apps.

- Considering that the majority of apps are offered for free, we should optimize our freemium model. By offering a free version of our app with additional paid features or in-app purchases, we can attract a larger user base and increase the likelihood of generating revenue.



Any query contact to us nihalshaikh.analyst@gmail.com

and connect to us [Linkedin](https://www.linkedin.com/in/nihalshaikh1/)

-----------------Thank you..................
