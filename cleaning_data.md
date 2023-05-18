What issues will you address by cleaning the data?

1. Irrelevant Data: 
  Since the questions and goals are open-ended, all data is considered relavant at this stage. 

2. Duplicate data:
  All tables are checked for duplicates. Example code:
  ```
  SELECT DISTINCT(productsku) FROM sales_report
  ```
  It was found no rows were duplicated. 


3. Incorrect data: Unit cost 
  The unit_price column in anlytics table needs to be divided by 1,000,000.

  ```
  UPDATE analytics
  SET unit_price = unit_price / 1000000
  ```

4. Replacing missing data:
  In tabel sales_report, column timeonsite, there are null values. 
  These null values are not assumed to be zeros because they appear in bulk, whcih can be casued by loss fo data.
 

5. Incorrect data in country columnz:
  In table all_sessions, column country, "Taiwan" and "Hong Kong" are falsely listed as countries intead of provinces of China. 
  (Since only 12 of 193 UN nations recognize Taiwan as a sovereign nation, it is safe to assume it is not a country. )
  The following code is used to correct this data:
  ```
  UPDATE all_sessions
  SET country=REPLACE(country,'Taiwan','China')
  ```
  ```
  UPDATE all_sessions
  SET country=REPLACE(country,'Hong Kong','China')
  ```
