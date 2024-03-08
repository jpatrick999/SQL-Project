What are your risk areas? Identify and describe them.

Some risk areas could be columns with no real information about them.
Another risk could be the query themselves in order to find the answers. or how data was cleaned

QA Process:
Describe your QA process and include the SQL queries used to execute it.

for the first question i decided to show the top 5 city's with the highest total revenue. In order to check my answer i decided to make a query, where it could check if there were any answers above my number 5 country.If i got back the same countries as my orignal query then the query should be correct. 
```SQL

SELECT 
    city, 
    country, 
    SUM(total_transactionrevenue) AS total_revenue
FROM 
    all_sessions
GROUP BY 
    city, 
    country
HAVING 
    SUM(total_transactionrevenue) > 602000000;

```
