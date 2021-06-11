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
SELECT first_name, last_name, points, (points * 10 + 100) AS "discount factor"
FROM customers
```

# DISTINCT statement

Remove duplicates by using DISTINCT

```
SELECT DISTINCT state
FROM customers
```

# WHERE statement

- Dates are string
- AND operators are evaluated first
- OR operator is evaluated after AND
- NOT operator

```
<>
!=
=
<
>
>=
<=

WHERE state = "VA"
WHERE birth_date > '1990-01-01' OR points > 100
WHERE birth_date > '1990-01-01' OR (points > 100 AND state = 'VA')


SELECT *
FROM order_items
WHERE order_id = 6 AND unit_price * quanity > 30

// IN operator

WHERE state IN ('VA', 'FL', 'GA')
WHERE state  NOT IN ('VA', 'FL', 'GA')

SELECT *
FROM products
WHERE quanity_in_stock IN (49,38,72)


```

# BETWEEN Operator

```
SELECT *
FROM proucts
WHERE price BETWEEN 3000 AND 4000

```
