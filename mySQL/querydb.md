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
FROM products
WHERE price BETWEEN 3000 AND 4000

```

# LIKE Operator

- Percent Sign
  %g% --> g is anywhere in the word
  g% --> g is at the beginning of the word
  %mac --> 'mac' is at the end of the word

- Underscore Sign
  '_g' --> second character must be g
  '_ \_ \_ \_ _ g' --> 6th character must be a g
  'b _ \_ \_ y --> must start with b and end with y

```

SELECT *
FROM customers
WHERE last_name LIKE '%g' OR '%mac%

SELECT *
FROM customers
WHERE last_name NOT LIKE '%g' OR '%mac%

```

# REGEXP Operator

- Search for more complex patterns
- ^ beginning of string (carrot)
- $ end of string (dollar sign)
- | pipe (represent logical or aka multiple search patterns)
- [gim]e
  - ge
  - ie
  - me
- [a-h]e

```

SELECT *
FROM customers
<!-- WHERE last_name LIKE '%field%' -->
WHERE last_name REGEXP 'field'



SELECT *
FROM customers
<!-- find lastnames with the word that starts with field or has mac in the name -->
WHERE last_name REGEXP '^field|mac'


SELECT *
FROM customers
<!-- find lastnames ge, ie, or me in their last name -->
WHERE last_name REGEXP '[gim]e'


SELECT *
FROM customers
WHERE first_name REGEXP 'ELKA|AMBUR'
last_name REGEXP 'EY$|ON$'
<!-- last name should start with 'my' or contain 'se' -->
last_name '^MY|se'
last_name 'b[ru]'


```
