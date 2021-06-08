# SELECT statement

1.) SELECT --> What columns do you want to select?
2.) If you want all the columns \*
3.) If you want particular columns list them out
4.) FROM --> which table?
5.) WHERE --> (particular clause to include)
6.) ORDER BY --> (name of column or other indicator)

```
USE sql_store;
SELECT *
FROM customers
ORDER BY first_name
```

```
SELECT
	first_name,
    last_name,
    points,
    points * 10 + 100 AS "discount factor"
FROM customers
```

## Remove Duplicates with DISTINCT statement

```
SELECT DISTINCT state
FROM customers
```
