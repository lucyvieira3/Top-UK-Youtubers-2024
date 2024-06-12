# Top UK Youtubers 2024

# Objective

## What is the key pain point?

The Head of Marketing wants to find out who the top YouTubers are in 2024 to decide on which YouTubers would be best to run marketing campaigns throughout the rest of the year.

## What is the ideal solution?

To create a dashboard that provides insights into the top UK YouTubers in 2024 that includes their

- Subscriber count
- Total views
- Total videos, and
- Engagement metrics

This will help the marketing team make informed decisions about which YouTubers to collaborate with for their marketing campaigns.

# User story

As the Head of Marketing, I want to use a dashboard that analyses YouTube channel data in the UK.

This dashboard should allow me to identify the top performing channels based on metrics like subscriber base and average views.

With this information, I can make more informed decisions about which Youtubers are right to collaborate with, and therefore maximize how effective each marketing campaign is.

# Data source

## What data is needed to achieve our objective?

We need data on the top UK YouTubers in 2024 that includes their

- Channel names

- Total subscribers

- Total views

- Total videos uploaded

Where is the data coming from? The data is sourced from Kaggle (an Excel extract), <a href="https://www.kaggle.com/datasets/bhavyadhingra00020/top-100-social-media-influencers-2024-countrywise?resource=download"> see here to find it.</a >

# Stages

- Design
- Developement
- Testing
- Analysis
  
# Design

## Dashboard components required

To understand what it should contain, we need to figure out what questions we need the dashboard to answer:

- Who are the top 10 YouTubers with the most subscribers?
- Which 3 channels have uploaded the most videos?
- Which 3 channels have the most views?
- Which 3 channels have the highest average views per video?
- Which 3 channels have the highest views per subscriber ratio?
- Which 3 channels have the highest subscriber engagement rate per video uploaded?

For now, these are some of the questions we need to answer, this may change as we progress down our analysis.

# Dashboard mockup

<img width="672" alt="dashboard_mockup" src="https://github.com/lucyvieira3/Top-UK-Youtubers-2024/assets/153330654/a8da7a86-672d-46b3-9eba-30d97a6c6074">

## Tools Used 

Excel - Exploring the data

SQL Server - Cleaning, testing, and analyzing the data

Power BI - Visualizing the data via interactive dashboards

GitHub - Hosting the project documentation and version control

## Development

What's the general approach in creating this solution from start to finish?

1. Get the data
2. Explore the data in Excel
3. Load the data into SQL Server
4. Clean the data with SQL
5. Test the data with SQL
6. Visualize the data in Power BI
7. Generate the findings based on the insights
8. Write the documentation + commentary
9. Publish the data to GitHub Pages

# Visualization

## Results

<img width="907" alt="powerbi_dashboard" src="https://github.com/lucyvieira3/Top-UK-Youtubers-2024/assets/153330654/72281c09-0d09-49a2-868b-9f14f503002e">

# DAX Measures

## 1. Total Subscribers (M)

Total Subscribers (M) = 
VAR million = 1000000
VAR sumOfSubscribers = SUM(view_uk_youtubers_2024[total_subscribers])
VAR totalSubscribers = DIVIDE(sumOfSubscribers,million)

RETURN totalSubscribers

## 2. Total Views (B)

Total Views (B) = 
VAR billion = 1000000000
VAR sumOfTotalViews = SUM(view_uk_youtubers_2024[total_views])
VAR totalViews = ROUND(sumOfTotalViews / billion, 2)

RETURN totalViews

## 3. Total Videos
Total Videos = 
VAR totalVideos = SUM(view_uk_youtubers_2024[total_videos])

RETURN totalVideos

## 4. Average Views Per Video (M)
Average Views per Video (M) = 
VAR sumOfTotalViews = SUM(view_uk_youtubers_2024[total_views])
VAR sumOfTotalVideos = SUM(view_uk_youtubers_2024[total_videos])
VAR  avgViewsPerVideo = DIVIDE(sumOfTotalViews,sumOfTotalVideos, BLANK())
VAR finalAvgViewsPerVideo = DIVIDE(avgViewsPerVideo, 1000000, BLANK())

RETURN finalAvgViewsPerVideo 

