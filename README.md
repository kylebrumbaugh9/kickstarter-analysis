# Kickstarting with Excel

## Overview of Project

### Purpose
The purpose of this analysis was to determine if launch date and/or funding goals have any correlation to the likelihood that a fundraising campaign for a play will succeed. 
### Background
Louise is going to start a fundraising for her campaign *Fever* and wants to raise $10,000. She has provided me a spreadsheet containing over 4,000 campaigns that Kickstarter has hosted in the past to see if she can increase her odds of success based on previous, similar campaigns.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

![Pivot_Table_Launch_Data](https://user-images.githubusercontent.com/114685724/197660710-54426e61-c8a9-4127-9126-56b9fca24f93.png)

One point I wanted to look into was if there was a difference in success based on the start month of a campaign. I first built a pivot table (see above) to get a pared down view of the dataset. This allowed me to filter the data down to look at just theater campaigns, similar to Louise's play, but including other theater-related campaigns like musicals. Because I'm comparing this data over time, I decided a line graph is the most effective way to see if there are any trends in the data. In order to filter by year, I had to create a new column that selected "year" from the full date column of "Date Created Conversion" - this ended up being a lot easier than I thought as I had already converted the unix timestamp to a date, the Year() function made it really easy. 

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/114685724/197658924-9fec324b-41b7-4a5d-97ca-30fa62814dec.png)
### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](https://user-images.githubusercontent.com/114685724/197839211-fd937d80-b99d-4521-b95f-2b95c572e2ea.png)

Another point I wanted to dig into was if there was a difference in success based on the amount that the campaign was asking for. First, I created a new worksheet with the intention of counting the successful, failed, and canceled campaigns. In order to count them, I needed to use the COUNTIF() function in Excel. However, COUNTIF was not sufficient because I had multiple criteria, not just whether or not it was successful: I also needed to look at the amount the campaign wanted to raise. So in order to create "bins" or "buckets", I used COUNTIFS() to add multiple criteria to the function. From there, I realized the sheer number of campaigns was not telling a proper story; I instead needed to look at the percentages to get a better idea of what was going on. 

I noticed some trends in the data as well, so I threw a trendline onto the chart as well just to see if my eyes were deceiving me (see below). 
![Outcomes_vs_Goals_with_Trendlines](https://user-images.githubusercontent.com/114685724/197843284-11aebea1-acdc-4e49-a709-4984c513e57e.png)

### Challenges and Difficulties Encountered

I ran into a couple of challenges with the analysis. First, creating the "Outcomes Based on Goals" worksheet was slightly difficult with the COUNTIFS() function. Ensuring that I had the proper values turned into a lot of manual work since I could not figure out how to automatically fill the additional rows dynamically. Second, the first time I built the chart for "Outcomes Based on Goal", my values were off. I realized that I had just used the "less than" and "greater than" symbols instead of "less than or equal to" and "greater than or equal to". That fixed my values so that my graph was identical to the assignment. 
## Results

**What are two conclusions you can draw about the Outcomes based on Launch Date?**
1. One conclusion that I drew is that the data shows a spike in the number of successful campaigns in the late spring/early summer. After the peak in May, there is a relatively consistent decrease in success through the end of the year. The late spring/early summer stretch of May-July averages about 100 successful campaigns per month, dropping off to averaging about 55 successful campaigns per month from October-December. This tells me that the late spring/early summer period is the best time to launch a campaign, at about a 70% success rate. 
2. Another conclusion that I drew is that the rate of failed campaigns remains relatively consistent over the course of the year though, averaging around 40 failed campaigns per month. This tells me that December is the worst time to launch a campaign, as the success rate is about 50%.

**What can you conclude about the Outcomes based on Goals?**

The main conclusion I noticed here is that success is correlated with the amount of money in the goal. The more money being asked for, the less successful the campaign will be. It makes logical sense, but the data backed that theory up. The interesting point is that I see a spike in success between $30,000-$44,999, but the sample size is much smaller than the sample size around the smaller goals. All in all, I think the conclusion is, asking for less money means that the campaign is more likely to succeed. 
**What are some limitations of this dataset?**

One main limitation is the sample size of campaigns asking for more than $15,000 for a play. If we had more data, I think the "outcomes based on goals" section would be more valuable and more accurate, but it makes sense that not a lot of plays ask for $15,000 or more. 

Another limitation of the dataset is the fact that we're only looking at Kickstarter data. We should look at other sources of crowdfunding and see if the same trends exist and/or combine that data with our dataset so that we get a larger sample size. 

**What are some other possible tables and/or graphs that we could create?**

I've added trendlines to one of the graphs to visualize the trend more effectively, but besides that, I think we need to do some statistical analyses that take sample size into account for our "Outcomes Based on Goal" sheet and I think we need to take a look at the "Theater Outcomes Based on Launch Date" on a "per year" basis as well. I took a look briefly at the data and it appears that the late spring/early summer spike has been consistent over the last few years, but I want to make sure there aren't any outliers. At the end of the day, the goal here is to find the right ingredients for Louise to plan her crowdfunding campaign. I think we need to look at her costs and make sure that those are low so that we can drive the goal amount down to increase our odds for success and then launch the campaign in the late spring/early summer. Therefore, I think a table holding her costs and then some visualizations around odds of success would really help solidify the approach Louise should pursue. 
