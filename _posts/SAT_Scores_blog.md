---
layout: post
title: SAT scores
---



{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## SAT scores\n",
    "==========\n",
    "\n",
    "### Introduction \n",
    "-----------------\n",
    "In this first week project for the General Assembly Data Science Immersive program, we will be dealing with a data set of SAT scores and their participation rate, as observed per state. \n",
    "\n",
    "### The data set\n",
    "-----------------\n",
    "\n",
    "The data set comes from the College Board and gives the mean SAT math and verbal scores, and the participation rate for each state and the District of Columbia for the year 2001.\n",
    "The data set is composed of 4 columns, as follows:\n",
    "  - State: string.\n",
    "  - Rate of Participation: string, will be converted to integer. On a scale 0 to 100, it tells us the percentage of students who took the SATs in the state described.\n",
    "  - Verbal: string, will be converted to integer. With a maximum score of 800, it gives us the average Verbal SAT score for students in the state described.\n",
    "  - Math: string, will be converted to integer. Similar to the Verbal SAT, it gives us the average Math SAT score for students in the state described.\n",
    "\n",
    "The data set is complete, with no missing data. The last line of the file describes national averages and will be discarded for homogeneity purposes.\n",
    "\n",
    "### Preparing the data\n",
    "------------------\n",
    "\n",
    "After inspection, the data required very little cleaning. I decided to discard the last line of the file (the national averages), since it adds a data point that is not in line with the rest of the data (one data point per state for each category).\n",
    "The data types were changed to integer for the three numerical columns (Rate, Verbal, Math), in order to facilitate mathematical operations and plotting.\n",
    "The table below describes the main statistics for the three columns.\n",
    "\n",
    "  <img style=\"float: middle;\" src='describe_data.png' width=\"300\">\n",
    "\n",
    "\n",
    "\n",
    "\n",
    "### Plotting the data\n",
    "\n",
    "I went on to plotting the data and drew the following plots:\n",
    "  - histograms on our three columns, both in Pyplot and Seaborn.\n",
    "  - scatter plots in Pyplot. \n",
    "  - one scatter plot and regression model in Seaborn.\n",
    "  - box plots of the three columns, in Pyplot.\n",
    "  - heat maps in Tableau.\n",
    "\n",
    "I will make the following observations:\n",
    "  - the Rate of Participation can be divided into two distinct subsets: one subset with high participation (between 51 and 82%), mainly representing the coasts, and another subset with low participation (between 4 and 34%), mainly representing the Heartland. \n",
    "  - both SATs have a similar plot, with bimodal distributions. Their coefficient of correlation are high (0.90), meaning that students who do well/poorly on one subject tend to do well/poorly on the other (if that conclusion can be drawn from state averages.)\n",
    "  \n",
    "       <img style=\"float: middle;\" src='scatterplotVerbalMath.png' width=\"300\"> \n",
    "  \n",
    "  - the SATs are negatively correlated to the Rate of Participation. In the figure above, the size of the bubbles on the scatter plot represent the Rate of Participation. The negative correlation is very clear: a grouping of low scores/high participation in the bottom left quadrant and another grouping of high scores/low participation in the upper right quadrant.\n",
    "  \n",
    "  - the heat maps give us a wonderful illustration of the coasts vs. the Heartland phenomenon. In the image below, the contrast is flagrant between the two areas. \n",
    "  \n",
    "       <img style=\"float: middle;\" src='Rate.png' width=\"600\">   \n",
    "       \n",
    "       \n",
    "### Conclusion\n",
    "\n",
    "As someone who never studied in the US, I am sometimes puzzled by the US education system. Still, I'll try to draw conclusions from the data we studied:\n",
    "  - While the SATs seem to be the norm on the coasts, with high participation rate drawing the average score down, the students in the Heartland take the tests in much smaller numbers, with much better results. From that observation, I'll conclude that only students with high grades take the tests in order to apply to highly selective colleges.\n",
    "  - Participation Rates of 4% in a number of states should not lead us to make definitive statements about those particular states' education systems. The average scores in those states are not representative of the entire population and the sample seems to be highly biased towards those with high grades and a good chance to do well on the tests.\n",
    "  \n",
    "Thank you for reading! "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": []
  }
 ],
 "metadata": {
  "anaconda-cloud": {},
  "kernelspec": {
   "display_name": "Python [conda root]",
   "language": "python",
   "name": "conda-root-py"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 2
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython2",
   "version": "2.7.12"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 1
}