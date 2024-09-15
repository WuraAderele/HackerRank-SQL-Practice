# SQL (Basic) HackerRank Practice

### Revising the Select Query I
Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
            SELECT *
            FROM City
            WHERE (
                CountryCode = "USA"
                AND Population > 100000
                );

### Revising the Select Query II
Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
            SELECT Name AS American_Cities
            FROM City
            WHERE (
                CountryCode = "USA"
                AND Population > 120000
                );
            
### Select All  
Query all columns (attributes) for every row in the CITY table. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
            SELECT * FROM City
            
### Select By ID  
Query all columns for a city in CITY with the ID 1661.The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
          SELECT *
          FROM City
          WHERE ID = 1661;

### Japanese Cities' Attributes
Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
            SELECT *
            FROM City
            WHERE CountryCode = "JPN"

### Japanese Cities' Names
Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
            SELECT Name
            FROM City
            WHERE CountryCode = "JPN";
            
### Revising Agregations: The COUNT Function
Query a count of the number of cities in CITY having a Population larger than 10000. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
              SELECT COUNT(*) 
              
              FROM City
              WHERE Population > 100000;
              
### Revising Agregations: The SUM Function
Query the total population of all cities in CITY where District is California. The CITY table is described as follows:|FIELD|TYPE|
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
              SELECT SUM(Population) 
              FROM City
              WHERE District = "California";

### Revising Agregations: The AVERAGE Function
Query the average population of all cities in CITY where District is California. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
            SELECT AVG(Population)
            FROM City
            WHERE DISTRICT = "California";
            
### Average Population
Query the average population for all cities in CITY, rounded down to the nearest integer. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
            SELECT FLOOR(AVG(Population)) 
            FROM City;

### JAPAN Population
Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
              SELECT SUM(Population)
              FROM City 
              WHERE Countrycode = "JPN";

### Population Density
Query the difference between the maximum and minimum populations in CITY. The CITY table is described as follows:
|FIELD|TYPE|
|------|----|
|ID|NUMBER|
|NAME|VARCHAR|
|COUNTRYCODE|VARCHAR|
|DISTRICT|VARCHAR|
|POPULATION|NUMBER|
            SELECT (MAX(POPULATION) - MIN(POPULATION))
            FROM CITY

### Weather Observation Station 1
Query a list of CITY and STATE from the STATION table. The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
            SELECT City
              ,STATE
            FROM Station;
            
### Weather Observation Station 2
Query the following two values from the STATION table:
* The sum of all values in LAT_N rounded to a scale of 2 decimal places.
* The sum of all values in LONG_W rounded to a scale of 2 decimal places.
The STATION table is described as follows:

|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|            
          SELECT ROUND(SUM(LAT_N), 2)
            ,ROUND(SUM(LONG_W), 2)
          FROM STATION;
          
### Weather Observation Station 3
Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
          SELECT DISTINCT City
          FROM Station
          WHERE (ID MOD 2 = 0);
          
### Weather Observation Station 4
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
The STATION table is described as follows: 
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
          SELECT (COUNT(CITY) - COUNT(DISTINCT CITY))
          FROM Station

### Weather Observation Station 6
Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates. The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
          SELECT DISTINCT City
          FROM Station
          WHERE SUBSTRING(City, 1, 1) IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              );
              
### Weather Observation Station 7
Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates. The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
        SELECT DISTINCT City
        FROM STATION
        WHERE RIGHT(City, 1) IN (
            "a"
            ,"e"
            ,"i"
            ,"o"
            ,"u"
            );
            
### Weather Observation Station 8
Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.
The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
          SELECT DISTINCT City
          FROM Station
          WHERE LEFT(City, 1) IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              )
            AND RIGHT(CITY, 1) IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              );

### Weather Observation Station 9
Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates. The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
          SELECT DISTINCT City
          FROM STATION
          WHERE LEFT(City, 1) NOT IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              );
              
### Weather Observation Station 10
Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates. The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
          SELECT DISTINCT City
          FROM Station
          WHERE RIGHT(City, 1) NOT IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              );
              
### Weather Observation Station 11
Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.
The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
          SELECT DISTINCT City
          FROM Station
          WHERE LEFT(City, 1) NOT IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              )
            OR RIGHT(City, 1) NOT IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              );
              
### Weather Observation Station 12
Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.
The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
          SELECT DISTINCT City
          FROM STATION
          WHERE LEFT(City, 1) NOT IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              )
            AND RIGHT(City, 1) NOT IN (
              "a"
              ,"e"
              ,"i"
              ,"o"
              ,"u"
              );
              
### Weather Observation Station 13
Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.2345.
Truncate your answer to 4 decimal places.
The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
              SELECT ROUND(SUM(LAT_N), 4)
              FROM STATION
              WHERE LAT_N > 38.7880
                AND LAT_N < 137.2345;
                
### Weather Observation Station 14
Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to 4 decimal places.
The STATION table is described as follows:
|Field|Type|
|-----|----|
|ID|NUMBER|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|
            SELECT ROUND(LAT_N, 4)
            FROM STATION
            WHERE LAT_N < 137.2345
            ORDER BY LAT_N DESC LIMIT 1;
            
### Higher Than 75 Marks
Query the Name of any student in STUDENTS who scored higher than 75 Marks. Order your output by the last three characters of each name.
If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.
The STUDENTS table is described as follows:
|Column|Type|
|------|----|
|ID|Integer|
|Name|String|
|Marks|Integer|
          SELECT Name
          FROM Students
          WHERE Marks > 75
          ORDER BY RIGHT(Name, 3)
            ,ID ASC;
            
