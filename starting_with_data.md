Question 1: Which product was bought when the customer had the longest time on site?

SQL Queries:
```sql
SELECT v2productname, timeonsite
FROM all_sessions
WHERE timeonsite IS NOT NULL
ORDER BY timeonsite DESC
```

Answer: 
Based on teh data available, the product is Android Men's Hoodie.


Question 2: What is the price of the product bought when the customer had the longest time on site? How much time?

SQL Queries: 
```sql
SELECT v2productname, timeonsite, productprice
FROM all_sessions
WHERE timeonsite IS NOT NULL
ORDER BY timeonsite DESC
```
Answer: The product price is 55.99 USD. Time one site is 4661.



Question 3: What is the time stayed on site for the highest product price? What is the prudct price?

SQL Queries:
```sql
SELECT v2productname, timeonsite, productprice
FROM all_sessions
WHERE timeonsite IS NOT NULL
ORDER BY productprice DESC
```

Answer: The price is 298 USD and time on site is 943.




