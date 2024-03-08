What issues will you address by cleaning the data?

The unit cost in the data needs to be divided by 1,000,000. 
some of the issues i will address are the missing data, for example "not available in demo dataset" and also not set for countries or citys.



Queries:
Below, provide the SQL queries you used to clean your data.

UPDATE analytics
SET unit_price = unit_price / 1000000;                                                                              

---made a view for the cleaned data  
```SQL

SELECT
    CASE 
        WHEN city IN ('(not set)', 'not available in demo dataset') THEN NULL
        ELSE city
    END AS city_cleaned,
    CASE 
        WHEN country IN ('(not set)', 'not available in demo dataset') THEN NULL
        ELSE country
    END AS country_cleaned
FROM 
    all_sessions;
    ```
