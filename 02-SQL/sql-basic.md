
_Query practice site link: `lukeb.co/sql_jobs_dib`_


## Comments

Comments in SQL are used to provide additional information or explanations within the code. They are not executed and are typically used for documentation or clarification purposes. In the provided example:

```sql
SELECT
  /*
    job_via,
    job_title,
 */
 	company_id
FROM
	job_postings_fact
```

The commented-out lines using `/* */` are not considered part of the executed query. They serve to explain that `job_via` and `job_title` columns are being ignored in this query.

## ORDER BY

The `ORDER BY` clause in SQL is used to sort the result set in either ascending or descending order. It helps to organize the data in a specified manner. For example:

```sql
SELECT
	  job_via,
          job_title,
 	  company_id
FROM
	  job_postings_fact
ORDER BY
 	  job_via
```

This query will sort the result set by the `job_via` column in ascending order.

<details>
  <summary>Click to expand the table</summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/65f0fe1c-7cc6-4409-97f5-ea6bb89a6d65" alt="Table" width="800" height="400">
</details>

## <> (Not Equal To)

In SQL, the `<>` operator is used to check for inequality. It means "not equal to". 

For example:

```sql
SELECT *
FROM job_postings_fact
WHERE job_via <> 'Contractor and TEMPORARY';
```

This query selects all rows from the table `job_postings_fact` where the value in the column `job_via` is not equal to `'Contractor and TEMPORARY'`.

<details>
  <summary>Click to expand the table</summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/16a01439-fb4f-42d5-ac71-b00334bb5fb3" alt="Table" width="800" height="400">
</details>

## = (Equal)

In SQL, the `=` operator is used to check for equality. 

For example:

```sql
SELECT *
FROM job_postings_fact
WHERE job_via = 'Contractor and TEMPORARY';
```

This query selects all rows from the table `job_postings_fact` where the value in the column `job_via` is equal to `'Contractor and TEMPORARY'`.

<details>
  <summary>Click to expand the table</summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/0a180dc8-c3a8-46b5-bb14-7695451f75b6" alt="Table" width="800" height="400">
</details>

As like we all can assume the result of `>` `<` , `<=` , `>=`

## AND

The `AND` operator in SQL is used to combine multiple conditions in a `WHERE` clause. It ensures that all conditions must be true for a row to be included in the result set.

```sql
SELECT *
FROM
	job_postings_fact
 where 
 	job_title_short = 'Cloud Engineer' 
 AND
 	job_location = 'Anywhere'
```

<details>
  <summary>Click to expand the table</summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/bfb511f6-8b6c-4732-8660-062e9dd57aa8" alt="Table" width="800" height="400">
</details>


## Between 

`BETWEEN` is a SQL operator used to filter data within a specified range, inclusive of both the start and end values.
```sql
SELECT 
	job_via,
    job_title,
    salary_year_avg
FROM
	job_postings_fact
WHERE
	salary_year_avg BETWEEN 100000 AND 200000
ORDER BY
	salary_year_avg
```
<details>
  <summary>Click to expand the table</summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/59a4136b-68a7-4534-9e8e-8e20d5e258e6" alt="Table" width="800" height="400">
</details>

 ## IN 

 `IN` specifies multiple values in a where a clause, on the other hand, it's similar to `OR`
 ```sql
 SELECT 
	job_via,
    job_title,
    salary_year_avg
FROM
	job_postings_fact
WHERE
 	job_title_short IN ('Data Analyst','Data Engineer')
```
or we can write like 

 ```sql
 WHERE
 	job_title_short  =  'Data Analyst' OR
    job_title_short  = 'Data Engineer'
```
- it returns the same result for us but the `in` increases the robustness 

<details>
  <summary>Click to expand the table</summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/af00a175-6f86-42da-b86e-2bffae61cc38" alt="Table" width="800" height="400">
</details>



