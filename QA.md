What are your risk areas? Identify and describe them.

1.
Assume that the visitid column is unique becasue a new visit id is generated for each individua visit. The uniqeness of Column "visitid" under Table "all_sessions" can be checked. 

2.
Assume the sku for each product is unique. The uniqueness of the Column "sku: under Table "products" can eb checked. 

3. 
The database has large amounts of NULL data entries. 
However, it is unsafe to remove all NULL rows or columns since we do not have enough domain knowledge. It shoudl be checked if any columns are all NULL. If so, the column can be dropped. 

QA Process:
Describe your QA process and include the SQL queries used to execute it.

1. 
```sql
SELECT visitid, COUNT(*)
FROM all_sessions
GROUP BY visitid
HAVING COUNT(*) > 1
```

It was found that 1018 visit id were duplicated twice. 
These duplicated rows should be removed from the table. 

2.
```sql
SELECT sku, COUNT(*)
FROM products
GROUP BY sku
HAVING COUNT(*) > 1
```
Nothing was returned, so the no sku was duplicated. 

3.
```sql
SELECT productRefundAmount
FROM all_sessions
WHERE productRefundAmount IS NOT NULL
```
It was found productRefundAmount, productQuantity, productRevenue, itemQuantity, itemRevenue, transactionRevenue, transactionId, eCommerceAction_option are all empty column which can be removed from the table. 

