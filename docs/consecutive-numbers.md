---
id: consecutive-numbers
title: Consecutive Numbers
sidebar_label: Consecutive Numbers
---
## Description
<div class="description">
<p>Write a SQL query to find all numbers that appear at least three times consecutively.</p>

<pre>
+----+-----+
| Id | Num |
+----+-----+
| 1  |  1  |
| 2  |  1  |
| 3  |  1  |
| 4  |  2  |
| 5  |  1  |
| 6  |  2  |
| 7  |  2  |
+----+-----+
</pre>

<p>For example, given the above <code>Logs</code> table, <code>1</code> is the only number that appears consecutively for at least three times.</p>

<pre>
+-----------------+
| ConsecutiveNums |
+-----------------+
| 1               |
+-----------------+
</pre>

</div>

## Solution(mysql)
```mysql
# Write your MySQL query statement below
SELECT DISTINCT
    l1.Num AS ConsecutiveNums
FROM
    Logs l1,
    Logs l2,
    Logs l3
WHERE
    l1.Id = l2.Id - 1
    AND l2.Id = l3.Id - 1
    AND l1.Num = l2.Num
    AND l2.Num = l3.Num
;
```