## 5. Subscriber Engagement Rate
Subscriber Engagement Rate = 
VAR sumOfTotalSubscribers = SUM(view_uk_youtubers_2024[total_subscribers])
VAR sumOfTotalVideos = SUM(view_uk_youtubers_2024[total_videos])
VAR subscriberEngRate = DIVIDE(sumOfTotalSubscribers, sumOfTotalVideos, BLANK())

RETURN subscriberEngRate 

## 6. Views per subscriber
Views Per Subscriber = 
VAR sumOfTotalViews = SUM(view_uk_youtubers_2024[total_views])
VAR sumOfTotalSubscribers = SUM(view_uk_youtubers_2024[total_subscribers])
VAR viewsPerSubscriber = DIVIDE(sumOfTotalViews, sumOfTotalSubscribers, BLANK())

RETURN viewsPerSubscriber 

# Analysis

## Findings

## 1. Who are the top 10 YouTubers with the most subscribers?
Rank	Channel Name	Subscribers (M)
1	NoCopyrightSounds	33.60
2	DanTDM	28.60
3	Dan Rhodes	26.50
4	Miss Katy	24.50
5	Mister Max	24.40
6	KSI	24.10
7	Jelly	23.50
8	Dua Lipa	23.30
9	Sidemen	21.00
10	Ali-A	18.90
   
## 3. Which 3 channels have uploaded the most videos?
Rank	Channel Name	Videos Uploaded
1	GRM Daily	14,696
2	Manchester City	8,248
3	Yogscast	6,435

## 4. Which 3 channels have the most views?
Rank	Channel Name	Total Views (B)
1	DanTDM	19.78
2	Dan Rhodes	18.56
3	Mister Max	15.97

## 5. Which 3 channels have the highest average views per video?
Channel Name	Averge Views per Video (M)
Mark Ronson	32.27
Jessie J	5.97
Dua Lipa	5.76

## 6. Which 3 channels have the highest views per subscriber ratio?
Rank	Channel Name	Views per Subscriber
1	GRM Daily	1185.79
2	Nickelodeon	1061.04
3	Disney Junior UK	1031.97

## 7. Which 3 channels have the highest subscriber engagement rate per video uploaded?
Rank	Channel Name	Subscriber Engagement Rate
1	Mark Ronson	343,000
2	Jessie J	110,416.67
3	Dua Lipa	104,954.95

## Notes
For this analysis, we'll prioritize analysing the metrics that are important in generating the expected ROI for our marketing client, which are the YouTube channels with the most subscribers, total views, and videos uploaded.

# Validation

1. Youtubers with the most subscribers
Calculation breakdown
Campaign idea = product placement

NoCopyrightSounds
Average views per video = 6.92 million
Product cost = $5
Potential units sold per video = 6.92 million x 2% conversion rate = 138,400 units sold
Potential revenue per video = 138,400 x $5 = $692,000
Campaign cost (one-time fee) = $50,000
Net profit = $692,000 - $50,000 = $642,000
b. DanTDM

Average views per video = 5.34 million
Product cost = $5
Potential units sold per video = 5.34 million x 2% conversion rate = 106,800 units sold
Potential revenue per video = 106,800 x $5 = $534,000
Campaign cost (one-time fee) = $50,000
Net profit = $534,000 - $50,000 = $484,000
c. Dan Rhodes

Average views per video = 11.15 million
Product cost = $5
Potential units sold per video = 11.15 million x 2% conversion rate = 223,000 units sold
Potential revenue per video = 223,000 x $5 = $1,115,000
Campaign cost (one-time fee) = $50,000
Net profit = $1,115,000 - $50,000 = $1,065,000
Best option from category: Dan Rhodes


2. Youtubers with the most videos uploaded
Calculation breakdown
Campaign idea = sponsored video series

GRM Daily
Average views per video = 510,000
Product cost = $5
Potential units sold per video = 510,000 x 2% conversion rate = 10,200 units sold
Potential revenue per video = 10,200 x $5= $51,000
Campaign cost (11-videos @ $5,000 each) = $55,000
Net profit = $51,000 - $55,000 = -$4,000 (potential loss)
b. Manchester City

