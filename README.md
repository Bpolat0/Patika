# Patika-SQL-Odevler

## Ödev 1

``` sql
SELECT title, description
FROM film;

SELECT *
FROM film
WHERE length > 60 AND length < 75;

SELECT *
FROM film
WHERE rental_rate = 0.99 AND (replacement_cost = 12.99 OR replacement_cost = 28.99);

SELECT last_name
FROM customer
WHERE first_name = 'Mary';

SELECT *
FROM film
WHERE NOT (length > 50) AND NOT (rental_rate = 2.99 OR rental_rate = 4.99);
```

## Ödev 2

``` sql
SELECT *
FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.99;

SELECT first_name, last_name
FROM actor
WHERE first_name IN ('Penelope', 'Nick', 'Ed');

SELECT *
FROM film
WHERE rental_rate IN (0.99, 2.99, 4.99)
  AND replacement_cost IN (12.99, 15.99, 28.99);
```

## Ödev 3

``` sql
SELECT *
FROM country
WHERE country LIKE 'A%a';

SELECT *
FROM country
WHERE LENGTH(country) >= 6 AND country LIKE '%n';

SELECT *
FROM film
WHERE title ILIKE '%T%T%T%T%';

SELECT *
FROM film
WHERE title LIKE 'C%' AND LENGTH(title) > 90 AND rental_rate = 2.99;
```

## Ödev 4

``` sql
SELECT DISTINCT replacement_cost
FROM film;

SELECT COUNT(DISTINCT replacement_cost)
FROM film;

SELECT COUNT(*)
FROM film
WHERE title LIKE 'T%' AND rating = 'G';

SELECT COUNT(*)
FROM country
WHERE LENGTH(country) = 5;

SELECT COUNT(*)
FROM city
WHERE city ILIKE '%r';
```

## Ödev 5

``` sql
SELECT *
FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;

SELECT *
FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5;

SELECT *
FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4;
```

## Ödev 6

``` sql
SELECT AVG(rental_rate) AS average_rental_rate
FROM film;

SELECT COUNT(*)
FROM film
WHERE title LIKE 'C%';

SELECT MAX(length) AS max_length
FROM film
WHERE rental_rate = 0.99;

SELECT COUNT(DISTINCT replacement_cost) AS distinct_replacement_costs
FROM film
WHERE length > 150;
```
## Ödev 7

``` sql
SELECT rating, COUNT(*) AS film_count
FROM film
GROUP BY rating;

SELECT replacement_cost, COUNT(*) AS film_count
FROM film
GROUP BY replacement_cost
HAVING COUNT(*) > 50
ORDER BY film_count DESC;

SELECT store_id, COUNT(*) AS customer_count
FROM customer
GROUP BY store_id;

SELECT country_id, COUNT(*) AS city_count
FROM city
GROUP BY country_id
ORDER BY city_count DESC
LIMIT 1;
```

## Ödev 8

``` sql
CREATE TABLE employee (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50),
    birthday DATE,
    email VARCHAR(100)
);

INSERT INTO employee (name, birthday, email) VALUES
('John Doe', '1990-05-15', 'john@example.com'),
('Jane Smith', '1988-09-21', 'jane@example.com'),
...
-- 50 adet benzeri kayıt

UPDATE employee SET name = 'New Name' WHERE id = 1;
UPDATE employee SET birthday = '1992-11-30' WHERE id = 2;
...
-- Diğer sütunlar için de benzer şekilde güncelleme

DELETE FROM employee WHERE id = 1;
DELETE FROM employee WHERE name = 'John Doe';
...
-- Diğer sütunlar için de benzer şekilde silme

```

## Ödev 9

``` sql
SELECT city.city, country.country
FROM city
INNER JOIN country ON city.country_id = country.country_id;

SELECT payment.payment_id, customer.first_name, customer.last_name
FROM customer
INNER JOIN payment ON customer.customer_id = payment.customer_id;

SELECT rental.rental_id, customer.first_name, customer.last_name
FROM customer
INNER JOIN rental ON customer.customer_id = rental.customer_id;

```

## Ödev 10

``` sql
SELECT city.city, country.country
FROM city
LEFT JOIN country ON city.country_id = country.country_id;

SELECT payment.payment_id, customer.first_name, customer.last_name
FROM customer
RIGHT JOIN payment ON customer.customer_id = payment.customer_id;

SELECT customer.first_name, customer.last_name, rental.rental_id
FROM customer
LEFT JOIN rental ON customer.customer_id = rental.customer_id

UNION ALL

SELECT customer.first_name, customer.last_name, rental.rental_id
FROM rental
LEFT JOIN customer ON rental.customer_id = customer.customer_id
WHERE customer.customer_id IS NULL;

```

## Ödev 11

``` sql

```

## Ödev 12

``` sql

```
