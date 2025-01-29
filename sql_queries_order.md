# How SQL Queries Are Executed Behind the Scenes

> **Note**: The flow described below isn't how SQL engines _always_ execute queries internally, but rather how SQL execution is logically ordered.

### **1. FROM and JOINs**

The engine starts by selecting the tables mentioned in the `FROM` clause. If there are any `JOIN`s, it combines the tables according to the specified conditions

### **2. WHERE**

After the tables are joined, It will filter rows based on the conditions in the `WHERE` clause. 

### **3. GROUP BY**

Next, grouping rows that have the same values in the specified columns (e.g., grouping by customer or product). This is useful when you want to apply aggregate functions like `COUNT`, `SUM`, or `AVG`.

### **4. HAVING**

Then `HAVING` clause.
It filters the results of the groups, just like `WHERE` filters individual rows before grouping.

### **5. SELECT**

At this point, It selects the columns. If any aggregate calculations are involved, they are performed here.

### **6. DISTINCT**

If specified, removing of duplicate rows in the result will be performed.

### **7. ORDER BY**

Then sorting will take place on the `ORDER BY` clause, either in ascending or descending order.

### **8. LIMIT / OFFSET**

Finally,  `LIMIT` will be applied to restrict the number of rows returned and `OFFSET` to skip a specified number of rows.

### Example:

```sql
SELECT
    t1.id,
    t1.name,
    COUNT(t2.order_id) AS order_count
FROM
    users t1
LEFT JOIN
    orders t2 ON t1.id = t2.user_id
WHERE
    t1.status = 'half-blood'
GROUP BY
    t1.id
HAVING
    COUNT(t2.order_id) > 5
ORDER BY
    order_count DESC
LIMIT 10 OFFSET 20;
```

Order in which SQL processes it:

1.  **FROM** and **JOINs**: Combines `users` and `orders`.
2.  **WHERE**: Filters users who are `active`.
3.  **GROUP BY**: Groups the data by `user id`.
4.  **HAVING**: Filters groups where the user has more than 5 orders.
5.  **SELECT**: Selects the columns to display.
6.  **ORDER BY**: Sorts the result by `order_count`.
7.  **LIMIT / OFFSET**: Returns the 10th to 20th row.


**any feedback about the article will make me more happy**

---
If the article helps you, leave a like, follow, or anything 🙂.

You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**