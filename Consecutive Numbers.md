180. Consecutive Numbers:
-------------------------

Find all numbers that appear at least three times consecutively.

Code:
----
select distinct s.num as ConsecutiveNums

from logs as s

join logs as b on s.id+1=b.id

join logs as c on b.id+1=c.id

where s.num=b.num and b.num=c.num

group by s.num

Logs table:
-----------
+----+-----+

| id | num |

+----+-----+

| 1  | 1   |

| 2  | 1   |

| 3  | 1   |

| 4  | 2   |

| 5  | 1   |

| 6  | 2   |

| 7  | 2   |

+----+-----+


Output: 
-------
+-----------------+

| ConsecutiveNums |

+-----------------+

| 1               |

+-----------------+


