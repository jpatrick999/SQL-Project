Question 1: What were the top3 best selling products overall

SQL Queries:
```SQL

SELECT
    v2productname AS best_selling_product,
    COUNT(*) AS product_count
FROM
    all_sessions
WHERE
    v2productname IS NOT NULL
GROUP BY
    v2productname
ORDER BY
    COUNT(*) DESC
LIMIT 3
```
Answer:

The Googles Mens Tshirt, Youtube Bottle Infuser and the Youtube Cap were te 3 most popular

![alt text](Images/my_questions1.PNG)

Question 2: Which citys and countries spent the most time on the site?

SQL Queries:   
```SQL

SELECT
    city,
    country,
    SUM(time_onsite) AS total_time_onsite
FROM
    all_sessions
WHERE
	time_onsite IS NOT NULL
    AND country != '(not set)'
    AND city != '(not set)'
    AND city != 'not available in demo dataset'
GROUP BY
    city,
    country
ORDER BY
    total_time_onsite DESC
```


Answer:



![alt text](Images/my_questions2.PNG)



Question 3: Which 5 Users spent the most on total revenue
```SQL

SQL Queries:
SELECT
    full_visitor_id,
    SUM(total_transactionrevenue) AS total_revenue
FROM
    all_sessions
WHERE
    full_visitor_id IS NOT NULL
	and total_transactionrevenue IS NOT NULL
GROUP BY
    full_visitor_id
ORDER BY
    total_revenue DESC
LIMIT 5
```

Answer:




![alt text](Images/my_questions3.PNG)

