#

## LEFT JOIN

- All container return from `A` and mathcing values that common on `B`
- A Left join B = All A + Common from `B`

```sql
SELECT
    job_postings.job_title_short as title,
    job_postings.salary_year_avg as salary,
    job_postings.job_country as country
FROM
    job_postings_fact as job_postings
LEFT JOIN
    company_dim as company 
 ON 
    job_postings.company_id = company.company_id
```
<!-- ![alt text](left-join.png) -->

## RIGHT JOIN

- the opposite concept of the `LEFFT JOIN`
- if the right table(`B`) has less column then left one(`A`) it takes to much time for return values

<!-- ![alt text](right-join.png) -->

## INNER JOIN

```sql
    SELECT
        job_postings.job_title_short as title,
        job_postings.job_id,
        skill.skill_id
    FROM
        job_postings_fact as job_postings
    INNER JOIN
        skills_job_dim as skill 
    ON 
        ob_postings.job_id = skill.job_id
```
<!-- ![alt text](inner-join.png) -->


## MULTIPLE INNER JOIN

```sql
    SELECT
        job_postings.job_title_short as title,
        job_postings.job_id,
        skill.skill_id,
        skilld.skill_id
    FROM
        job_postings_fact as job_postings
    INNER JOIN
        skills_job_dim as skill ON  job_postings.job_id = skill.job_id
    INNER JOIN
        skills_dim as skilld ON  skilld.skill_id = skill.skill_id
```

![alt text](multiple-inner-join.png)

<!-- ---1:26:38--- -->