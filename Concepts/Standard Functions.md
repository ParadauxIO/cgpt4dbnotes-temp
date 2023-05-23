There are many SQL functions that a DBA (Database Administrator) may need to be familiar with. Let's look at a few of them, using the SQL standard and Oracle's SQL dialect as examples. It's worth noting that specific syntax can vary between different SQL implementations, so always check the relevant documentation.

TO_CHAR: In Oracle SQL, the TO_CHAR function converts a number or date to a string. The syntax for TO_CHAR in the context of a date is ```TO_CHAR(date, 'format')``` where 'format' could be something like 'YYYY-MM-DD'. For a number, it's ```TO_CHAR(number, 'format')```, where the format could be something like '999,999.99'.

TO_DATE: The TO_DATE function is used to convert a string to a date. The syntax is ```TO_DATE('string', 'format')```, where 'string' is the date in string format and 'format' is the format of that string, such as 'YYYY-MM-DD'.

SUBSTR: The SUBSTR function is used to extract a substring from a string. The syntax is ```SUBSTR(string, start_position, length)```. Start_position is the point in the string where you start extracting, and length is the number of characters to extract.

CONCAT: The CONCAT function is used to concatenate two strings together. The syntax is ```CONCAT(string1, string2)```. This will return a string that is the combination of string1 and string2.

LENGTH: The LENGTH function is used to return the length of a string. The syntax is ```LENGTH(string)```. This will return the number of characters in the string.

ROUND: The ROUND function is used to round a number to a specified number of decimal places. The syntax is ```ROUND(number, decimal_places)```. If decimal_places is omitted, the number is rounded to 0 decimal places.

TRIM: The TRIM function is used to remove leading and/or trailing characters from a string. The syntax is ```TRIM([LEADING | TRAILING | BOTH] [removal_string] FROM string)```. If removal_string is omitted, it defaults to a space character.

AVG: The AVG function returns the average value of a numeric column. The syntax is ```AVG(column_name)```.

COUNT: The COUNT function returns the number of rows that matches a specified criterion. The syntax is ```COUNT(column_name)```.

MIN/MAX: The MIN and MAX functions return the smallest/largest value of the selected column. The syntax is ```MIN(column_name)``` and ```MAX(column_name)```.

GROUP BY: Although not a function, the GROUP BY statement is often used with aggregate functions (like COUNT, AVG, MAX, etc.) to group the result-set by one or more columns.

SUM: The SUM function returns the total sum of a numeric column. The syntax is ```SUM(column_name)```.

These are just a few of the many functions available in SQL. Different databases may have different functions or variations of these, so it's always a good idea to refer to the specific documentation for the SQL version you're using.

