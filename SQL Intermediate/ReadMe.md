# Hackerank SQL (Intermediate) Challenges

## Binary Tree Nodes
You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.

| Column | Type |
|-------|-------|
|N | Integer |
| P | Integer |

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

Root: If node is root node.

Leaf: If node is leaf node.

Inner: If node is neither root nor leaf node.

      SELECT 
          N,
          CASE
              WHEN P IS NULL THEN 'Root'
              WHEN N NOT IN (SELECT DISTINCT P FROM BST WHERE P IS NOT NULL) THEN 'Leaf'
              ELSE 'Inner'
          END AS node_type
      FROM BST
      ORDER BY N;

**Explanation:**

**Root:** If P is NULL, it means the node has no parent and is the root.

**Leaf:** If a node N does not appear in the P column of any row, it is a leaf node (no children).

**Inner:** If a node has a parent and also appears in the P column for other nodes, it is an inner node.


## New Companies
Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy:

Founder --> Lead Manager --> Senior Manager --> Employee

Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

Note:

The tables may contain duplicate records.
The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.

Input Format

The following tables contain company data:

* Company: The company_code is the code of the company and founder is the founder of the company.

| Column | Type |
|--------|------|
| company_code | String |
| founder | String |

* Lead_Manager: The lead_manager_code is the code of the lead manager, and the company_code is the code of the working company.

| Column | Type |
|--------|------|
| lead_manager_code | String |
| company_code | String |

* Senior_Manager: The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.
  
| Column | Type |
|--------|------|
| senior_manager_code | String |
| lead_manager_code | String |
| company_code | String |

* Manager: The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company. 

| Column | Type |
|--------|------|
| manager_code | String |
| senior_manager_code | String |
| lead_manager_code | String |
| company_code | String |

* Employee: The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.

| Column | Type |
|--------|------|
| employee_code | String |
| manager_code | String |
| senior_manager_code | String |
| lead_manager_code | String |
| company_code | String |

## Weather Observation Station 20

A median is defined as a number separating the higher half of a data set from the lower half. Query the median of the Northern Latitudes (LAT_N) from STATION and round your answer to 4 decimal places.

The STATION table is described as follows:

| Field | Type |
|-------|------|
| ID | Number |
| City | VarChar(21) |
| State | VarChar(2) |
| Lat_N | Number |
| Long_W | Number |

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution

To find the median in any dataset,
* tOrder the values in ascending or descending order
* Determine the count of all the values. If the count is even, find the average of the two middle numvbers. If the count is odd, the median is the middle number.

Implement this in MySQL:

      WITH ranked_values AS (      -- create a CTE that orders the column that contains the values we want to extract the median from
          SELECT
              LAT_N,
              ROW_NUMBER() OVER (ORDER BY LAT_N) AS row_num, -- Assigns a unique row number to each value when sorted by value
              COUNT(*) OVER () AS total      -- Provides the total count of rows in the dataset, avoiding the need for a separate count query
          FROM STATION
      )
      
      SELECT
          ROUND(AVG(LAT_N), 4) AS Median
      FROM ranked_values
       WHERE row_num IN (FLOOR((total+1)/2), CEIL((total+1)/2))      -- Find the middle row(s) for both odd and even numbers of rows


**Note:**

For odd rows, the expression FLOOR((total_rows + 1) / 2) and CEIL((total_rows + 1) / 2) will point to the same middle value.
For even rows, it helps identify the two middle values, which are averaged to compute the median.
