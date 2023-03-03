# Social Buzz Marketing Content Analysis 

## Introduction   
This case study is part of the Accenture North America Data Analytics and Visualization. 

## About Social Buzz 
Social Buzz was founded by two former engineers from a large social media conglomerate, one from London and the other from San Francisco. They left in 2008 and both met in San Francisco to start their business. They started Social Buzz because they saw an opportunity to build on the foundation that their previous company started by creating a new platform where content took center stage. Social Buzz emphasizes content by keeping all users anonymous, only tracking user reactions on every piece of content. There are over 100 ways that users can react to content, spanning beyond the traditional reactions of likes, dislikes, and comments. This ensures that trending content, as opposed to individual users, is at the forefront of userfeeds.

## Method Approach 

## Phase 1: Ask 
#### 1.1: Business Task
Client wanted to see "An analysis of their content categories showing the top 5 categories with the largest popularity" 
As explained in the data model, popularity is quantified by the “Score” given to each reaction type.
We therefore need data showing the content ID, category, content type, reaction type, and reaction score.
So, to figure out popularity, we’ll have to add up which content categories have the largest score.

## Phase 2: Prepare
#### 2.1 Dataset Summary 
<img src ="https://imgur.com/gZGxF6I.png">  
<img src ="https://imgur.com/cdg1XnW.png"> 
#### 2.3 Dataset Limitations and Integrity 

## Phase 3: Process
### 3.1 Importing Datasets 
importing three datasets into ```MySQL database``` using UI 
<img src "https://imgur.com/6oShL6f.png">  

```sql
SELECT r.`Content ID`,r.`User ID`, r.Datetime , r.Type , c.Category, c.Type as ContentType, rt.sentiment,  rt.Score, SUM(rt.Score) AS SumScore
      FROM accenture.reactions as r 
      LEFT JOIN accenture.content as c
      ON r.`Content ID` = c.`Content ID`
      LEFT JOIN accenture.reactiontypes as rt
      ON r.Type = rt.Type 
      Where rt.Score IS NOT NULL
      Group By c.Category
      ORDER BY SumScore desc; 
``` 

## Phase 4: Analyze (Data Visualization)  

### 4.1 ```Top Five Most Popular Categories of Posts```
<img src ="https://imgur.com/saWmY9F.png">
From our analysis you can see that the top 5 most popular categories of posts were food, culture, soccer, cooking and animals in descending order.
Food had an aggregate popularity score of almost 76000. It is very interesting to see both food and cooking within the top 5, it really shows what people enjoy consuming as content. But also interesting to see culture too. Clearly users favor "real-life" content on this platform.
Furthermore soccer is an interesting category because there is the European championships being played very soon. This presents a huge opportunity for you to differentiate your platform and to run specific content or events linked to this global spectacle.

### 4.2 ```

<img src="https://imgur.com/SwvxGxi.png">
-From our analysis you can see that the top 5 most popular categories of posts were **food**, **culture**, **soccer**, **cooking** and **animals** in descending order.
-Food had an aggregate popularity score of almost 76000. It is very interesting to see both food and cooking within the top 5, it really shows what people enjoy consuming as content. 
-But also interesting to see culture too. Clearly users favor "real-life" content on this platform.
-Furthermore soccer is an interesting category because there is the European championships being played very soon. 
-This presents a huge opportunity for you to differentiate your platform and to run specific content or events linked to this global spectacle.

<img src= "https://imgur.com/W0YSZPq.png">
So to summarize:
We tackled this task and found the top 5 most popular categories as asked, but we also went one step further.
- We found that food and culture are the two most popular categories, suggesting that users like "real-life" content
- We also found that soccer was the third most popular, perhaps due to the tournament coming up. This presents a massive opportunity for Social Buzz to ride on this global event, as all eyes will be on it as well as the players.
- As much as this analysis was insightful, we are ready to take it to the next stage and we have the expertise within Accenture to help you realize these kinds of insights in production across your organization and in real time. We would love to help you with this.

<img src="https://imgur.com/DlSTgVy.png">
From your data we found that you had a total of 16 unique categories of posts across your sample dataset. This includes things such as Food, Culture and Sport.
As well as this, there was 1913 posts from just the Food category alone! People obviously really like food!
And also the most common month for users to post within was December, since this is such a seasonal month with so many holidays and events, this is interesting to know that people are most active during this month! But now, onto the main question... which is... what were the top 5 most popular categories of posts?

