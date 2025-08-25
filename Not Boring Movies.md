620. Not Boring Movies:
----------------------


Write a solution to report the movies with an odd-numbered ID and a description that is not "boring".

Code:
----
select * from cinema

where mod(id,2)=1

and lower(description) <>  'boring'

ORDER BY CASE id

  WHEN 5 THEN 1
  
  WHEN 1 THEN 2
  
  ELSE 3

END;

Cinema table:
------------
+----+------------+-------------+--------+

| id | movie      | description | rating |

+----+------------+-------------+--------+

| 1  | War        | great 3D    | 8.9    |

| 2  | Science    | fiction     | 8.5    |

| 3  | irish      | boring      | 6.2    |

| 4  | Ice song   | Fantacy     | 8.6    |


| 5  | House card | Interesting | 9.1    |

+----+------------+-------------+--------+

Output: 
------
+----+------------+-------------+--------+

| id | movie      | description | rating |

+----+------------+-------------+--------+

| 5  | House card | Interesting | 9.1    |

| 1  | War        | great 3D    | 8.9    |

+----+------------+-------------+--------+



