1581. Customer Who Visited but Did Not Make Any Transactions:
------------------------------------------------------------
Code:
-----
select v.customer_id, COUNT(*) AS count_no_trans

from visits v

left join transactions t

on v.visit_id = t.visit_id

where t.visit_id is null

group by v.customer_id;


Visits:
-------

+----------+-------------+

| visit_id | customer_id |

+----------+-------------+

| 1        | 23          |

| 2        | 9           |

| 4        | 30          |

| 5        | 54          |

| 6        | 96          |

| 7        | 54          |

| 8        | 54          |

+----------+-------------+

Transactions:
------------

+----------------+----------+--------+

| transaction_id | visit_id | amount |

+----------------+----------+--------+

| 2              | 5        | 310    |


| 3              | 5        | 300    |

| 9              | 5        | 200    |

| 12             | 1        | 910    |

| 13             | 2        | 970    |
+----------------+----------+--------+


Output: 
-------

+-------------+----------------+

| customer_id | count_no_trans |

+-------------+----------------+

| 54          | 2              |

| 30          | 1              |

| 96          | 1              |

+-------------+----------------+





