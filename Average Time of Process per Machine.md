1661. Average Time of Process per Machine:
------------------------------------------

There is a factory website that has several machines each running the same number of processes. Write a solution to find the average time each machine takes to complete a process.

The time to complete a process is the 'end' timestamp minus the 'start' timestamp. The average time is calculated by the total time to complete every process on the machine divided by the number of processes that were run.

The resulting table should have the machine_id along with the average time as processing_time, which should be rounded to 3 decimal places.

Return the result table in any order.




Code:
-----
SELECT machine_id, ROUND(AVG(end_time - start_time), 3) AS processing_time

FROM (

    SELECT machine_id, process_id,
    
        MAX(CASE WHEN activity_type = 'start' THEN timestamp END) AS start_time,
        
        MAX(CASE WHEN activity_type = 'end' THEN timestamp END) AS end_time
    
    FROM Activity

    GROUP BY machine_id, process_id ) AS process_times

GROUP BY machine_id;

Activity table:
--------------
| machine_id | process_id | activity_type | timestamp |

| ---------- | ---------- | ------------- | --------- |

| 0          | 0          | start         | 0.712     |

| 0          | 0          | end           | 1.52      |

| 0          | 1          | start         | 3.14      |

| 0          | 1          | end           | 4.12      |

| 1          | 0          | start         | 0.55      |

| 1          | 0          | end           | 1.55      |

| 1          | 1          | start         | 0.43      |

| 1          | 1          | end           | 1.42      |

| 2          | 0          | start         | 4.1       |

| 2          | 0          | end           | 4.512     |

| 2          | 1          | start         | 2.5       |

| 2          | 1          | end           | 5         |

Output:
------
| machine_id | processing_time |

| ---------- | --------------- |

| 0          | 0.894           |

| 1          | 0.995           |

| 2          | 1.456           |

