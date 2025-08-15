1683. Invalid Tweets:
--------------------

Write a solution to find the IDs of the invalid tweets. The tweet is invalid if the number of characters used in the content of the tweet is strictly greater than 15.

Code:
----
Select tweet_id

from tweets

where length(content)>15;

Tweets table:
------------
+----------+-----------------------------------+

| tweet_id | content                           |

+----------+-----------------------------------+

| 1        | Let us Code                       |

| 2        | More than fifteen chars are here! |

+----------+-----------------------------------+

Output: 
-------
+----------+

| tweet_id |

+----------+
| 2        |
+----------+
