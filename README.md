🎬 Netflix Content Analysis using SQL (PostgreSQL)
📌 Project Overview

This project analyzes Netflix Movies and TV Shows data using PostgreSQL to uncover valuable insights about content distribution, release trends, country-wise production, ratings, and genres.

The goal is to perform Exploratory Data Analysis (EDA) using SQL queries and generate business insights that support data-driven decision-making.

🚀 Objectives
Analyze the distribution of Movies vs TV Shows
Study content release trends over the years
Identify top content-producing countries
Understand audience targeting through content ratings
Explore genre popularity
Practice advanced SQL concepts such as aggregations, joins, and subqueries
🛠️ Tools & Technologies
PostgreSQL
SQL
Netflix Titles Dataset
Data Analysis & Query Optimization
📂 Dataset Information

The dataset contains information about Netflix content, including:

Column	Description
show_id	Unique identifier
type	Movie or TV Show
title	Content title
director	Director name
cast	Cast members
country	Production country
date_added	Date added to Netflix
release_year	Release year
rating	Content rating
duration	Duration/Seasons
listed_in	Genre
description	Content description
🧹 Data Cleaning & Preparation

Before analysis, the dataset was cleaned using SQL:

Checked for missing values
Handled NULL records
Standardized date formats
Removed duplicate entries
Processed multi-value fields (Country, Genres)

Example:

SELECT *
FROM netflix
WHERE country IS NULL;
📊 Key Analysis Performed
1️⃣ Movies vs TV Shows Distribution
SELECT type, COUNT(*) AS total_content
FROM netflix
GROUP BY type;

Insight: Netflix contains significantly more Movies than TV Shows.

2️⃣ Content Release Trend Analysis
SELECT release_year, COUNT(*) AS total_titles
FROM netflix
GROUP BY release_year
ORDER BY release_year;

Insight: Content production increased rapidly after 2015.

3️⃣ Top Content Producing Countries
SELECT country, COUNT(*) AS total_titles
FROM netflix
GROUP BY country
ORDER BY total_titles DESC
LIMIT 10;

Insight: The United States dominates content production, followed by India, the UK, and Canada.

4️⃣ Content Rating Analysis
SELECT rating, COUNT(*) AS total_titles
FROM netflix
GROUP BY rating
ORDER BY total_titles DESC;

Insight: TV-MA and TV-14 are the most common ratings, indicating strong focus on adult and teen audiences.

5️⃣ Most Popular Genres
SELECT listed_in, COUNT(*) AS total
FROM netflix
GROUP BY listed_in
ORDER BY total DESC;
🔥 Advanced SQL Concepts Used
Aggregations
COUNT()
GROUP BY
ORDER BY
Subqueries
SELECT *
FROM netflix
WHERE release_year = (
    SELECT MAX(release_year)
    FROM netflix
);
Joins
SELECT a.title, b.country
FROM netflix a
JOIN countries b
ON a.country_id = b.id;
📈 Key Insights
Netflix hosts more Movies than TV Shows.
Content production grew rapidly after 2015.
The United States produces the highest number of titles.
TV-MA and TV-14 are the most common content ratings.
Netflix continues expanding international content production.
💼 Business Value

This analysis can help media companies:

Understand content production trends
Identify high-performing regions
Optimize content investment decisions
Improve audience targeting strategies
Support content acquisition planning
📋 Sample SQL Queries
Find Longest Movie
SELECT title, duration
FROM netflix
WHERE type = 'Movie'
ORDER BY duration DESC
LIMIT 1;
Find Movies Released in 2020
SELECT title
FROM netflix
WHERE release_year = 2020
AND type = 'Movie';
Content Added Each Year
SELECT EXTRACT(YEAR FROM date_added) AS year_added,
COUNT(*) AS total
FROM netflix
GROUP BY year_added
ORDER BY year_added;
Find Content from India
SELECT title, type
FROM netflix
WHERE country = 'India';
🎯 Interview Summary

Performed Exploratory Data Analysis on Netflix Movies and TV Shows data using PostgreSQL. Applied SQL concepts such as aggregations, joins, filtering, and subqueries to analyze content distribution, release trends, country-wise production, and audience ratings, generating insights for data-driven decision-making.

👨‍💻 Author

Kalyan
Aspiring Data Analyst | SQL | PostgreSQL | Data Analytics

🔗 GitHub: https://github.com/Kalyan-hub19

Repository Structure
Netflix-analysis/
│
├── Dataset/
│   └── netflix_titles.csv
│
├── SQL Queries/
│   └── netflix_analysis.sql
│
├── README.md
│
└── Project Report/
    └── Netflix_Project.pdf

This README is polished for recruiters and hiring managers and follows a standard GitHub project format.
