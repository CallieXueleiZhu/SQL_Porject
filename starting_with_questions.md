Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
```
SELECT city, SUM(totaltransactionrevenue) AS revenue_by_city 
FROM all_sessions
GROUP BY city
ORDER BY revenue_by_city
```

```
SELECT country, SUM(totaltransactionrevenue) AS revenue_by_country 
FROM all_sessions
GROUP BY country
ORDER BY revenue_by_country
```

Answer:
City Zurich has the highest total transaction revenue of 1.699e+07. 
Country Switzerland has the highest total transaction revenue of 1.699e+07. 


**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:



Answer:





**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:



Answer:





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:



Answer:





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:



Answer:







