Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
```sql
SELECT city, SUM(totaltransactionrevenue) AS revenue_by_city 
FROM all_sessions
GROUP BY city
ORDER BY revenue_by_city DESC
```

```
SELECT country, SUM(totaltransactionrevenue) AS revenue_by_country 
FROM all_sessions
GROUP BY country
ORDER BY revenue_by_country DESC
```

Answer:
City San Francisco and country United States.


**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
```
SELECT city, AVG(productquantity) AS avgquant_by_city 
FROM all_sessions
GROUP BY city
ORDER BY avgquant_by_city DESC
```

```
SELECT country, AVG(productquantity) AS avgquant_by_country 
FROM all_sessions
GROUP BY country
ORDER BY avgquant_by_country DESC
```


Answer:
City Madrid and Country Spain.




**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:



Answer:





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:



Answer:





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:



Answer:







