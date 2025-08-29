176. Second Highest Salary:
--------------------------

Write a solution to find the second highest distinct salary from the Employee table. If there is no second highest salary, return null (return None in Pandas).

Code:
----
select

    (select distinct Salary
    
        from Employee
        
        order by Salary desc
        
        limit 1 offset 1) 

as SecondHighestSalary;


Employee table:
---------------

+----+--------+

| id | salary |

+----+--------+

| 1  | 100    |

| 2  | 200    |

| 3  | 300    |

+----+--------+

Output: 
------
+---------------------+

| SecondHighestSalary |

+---------------------+

| 200                 |

+---------------------+



