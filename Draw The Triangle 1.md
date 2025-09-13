Draw The Triangle 1:

P(R) represents a pattern drawn by Julia in R rows. The following pattern represents P(5):

* * * * * 

* * * * 

* * * 

* * 

*
Write a query to print the pattern P(20).

Code:
----
WITH RECURSIVE numbers AS (
    
    SELECT 20 AS n
    
    UNION ALL
    
    SELECT n - 1
    
    FROM numbers
    
    WHERE n > 1

)

SELECT REPEAT('* ', n) AS pattern

FROM numbers;
