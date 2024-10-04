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

