Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
```sql
SELECT city, SUM(totaltransactionrevenue) AS revenue_by_city 
FROM all_sessions
GROUP BY city
ORDER BY revenue_by_city DESC
```

```sql
SELECT country, SUM(totaltransactionrevenue) AS revenue_by_country 
FROM all_sessions
GROUP BY country
ORDER BY revenue_by_country DESC
```

Answer:
City San Francisco and country United States.


**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
```sql
SELECT AVG(avgquant_by_city)
FROM (
SELECT city, AVG(productquantity) AS avgquant_by_city 
FROM all_sessions
GROUP BY city
ORDER BY avgquant_by_city DESC
	) AS virtual_table

```



Answer:
2.23




**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:

```sql
SELECT v2productcategory,COUNT(v2productcategory)
FROM all_sessions
GROUP BY v2productcategory
ORDER BY COUNT(v2productcategory) DESC
```

```sql
SELECT city, COUNT(DISTINCT(v2productcategory))
FROM all_sessions
GROUP BY city
ORDER BY COUNT(DISTINCT(v2productcategory)) DESC
```

```sql
SELECT country, COUNT(DISTINCT(v2productcategory))
FROM all_sessions
GROUP BY country
ORDER BY COUNT(DISTINCT(v2productcategory)) DESC
```

Answer:
The most ordered product category is "Home/Shop by Brand/YouTube/". 
City Mountain View orders the highest variety of product types among all cities.
Country United States oders the highest variety of product types among all countries. 




**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:
```sql
SELECT v2productname, COUNT(*)
FROM all_sessions
WHERE city='Toronto' 
--Top selling product for each city can be found by changing the city name 
GROUP BY v2productname 
ORDER BY COUNT(*) DESC
```

```sql
SELECT v2productname, COUNT(*)
FROM all_sessions
WHERE country='Canada' 
--Top selling product for each country can be found by changing the country name 
GROUP BY v2productname 
ORDER BY COUNT(*) DESC
```


Answer:
To find the top selling product for each city/country, the city/country name in in line 3 of the codes can be changed to the desired city/country name. For example, the above example code shows the top selling product for Toronto is YouTube Trucker Hat, and the top selling product for Canada is 22oz YouTube Bottle Infuser. 




**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:
Use the following code to find the total revenue for all countries.
```sql
SELECT SUM(revcountry)
FROM(
SELECT country, SUM(totaltransactionrevenue) AS revcountry
FROM all_sessions
Group BY country
ORDER BY SUM(totaltransactionrevenue) DESC
) AS virtual_table
```
The revenue for each country can be found:
```sql
SELECT country, SUM(totaltransactionrevenue) AS revcountry
FROM all_sessions
Group BY country
ORDER BY SUM(totaltransactionrevenue) DESC
```

Use the following code to find the total revenue for all cities.
```sql
SELECT SUM(revcity)
FROM(
SELECT city, SUM(totaltransactionrevenue) AS revcity
FROM all_sessions
Group BY city
ORDER BY SUM(totaltransactionrevenue) DESC
) AS virtual_table
```
The revenue for each city can be found:
```sql
SELECT city, SUM(totaltransactionrevenue) AS revcity
FROM all_sessions
Group BY city
ORDER BY SUM(totaltransactionrevenue) DESC
```



Answer:
By comparing the total revenue and individual revenue, the impact can be summarized. 
United States has the highest revenue and Switzerland has the lowest revenue. 
San Francisco has the highest revenue and Zurich has the lowest revenue. 





