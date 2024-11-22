# LeetCode 584: Find Customer Referee

## Problem Statement
You are given a table `customer` that holds customers' information along with their referees. Write a query to find the names of customers who were **not referred by the customer with `id = 2`**.

### Table: customer

| Column      | Type    |
|-------------|---------|
| `id`        | int     |
| `name`      | varchar |
| `referee_id`| int     |

**Example Input:**

| id | name  | referee_id |
|----|-------|------------|
| 1  | Will  | NULL       |
| 2  | Jane  | NULL       |
| 3  | Alex  | 2          |
| 4  | Bill  | NULL       |
| 5  | Zack  | 1          |
| 6  | Mark  | 2          |

**Example Output:**

| name  |
|-------|
| Will  |
| Jane  |
| Bill  |
| Zack  |

## Explanation
- Customers Alex and Mark were referred by the customer with `id = 2`, so they are excluded from the result.
- The query should include customers who have `NULL` as their `referee_id` or those who were referred by someone other than `id = 2`.

---

## Solution

### SQL Query
```sql
SELECT name
FROM customer
WHERE referee_id <> 2 OR referee_id IS NULL;