Average views per video = 240,000
Product cost = $5
Potential units sold per video = 240,000 x 2% conversion rate = 4,800 units sold
Potential revenue per video = 4,800 x $5= $24,000
Campaign cost (11-videos @ $5,000 each) = $55,000
Net profit = $24,000 - $55,000 = -$31,000 (potential loss)
b. Yogscast

Average views per video = 710,000
Product cost = $5
Potential units sold per video = 710,000 x 2% conversion rate = 14,200 units sold
Potential revenue per video = 14,200 x $5= $71,000
Campaign cost (11-videos @ $5,000 each) = $55,000
Net profit = $71,000 - $55,000 = $16,000 (profit)
Best option from category: Yogscast

3. Youtubers with the most views
Calculation breakdown
Campaign idea = Influencer marketing

a. DanTDM

Average views per video = 5.34 million
Product cost = $5
Potential units sold per video = 5.34 million x 2% conversion rate = 106,800 units sold
Potential revenue per video = 106,800 x $5 = $534,000
Campaign cost (3-month contract) = $130,000
Net profit = $534,000 - $130,000 = $404,000
b. Dan Rhodes

Average views per video = 11.15 million
Product cost = $5
Potential units sold per video = 11.15 million x 2% conversion rate = 223,000 units sold
Potential revenue per video = 223,000 x $5 = $1,115,000
Campaign cost (3-month contract) = $130,000
Net profit = $1,115,000 - $130,000 = $985,000
c. Mister Max

Average views per video = 14.06 million
Product cost = $5
Potential units sold per video = 14.06 million x 2% conversion rate = 281,200 units sold
Potential revenue per video = 281,200 x $5 = $1,406,000
Campaign cost (3-month contract) = $130,000
Net profit = $1,406,000 - $130,000 = $1,276,000
Best option from category: Mister Max

# Discovery

## What did we learn?

We discovered that

- NoCopyrightSOunds, Dan Rhodes and DanTDM are the channnels with the most subscribers in the UK.

- GRM Daily, Man City and Yogscast are the channels with the most videos uploaded.

- DanTDM, Dan RHodes and Mister Max are the channels with the most views.
  
- Entertainment channels are useful for broader reach, as the channels posting consistently on their platforms and generating the most engagement are focus on entertainment and music.
  
# Recommendations

Dan Rhodes is the best YouTube channel to collaborate with if we want to maximize visbility because this channel has the most YouTube subscribers in the UK.

Although GRM Daily, Man City and Yogcasts are regular publishers on YouTube, it may be worth considering whether collaborating with them with the current budget caps are worth the effort, as the potential return on investments is significantly lower compared to the other channels.

Mister Max is the best YouTuber to collaborate with if we're interested in maximizing reach, but collaborating with DanTDM and Dan Rhodes may be better long-term options considering the fact that they both have large subscriber bases and are averaging significantly high number of views.

The top 3 channels to form collaborations with are NoCopyrightSounds, DanTDM and Dan Rhodes based on this analysis, because they attract the most engagement on their channels consistently.

# Potential ROI

## What ROI do we expect if we take this course of action?

- Setting up a collaboration deal with Dan Rhodes would make the client a net profit of $1,065,000 per video. 
- An influencer marketing contract with Mister Max can see the client generate a net profit of $1,276,000.
- If we go with a product placement campaign with DanTDM, this could generate the client approximately $484,000 per video. If we advance with an influencer marketing campaign deal instead, this would make the client a one-off net profit of $404,000.
- NoCopyrightSounds could profit the client $642,000 per video too (which is worth considering).
  
# Action plan

## What course of action should we take and why?

Based on our analysis, we beieve the best channel to advance a long-term partnership deal with to promote the client's products is the Dan Rhodes channel.

We'll have conversations with the marketing client to forecast what they also expect from this collaboration. Once we observe we're hitting the expected milestones, we'll advance with potential partnerships with DanTDM, Mister Max and NoCopyrightSounds channels in the future.

## What steps do we take to implement the recommended decisions effectively?

- Reach out to the teams behind each of these channels, starting with Dan Rhodes
- Negotiate contracts within the budgets allocated to each marketing campaign
- Kick off the campaigns and track each of their performances against the KPIs
- Review how the campaigns have gone, gather insights and optimize based on feedback from converted customers and each channel's audiences
