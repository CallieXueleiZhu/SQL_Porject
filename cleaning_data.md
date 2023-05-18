What issues will you address by cleaning the data?
1. Irrelevant Data: 
Since the questions and goals are open-ended, all data is considered relavant at this stage. 
3. Duplicate data:
All tables are checked for duplicates. Example code:

```
SELECT DISTINCT(productsku) FROM sales_report
```

It was found no rows were duplicated. 

4. Date Data's Format and constainsts:
5. Incorrect data: country and city 
6. Incorrect data: Unit cost 
The unit_price column in anlytics table needs to be divided by 1,000,000.

```

```



Queries:
Below, provide the SQL queries you used to clean your data.
