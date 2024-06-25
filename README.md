# Database-Main-Project

https://docs.google.com/document/d/1pVwyGORCdfTGuB3ClrS_UdhIV7efQkwhbwwZA8I2rKU/edit?usp=sharing
https://www.canva.com/design/DAGIyyCybR8/SFN6i-sBQD-qRBuJQFQJrg/edit?utm_content=DAGIyyCybR8&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton


# Social Media Usage Analysis Database Project
# Dataset Overview
The dataset contains information on the average time spent by users on various social media platforms, including demographic details such as age, gender, location, interests, profession, and more.

#Goals
The goal of this project is to analyze the dataset to uncover user behavior patterns, popular platforms, and interests.

# Import Process and Interesting Findings

Imported the CSV file into MySQL Workbench.
Created a table social_media_usage to store the data.
Used the LOAD DATA INFILE command to populate the table.

#Interesting Finding:

Observed that younger users tend to spend more time on social media compared to older users.

# Cool Fact 1 - Average Time Spent on Social Media by Age Groups

SELECT 
    CASE
        WHEN age BETWEEN 13 AND 18 THEN '13-18'
        WHEN age BETWEEN 19 AND 24 THEN '19-24'
        WHEN age BETWEEN 25 AND 34 THEN '25-34'
        WHEN age BETWEEN 35 AND 44 THEN '35-44'
        WHEN age BETWEEN 45 AND 54 THEN '45-54'
        WHEN age BETWEEN 55 AND 64 THEN '55-64'
        ELSE '65+'
    END AS age_group,
    AVG(time_spent) AS average_time_spent
FROM 
    social_media_usage
GROUP BY 
    age_group
ORDER BY 
    age_group;
    
#What I Learned:

Users aged 19-24 spend the most time on social media, averaging 5.2 hours per day.
Users aged 65+ spend the least time on social media, averaging 2.8 hours per day.

# Cool Fact 2: Distribution of Interests Among Users

# SQL Query:

SELECT interests, COUNT(*) AS count
FROM social_media_usage
GROUP BY interests
ORDER BY count DESC
LIMIT 3;

# What I Learned:

The most common interests among users are Lifestyle, Sports, and Travel.

# Questions and SQL Queries

Question 1: What is the average time spent on social media by users in different age groups?
SQL Query:

SELECT 
    CASE
        WHEN age BETWEEN 13 AND 18 THEN '13-18'
        WHEN age BETWEEN 19 AND 24 THEN '19-24'
        WHEN age BETWEEN 25 AND 34 THEN '25-34'
        WHEN age BETWEEN 35 AND 44 THEN '35-44'
        WHEN age BETWEEN 45 AND 54 THEN '45-54'
        WHEN age BETWEEN 55 AND 64 THEN '55-64'
        ELSE '65+'
    END AS age_group,
    AVG(time_spent) AS average_time_spent
FROM 
    social_media_usage
GROUP BY 
    age_group
ORDER BY 
    age_group;
Question 2: What are the top 3 most popular social media platforms among users in different professions?

# SQL Query:

SELECT 
    profession,
    platform,
    COUNT(*) AS user_count
FROM 
    social_media_usage
GROUP BY 
    profession, platform
ORDER BY 
    profession, user_count DESC
LIMIT 3;

# Average Time Spent on Social Media by Age Groups
![image](https://github.com/Tusneld/Database-Main-Project/assets/109280117/e16febfb-45b8-483a-bc5e-95827353373f)


# Explanation:

The bar chart illustrates that users aged 19-24 spend the most time on social media, while users aged 65+ spend the least time.

# Distribution of Interests Among Users

![image](https://github.com/Tusneld/Database-Main-Project/assets/109280117/f356bbf5-b5ce-443a-89bd-76039ecc236b)


# Explanation:

The pie chart shows that Lifestyle, Sports, and Travel are the top three interests among users.

# Top Social Media Platforms by Profession

![image](https://github.com/Tusneld/Database-Main-Project/assets/109280117/afaab82b-ecd2-4bde-8ab9-e82e94cc7e0c)

#Explanation:

The bar chart indicates that Facebook is the most popular platform among both engineers and teachers, with YouTube and Instagram also being popular.

# Summary

Introduced the dataset and the goals of the analysis.
Explained the import process and shared an interesting finding.
Presented two cool facts discovered from the data.
Discussed the formulated questions, SQL queries, and the insights gained.
Showcased charts that visualized the findings.

# Conclusion:
The analysis provided valuable insights into user behavior on social media, highlighting differences in usage patterns by age group, interests, and profession.
