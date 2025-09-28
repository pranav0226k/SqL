183. Customers Who Never Order:
------------------------------

Write a solution to find all customers who never order anything.

Code:
----
select name as Customers

from customers

where id not in (

    select customerId from orders

)

Input: 
-------
Customers table:
----------------
+----+-------+

| id | name  |

+----+-------+

| 1  | Joe   |

| 2  | Henry |

| 3  | Sam   |

| 4  | Max   |

+----+-------+


Orders table:
-------------
+----+------------+

| id | customerId |

+----+------------+

| 1  | 3          |

| 2  | 1          |

+----+------------+

Output: 
-----------

| Customers |

+-----------+

| Henry     |

| Max       |

+-----------+
