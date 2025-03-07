## Web Link 
https://gabi246.github.io/a3-Experiment/ 

# Hypothesis 
Our study will focus on which type of graph is easiest to interpret and if color impacts the user’s ability to interpret the graph. We will be comparing Bar graphs, Stacked Bar Charts, and Pie Charts. For our two trials of each chart, we will be using gray and red to act as the color variable in our study. We decided to choose red because of its brightness and notability to be associated with being quick (like Lightning McQueen :) ). 

We hypothesize that the Bar graph will be interpreted the easiest followed by the pie chart then the stacked bar chart. We are also hypothesized that the charts using color will be interpreted with more success than those with no color. 

# Data Generation 
The data that is used to generate the pie chart, bar chart, and stacked bar chart is generated from an R file. The values are randomly generated from 0 to 100 and then saved to a csv file. \

# Stacked Bar Chart
In making a stacked bar chart, I first created a custom object that structured those values in the csv so they would be easier to extract when building the stacked bar chart. This object consisted of a label depicting each portion of the stacked bar, the value which was the numeric value or how long each portion of the stacked bar was, and finally a boolean value titled chosen which was true if it was one of the two portions of the graph that was being compared. This was data was then passed into the function that actually created the stacked bar that checked the csv and if the “chartNum” value was set to 1 it would make a colored stacked bar chart and if the “chartNum” value was set to 2 it would make a grayscale stacked bar chart. The way the graph is structured is through creating a bunch of rectangles next to each other that is contained in an svg using d3. 

![Screenshot (59)](https://user-images.githubusercontent.com/48228807/154776685-4530394d-5b66-42c6-8e41-5a5350f098b0.png)

# Pie Chart
The Pie Chart is created from data in a csv file. The arclength for each of the slices in the pie chart are calculated using a d3 arc library from the total radius from the width and height of the svg element. Next, when filling the chart with a color, it depends on what the chart number is. If the chart number is three, then the pie chart is filled with color. But if the chart number is four, then the pie chart is filled with gray. The asterisk is then applied to the on the slices that are going to be compared and if the chart is colored, the slices also turn red. 

![Screenshot (60)](https://user-images.githubusercontent.com/48228807/154776792-1e9f357f-2b49-4b97-b0d9-f9512ecfc4cd.png)

# Bar Chart
The bar chart is also created from the data in a csv file. The bar heights are scaled to fit the svg file. In a similar way to the pie chart, the bar chart determines whether or not it is colored or gray using the chart number.

![Screenshot (61)](https://user-images.githubusercontent.com/48228807/154776795-9baed3e8-6f26-4e4c-98b1-8555b91c0817.png)

# Web Interface 
The website consists of 6 different graphs, the colored stacked bar chart, grayscale stacked bar chart, colored pie chart, grayscale pie chart, colored bar chart, and the grayscale bar chart. In order to assist the user on which two portions of the graphs they were comparing we decided to include asterisks to highlight the two specific portions. We phrased the questions as “how many times bigger is the bigger portion than the smaller portion”. We felt that this was a better way to phrase it than using percentages because it is a lot less complicated for someone to say how much bigger something is than having to deal with percentages. We wanted the user experience to be as simple as possible. This is why when the user enters their answer, the graph simply goes away so that they can move onto the next question as efficiently as possible without having to think of any other buttons to press and have their full concentration on the experiment. At the end of the experiment, their results are compiled in the form of a csv that consists of the following data points:


- Participant Number: the id of the participant
- Chart Number: the specific chart that the answer correlates to
    - 1 = Colored Stacked Bar Chart
    - 2 = Grayscale Stacked Bar Chart
    - 3 = Colored Pie Chart
    - 4 = Grayscale Pie Chart
    - 5 = Colored Bar Chart
    - 6 = Grayscale Bar Chart
- True Value: The correct answer of how many times bigger the bigger portion is
- Observed Value: the value that the user entered
- Error Rate: the error rate that was calculated


# R Graphs and Analysis
We decided to create a boxplot with jitter of each chart type, graphing the error values using the ggpubr package, a cousin if you will of ggplot2. The box plot is great in that it shows the mean, range, error, and confidence intervals all on the same graph. The jitter also allows us to see all the data points on each chart, showing us any outliers that might be skewing the data. 
It was found that the Colored Bar Chart, Colored Pie Chart, and Gray stacked bar chart were interpreted the easiest. This can be seen by the smaller variance as depicted by the smaller size of the boxes. This supports our hypothesis that the colored charts will be interpreted with more success than those with no color. This can be seen with the colored bar chart as well as the colored pie chart. 
In addition to this, we hypothesized that the bar charts would have more success than the other charts. This can also be seen as the colored bar chart was the one that had the most success. We found that the Gray Stacked Bar Chart also performed very well which was unexpected. We think the chart may have been easier to interpret because it was a horizontal stacked bar chart rather than a vertical stacked bar chart. This would allow the user to use the height of the chart as a commonality when comparing the two sections of the chart. In addition to this, we were surprised to see how much variance there was in the colored stacked bar chart. 
In general, the gray charts are seen to have more variance than the colored charts as predicted. The colored stacked bar chart had a lot of variance, which was unpredicted. We think this may have been because the red color did not pop enough in comparison to the other colors used in the stacked bar chart, making it more difficult for the user to interpret the graph. Also we think this may have been because there were too many colors associated with the stacked bar and it was confusing for the user to have the portions laid out horizontally to compare the different sizes.

![Screenshot (58)](https://user-images.githubusercontent.com/48228807/154776583-b438e5a3-916a-4063-a60f-8b0cde516c62.png)

# Discussion 
When looking back over the instructions for this assignment, we had not released that 200 trials per visualization type in total where needed. We were not able to reach this goal, but were able to get 29 participants to take the quiz, totalling 29 trials per visualization. 
In the future, to improve this experiment we would run more trials on each of the visualizations to collect more data and also have varying data sets. 

GitHub Details
---

- Fork the GitHub Repository. You now have a copy associated with your username.
- Make changes to index.html to fulfill the project requirements. 
- Make sure your "master" branch matches your "gh-pages" branch. See the GitHub Guides referenced above if you need help.
- Edit this README.md with a link to your gh-pages site: e.g. http://YourUsernameGoesHere.github.io/Experiment/index.html
- Replace this file (README.md) with your writeup and Design/Technical achievements.
- To submit, make a [Pull Request](https://help.github.com/articles/using-pull-requests/) on the original repository.
- Name your submission using the following scheme: 
```
a3-FirstLastnameMember1-FirstLastnameMember2-FirstLastnameMember3-...
```
