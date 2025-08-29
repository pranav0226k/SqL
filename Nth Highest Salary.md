177. Nth Highest Salary:
-----------------------

Write a solution to find the nth highest distinct salary from the Employee table. If there are less than n distinct salaries, return null.

Code:
----

CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT

BEGIN

  RETURN (
  
      select distinct salary as 'getNthHighestSalary(2)'
      
       from  (
       
          select salary,
          
                dense_rank() over(order by salary desc) as rnk
          
          from employee
      
      )  sal_rnk
      
      where rnk = n 
  );

Employee table:
--------------
+----+--------+

| id | salary |

+----+--------+

| 1  | 100    |

| 2  | 200    |

| 3  | 300    |

+----+--------+

n = 2

Output: 
-------
+------------------------+

| getNthHighestSalary(2) |

+------------------------+

| 200                    |

+------------------------+


E ND
