#

`basic-02` welcome back

## Renaming with `AS` (Alias)

We can use the `AS` keyword to rename table columns. This can make our query results more readable. 

```sql
SELECT 
     job_title_short AS jts,
     company_id AS ci
FROM job_postings_fact
```
<!-- <details>
  <summary>Click to show output 🖐️ </summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/44855e7e-a601-4fb5-b242-e695c896f391" alt="Table" width="800" height="400">
![alt text](as_image.png)
</details> -->

In this example, `job_title_short` is renamed as `jts`, and `company_id` is renamed as `ci`.

We can also rename tables themselves:

```sql
SELECT 
     job_title_short AS jts,
     company_id AS ci
FROM 
    job_postings_fact AS jpt
```

Here, `job_postings_fact` is renamed as `jpt`.

### Renaming without `AS`

Although We can rename without `AS`, it's less readable:

```sql
SELECT
    name AS n,
    link AS l
FROM company_dim
```

## Arithmetic Operations (`+`, `-`, `*`, `%`)

We can perform arithmetic operations directly in SQL queries.

### Addition (`+`)

For example, if We want to apply a discount to the hourly rate:

```sql
SELECT 
    project_company,
    nerd_role,
    hours_rate AS original_rate,
    hours_rate - 10 AS price_drop
FROM invoices_fact
```
<!-- ![alt text](plus_salary.png) -->
### Multiplication (`*`)

To filter data based on the product of two columns:

```sql
SELECT 
    project_company,
    nerd_role,
    hours_spent,
    hours_rate AS original_rate,
    hours_rate - 10 AS price_drop
FROM invoices_fact
WHERE
    hours_spent * hours_rate < 1000
```
<!-- ![alt text](multiplication_image.png) -->
### Modulus (`%`)

We can use `%` to find remainder, like in this example to find extra hours:

```sql
SELECT 
    nerd_role,
    hours_spent,
    hours_spent % 8 AS extra_hours
FROM  invoices_fact
WHERE
    hours_spent > 8
```
<!-- ![alt text](extrahours.png) -->
## Aggregate Functions

Aggregate functions operate on sets of rows and return a single result.

### `SUM()`

To find the total of a column:

```sql
SELECT 
    SUM(hours_spent) AS total_hours_spent
FROM invoices_fact
```
<!-- ![alt text](image.png) -->
### `COUNT(*)`

To count all rows:

```sql
SELECT 
    COUNT(*) AS row_count
FROM invoices_fact
```

### `COUNT(DISTINCT column)`

To count unique values in a column:

```sql
SELECT 
    COUNT(DISTINCT project_company) AS unique_projects
FROM invoices_fact
```

### `AVG()`

To find the average value of a column:

```sql
SELECT 
    AVG(hours_spent) AS average_hours_spent
FROM invoices_fact
```

### Combining `AVG()`, `MIN()`, and `MAX()`

```sql
SELECT 
    AVG(hours_spent) AS avg_hours_spent,
    MIN(hours_spent) AS min_hours_spent,
    MAX(hours_spent) AS max_hours_spent
FROM invoices_fact
```
<!-- ![alt text](avg-min-max.png) -->
## `GROUP BY`

We can use `GROUP BY` to group rows with the same values into summary rows:

```sql
SELECT 
    project_company as pc,
    AVG(hours_spent) as avg_hs,
    min(hours_spent) as min_hs,
    max(hours_spent) as max_hs
FROM  invoices_fact
GROUP BY project_company
```
<!-- ![alt text](group-by-1.png) -->

<!-- The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country" -->
<!-- SELECT skills as sk, 
COUNT(type) as ty
FROM skills_dim
GROUP BY
	type -->
<!-- ![alt text](group-by-2.png) -->

## NULL - values 

- a field with no values
- used the command `where` or `having` for filter

```sql
    SELECT
        job_title_short as jts,
        salary_year_avg as sya
        
    FROM
        job_postings_fact
    WHERE 
        salary_year_avg is NULL
    ORDER BY
        salary_year_avg
```

<!-- ![alt text](null-values.png) -->