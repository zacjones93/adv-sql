# Common Table Expressions

## 01.
The query below finds the averge of all purchases relative to the user.

Break the subquery out into a CTE so that you can re-use the logic elsewhere.

```sql
select user_handle, sku, 
(select avg(quantity) from Purchases 
  where user_handle = p.user_handle and sku = p.sku
) from Purchases p 
group by user_handle, sku;
```

## 02. 

With that CTE defined, use the CTE to find the average quantity of the user with a `user_handle` of `59`.