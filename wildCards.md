`%` is a wildcard symbal , it returns 0 or more characters
- ]db link - search on browser `https://lukeb.co/sql_jobs_db`

`%A` returns anything that and with Char `A`
```sql
SELECT 
    job_location
FROM
    job_postings_fact
WHERE
    job_location LIKE '%A'
```
<details>
  <summary>Click to show output 🖐️ </summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/f8e39865-6e8e-48a2-a799-c306ec2174b3" alt="Table" width="800" height="400">
</details>

`A%` returns anything that and with Char `A`
```sql
SELECT 
    job_location
FROM
    job_postings_fact
WHERE
    job_location LIKE '%A'
```
<details>
  <summary>Click to show output 🖐️ </summary>
<img src="https://github.com/sajjadrahman56/Data-Analytics/assets/67529599/44855e7e-a601-4fb5-b242-e695c896f391" alt="Table" width="800" height="400">
</details>
 
