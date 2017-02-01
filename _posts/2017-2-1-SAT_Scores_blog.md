---
layout: post
title: SAT scores
---

### Introduction

In this first week project for the General Assembly Data Science Immersive program, we will be dealing with a data set of SAT scores and their participation rate, as observed per state.

### The data set

The data set comes from the College Board and gives the mean SAT math and verbal scores, and the participation rate for each state and the District of Columbia for the year 2001.
The data set is composed of 4 columns, as follows:
  - State: string.
  - Rate of Participation: string, will be converted to integer. On a scale 0 to 100, it tells us the percentage of students who took the SATs in the state described.
  - Verbal: string, will be converted to integer. With a maximum score of 800, it gives us the average Verbal SAT score for students in the state described.
  - Math: string, will be converted to integer. Similar to the Verbal SAT, it gives us the average Math SAT score for students in the state described.

The data set is complete, with no missing data. The last line of the file describes national averages and will be discarded for homogeneity purposes.

### Preparing the data

After inspection, the data required very little cleaning. I decided to discard the last line of the file (the national averages), since it adds a data point that is not in line with the rest of the data (one data point per state for each category).
The data types were changed to integer for the three numerical columns (Rate, Verbal, Math), in order to facilitate mathematical operations and plotting.
The table below describes the main statistics for the three columns.

    <img style=\"float: middle;\" src='describe_data.png' width=\"300\">

### Plotting the data

I went on to plotting the data and drew the following plots:
  - Histograms on our three columns, both in Pyplot and Seaborn.
  - Scatter plots in Pyplot.
  - One scatter plot and regression model in Seaborn.
  - Box plots of the three columns, in Pyplot.
  - Heat maps in Tableau.

I will make the following observations:
  - The Rate of Participation can be divided into two distinct subsets: one subset with high participation (between 51 and 82%), mainly representing the coasts, and another subset with low participation (between 4 and 34%), mainly representing the Heartland.
  - Both SATs have a similar plot, with bimodal distributions. Their coefficient of correlation are high (0.90), meaning that students who do well/poorly on one subject tend to do well/poorly on the other (if that conclusion can be drawn from state averages.)
 
 <img style=\"float: middle;\" src='scatterplotVerbalMath.png' width=\"300\">

  - The SATs are negatively correlated to the Rate of Participation. In the figure above, the size of the bubbles on the scatter plot represent the Rate of Participation. The negative correlation is very clear: a grouping of low scores/high participation in the bottom left quadrant and another grouping of high scores/low participation in the upper right quadrant.
  - The heat maps give us a wonderful illustration of the coasts vs. the Heartland phenomenon. In the image below, the contrast is flagrant between the two areas.
<img style=\"float: middle;\" src='Rate.png' width=\"600\"> 

### Conclusion

As someone who never studied in the US, I am sometimes puzzled by the US education system. Still, I'll try to draw conclusions from the data we studied:
  - While the SATs seem to be the norm on the coasts, with high participation rate drawing the average score down, the students in the Heartland take the tests in much smaller numbers, with much better results. From that observation, I'll conclude that only students with high grades take the tests in order to apply to highly selective colleges.
  - Participation Rates of 4% in a number of states should not lead us to make definitive statements about those particular states' education systems. The average scores in those states are not representative of the entire population and the sample seems to be highly biased towards those with high grades and a good chance to do well on the tests.

Thank you for reading!