### Employee Names
Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.
The Employee table containing employee data for a company is described as follows:
|Column|Type|
|-------|----|
|employee_id|Integer|
|name|String|
|months|Integer|
|salary|Integer|
          SELECT name
          FROM Employee
          ORDER BY name ASC;
          
### Employee Salaries        
Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per
month who have been employees for less than 10  months. Sort your result by ascending employee_id. The Employee table containing employee data for a company is described as follows:  
|Column|Type|
|------|----|
|employee_id|Integer|
|name|String|
|months|Integer|
|salary|Integer|
            SELECT name
            FROM Employee
            WHERE Salary > 2000
              AND months < 10
            ORDER BY employee_id ASC;

### The Blunder
Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's 
0 key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation 
(using salaries with any zeros removed), and the actual average salary.
Write a query calculating the amount of error (i.e.: actual - miscalculated average monthly salaries), and round it up to the next integer.
The Employee table containing employee data for a company is described as follows:  
|Column|Type|
|------|----|
|employee_id|Integer|
|name|String|
|months|Integer|
|salary|Integer|
            SELECT ROUND(AVG(SALARY)) - ROUND(AVG(REPLACE(SALARY, '0', '')))
            FROM EMPLOYEES;
            
### Top Earners
We define an employee's total earnings to be their monthly salary x months worked, and the maximum total earnings to be the maximum total 
earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number 
of employees who have maximum total earnings. Then print these values as  space-separated integers.
The Employee table containing employee data for a company is described as follows:  
|Column|Type|
|------|----|
|employee_id|Integer|
|name|String|
|months|Integer|
|salary|Integer|
              SELECT (months * salary) AS earnings
                ,COUNT(*) 
                
              FROM Employee
              GROUP BY earnings
              ORDER BY earnings DESC LIMIT 1;
              
### Type of Triangle 
Write a query identifying the type of each record in the TRIANGLES table using its three side lengths.
Output one of the following statements for each record in the table:
* Equilateral: It's a triangle with 3 sides of equal length.
* Isosceles: It's a triangle with 2 sides of equal length.
* Scalene: It's a triangle with 3 sides of differing lengths.
* Not A Triangle: The given values of A, B, and C don't form a triangle. The TRIANGLES table is described as follows:

|Column|Type|
|-------|---|
|A|Integer|
|B|Integer|
|C|Integer|

              SELECT CASE 
                  WHEN A + B <= C
                    OR A + C <= B
                    OR B + C <= A
                    THEN "Not A Triangle"
                  WHEN A = B
                    AND B = C
                    THEN "Equilateral"
                  WHEN A = B
                    OR A = C
                    OR B = C
                    THEN "Isosceles"
                  ELSE "Scalene"
                  END
              FROM TRIANGLES;

### The PADS
Generate the following two result sets:
* Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a 
parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
* Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in 
* the following format:
  * There are a total of [occupation_count] [occupation]s.
 where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name.
If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.
Note: There will be at least two entries in the table for each type of occupation.

The OCCUPATIONS table is described as follows: 
|Column|Type|
|-----|----|
|Name|String|
|Occupation|String|

                SELECT CONCAT (
                    name
                    ,"("
                    ,LEFT(Occupation, 1)
                    ,")"
                    )
                FROM OCCUPATIONS
                ORDER BY Name ASC;

                SELECT CONCAT (
                    'There are a total of '
                    ,COUNT(Occupation)
                    ,' '
                    ,LOWER(Occupation)
                    ,'s.'
                    )
                FROM OCCUPATIONS
                GROUP BY Occupation
                ORDER BY Count(Occupation)
                  ,Occupation ASC;

### Weather Observation Station 18

Consider *P1(a,b)* and *P2(c,d)* and  to be two points on a 2D plane.

* a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
* b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
* c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
* d happens to equal the maximum value in Western Longitude (LONG_W in STATION).

Query the Manhattan Distance between points *P1* and *P2* and  and round it to a scale of 4 decimal places.

The **STATION** table is described as follows:

| Field | Type |
|------ |------|
| ID | Number |
| City | Varchar2(21) |
| State | Varchar2(1) |
| Lat_N | Number |
| Long_N | Number |

**Solution:**

**Definition of Manhattan distance:** The distance between two points measured along axes at right angles. In a plane with p1 at (x1, y1) and p2 at (x2, y2), it is |x1 - x2| + |y1 - y2|.

            SELECT
                 ROUND(ABS(a - c) + ABS(b - d), 4)
            FROM
                (SELECT
                    min(LAT_N) AS a,
                    min(LONG_W) AS b,
                    max(LAT_N) AS c,
                    max(LONG_W) AS d
                FROM STATION) AS dist_variables

### Weather Observation Station 19

Consider *P1(a,b)* and *P2(c,d)* and  to be two points on a 2D plane where *(a,b) are the respective minimum and and maximum values of Northern Latitude (LAT_N) and (c,d) are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.

Query the Euclidean Distance between points *P1* and *P2* and format your answer to display 4 decimal digits.

The STATION table is described as follows:

| Field | Type |
|------ |------|
| ID | Number |
| City | Varchar2(21) |
| State | Varchar2(1) |
| Lat_N | Number |
| Long_N | Number |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**

Euclidean distance formular:
<p align="left">
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/9c0157084fd89f5f3d462efeedc47d3d7aa0b773"></p>

            SELECT
                ROUND(SQRT(POW((a - c),2) + POW((b - d),2)), 4)
            FROM
                (SELECT
                    min(LAT_N) AS a,
                    min(LONG_W) AS b,
                    max(LAT_N) AS c,
                    max(LONG_W) AS d
                FROM STATION) AS dist_variables

