584. Find Customer Referee:
--------------------------

Find the names of the customer that are either:

-referred by any customer with id != 2.

-not referred by any customer.

Return the result table in any order.

Code:
----

SELECT name

FROM Customer

WHERE referee_id IS NULL or referee_id != 2;
