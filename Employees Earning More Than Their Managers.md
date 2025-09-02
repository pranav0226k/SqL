181. Employees Earning More Than Their Managers:
------------------------------------------
Write a solution to find the employees who earn more than their managers.

Code:
----
select e.name

from employee e

inner join employee em

on e.managerId = em.id

where e.salary > em.salary;

Employee table:
---------------
+----+-------+--------+-----------+

| id | name  | salary | managerId |

+----+-------+--------+-----------+

| 1  | Joe   | 70000  | 3         |

| 2  | Henry | 80000  | 4         |

| 3  | Sam   | 60000  | Null      |

| 4  | Max   | 90000  | Null      |

+----+-------+--------+-----------+

Output: 
------
+----------+

| Employee |

+----------+

| Joe      |

+----------+




