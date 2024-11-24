# LeetCode Problem 1757: Recyclable and Low Fat Products

## Problem Description

Given a table `Products`, write a SQL query to find all products that are recyclable and low fat.  

The `Products` table is defined as:

| Column Name     | Type    |
|------------------|---------|
| product_id       | int     |
| low_fats         | enum    |
| recyclable       | enum    |

- `product_id` is the primary key for this table.
- `low_fats` is an ENUM ('Y', 'N') where 'Y' means low fat and 'N' means not low fat.
- `recyclable` is an ENUM ('Y', 'N') where 'Y' means recyclable and 'N' means not recyclable.

Return the `product_id` of products that are both low fat (`low_fats = 'Y'`) and recyclable (`recyclable = 'Y'`).

### Refer the Question on [Leetcode.com](https://leetcode.com/problems/recyclable-and-low-fat-products/description/?envType=study-plan-v2&envId=top-sql-50) 

---

## Solution

### SQL Query

```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y';
