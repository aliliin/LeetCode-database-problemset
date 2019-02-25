
<h1>第N高的薪水</h1>
<hr>
编写一个 SQL 查询，获取 Employee 表中第 n 高的薪水（Salary）。

| Id | Salary |
|----|--------|
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |

例如上述 Employee 表，n = 2 时，应返回第二高的薪水 200。如果不存在第 n 高的薪水，那么查询应返回 null。

| getNthHighestSalary(2) |
|------------------------|
| 200                    |


```
select distinct Salary from Employee as e where N = (select count(distinct (Salary)) from Employee where Salary >= e.Salary )
```