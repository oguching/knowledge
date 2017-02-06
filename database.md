transactions

joins  
Given two tables T1 and T2  
**inner join**   
Will produce a set of rows that only match both T1 and T2. This represents the intersection of T1 and T2, think of it as a logical AND.

**outer join**  
The outer join allows us to retrieve all rows from one table, plus any rows that match from the other tables. 
If there's no matching data, NULL values are returned for those columns.

**left outer join**  
Will produce the complete set of records from T1 with the matching records in T2. 
If there is no match, NULL values are returned for those columns.

The left table is the one encountered first in the SQL statement.

[Marco Arment](https://marco.org) really does not like joins and advocates you avoid it. In his Blogpost he quotes CodingHorror's tweet saying Joins are expensive. He claims Tumblr and Instapaper never used joins.
> Don't underestimate the benefits of some denormalisation and avoiding joins.   


He uses a two-query substitution

```php
  $user_ids = $following->query_return_column_array(
    'SELECT user_id FROM ?table WHERE following_id = ?i', $this->id
  );
  $followed_users = $user->find(
    'SELECT * from ?table WHERE id IN ?ai', $user_ids
  );
```


resources  
* [getting joins](http://www.khankennels.com/blog/index.php/archives/2007/04/20/getting-joins/)
* [Visual Explanation of SQL Joins](https://blog.codinghorror.com/a-visual-explanation-of-sql-joins/) CodingHorror
* [Joins are Expensive](https://marco.org/2009/01/30/on-database-joins)
