* `SQL Injection` - A vulnerability that happens when user input is handled as part of SQL code, allowing the input to change the meaning of a database query.


* `UNION` - Combines the results of two SELECT queries into one result set. Both queries must return the same number of columns, and matching columns must have compatible data types.


* `CONCAT` - Joins multiple strings or values into one string. It can display values from different columns together, but it does not retrieve data by itself.


* `In-Band SQL Injection` - The application shows database results directly in the same response channel used for the request.


* `Blind SQL Injection` - The application does not show database results directly, so information must be inferred from observable behavior, such as response differences or response times.


* `Error-Based SQL Injection` - Uses detailed database error messages to infer information about the database or the query, such as an unknown column or an invalid reference.


* `Union-Based SQL Injection` - Uses UNION to combine the application's original query results with results from another query. This requires a matching number of columns and compatible data types; access also depends on database permissions and what the application displays.


* `Boolean-Based Blind SQL Injection` - Infers information by observing how the application responds when a condition is true or false.


* `Time-Based Blind SQL Injection` - Infers information by observing response-time differences, which can be caused by a conditional delay.
