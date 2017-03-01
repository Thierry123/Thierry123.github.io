---
layout: post
title: Data Science Job Search
---



### Introduction

The fourth week's project for DSI-GA covers the online job industry, and specifically listings for Data Scientist.
I will design a logistic regression model that predicts whether a certain listing will be for a high paying job or not.

### The scrape

The data set was assembled through web scraping. I started with Indeed.com, which yielded about 19,200 listings covering job title, location, salary, company and a brief blurb. Unfortunately, after eliminating duplicates, there were only 3000 left. Of these, I also had to check for the listings that mentioned a salary. Only 135 were left after this elimination. Upon closer examination, a large number of those were also for jobs not directly related to Data Science (Truck Driver, anyone?)

I decided then to expand my horizons by gathering data from Glassdoor.com, which was much more helpful in the quality of its data, but much more defensive of its domain. The scraping of Glassdoor was done in several steps, after an initial attempt at a broad scrape failed. When scraping city by city, the results became much better and I was able to obtain about 11,000 listings (job title, company, salary, location and the url leading to the job description.)

Of the 11,000 listings harvested, about 7,100 had a salary attached, which made the data set much more powerful. I started a second scrape of Glassdoor, this time gathering the job description for each job listed. This scrape was very time-consuming, but promised to yield a very large number of keywords.

Pressed by time, I was only able to gather 5,000 job descriptions. Time to move on to dressing the data.


### Cleaning the data

The salary data was made of strings such as 'Est.Salary 88k-124k'. A little cleaning was required to obtain floats and I decided to keep the mid-point of those numbers. 

Similarly, the company names required some string manipulation to get an satisfying set.

The job title didn't require any work, but I decided to add a column based on keywords present in the job title that denote of a senior (high-paying), a junior (low-paying) position or something in between.

I also added a column with the dictionary made from the company names value count. Finally, I made the metro area for which the job listing referred a dummy variable.


### The dictionary

I implemented a counter on the job descriptions attached to the jobs in the 75% percentile of salaries ($108,500 in my data set) to extract the 50 most common words in those descriptions (5 letters minimum, with the exceptions of 'data' and 'phd'.)
I then matched this list of 50 words with each listing's dictionary and gave the listing a word_score representing how many times one of the top 50 words were present in the listing.


### The regression

I fitted a LogisticRegression model from sklearn on a train set, and then tested it on the test set. The score was around 71%, meaning my model has a 71% chance of correctly classifying a listing as a high-paying job.

A grid search with L1. and L2 penalties revealed that the main features are the 'Senior' column (keyword in the job title) and four dummy variables (San Francisco, Princeton, New York and Los Angeles.)

A plot of the ROC, for your enjoyment:

![ROC](ROC.png)


### Conclusion

Although a great effort was made to gather data, the keyword dictionary on job description didn't seedm to help. In the end, a few obvious keywords about a job title and 3 metro areas known for high salaries (plus Princeton) were the determining factors.

Thank you for reading.







