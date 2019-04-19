# Final Milestone SQL Statments

## Authors

Pranav Bhusari **

Scott Luntz

Matt Quigley

Myles Lesser

Justin Walshager

## Class

CNIT 27200

Professor: Dawn Laux

Team 11

## Tasks

### Task 1

Start with a single table query with 3 attributes and one filter in the WHERE clause.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 2

In a single table query, filter between two dates. Include appropriate attributes (including the date attribute used in the filter) that would make the query useful.


#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 3

Use LIKE in a filter (with the % wildcard). Use LIKE in such a way that the filter cannot be accomplished with an equal sign. For example: where color like ‘b%’ to find all colors that start with b.

#### Assigned to



#### SQL Statement

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 4

In the select clause, calculate two attributes to make a temporary calculated column. Give it a column alias. For example: Select price, quantity, price * quantity AS TOTAL_PRICE.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 5

Use NOT IN to filter out a list of values from an attribute in a single table query.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 6

In the Select clause, use a Null Value function (NVL) on an attribute, and right justify another of your attributes in the same statement. Add * to fill the empty spaces in the right justified column, and choose an appropriate replacement for the null values.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 7

In your database, where you have a date stored (order date, event date, etc), find the oldestdate along with the other fields in that table. (ie, oldest order in the ORDER table, oldest event stored in the DB).

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 8

Use the Count function to group by an attribute in your database. Use Count appropriately, as there should not be a count of 1 in each row of the result set. Find an attribute that uses the same value more than once (ie, do not use count on a primary key…).

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 9

Use the Sum function to add up a calculated column. For example: SUM(price*quantity) as TOTAL_ORDER.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 10

Use the Average function on either a number or date in your database. Use Group by to group the average by one field in the result set. (ie, Average price of each equipment type)

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 11

Use HAVING to filter an aggregated function (use Count, Sum, Min, Max or Avg in a query)

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 12

Build a SQL statement that filters with both a WHERE clause and a HAVING clause.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 13

Build an INNER JOIN between just two tables. The chosen attributes in the Select clause should come from both tables. Filter with at least two items in the WHERE clause.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 14

Build a query that has to pull from at least 4 different tables. The attributes in the Select clause should come from at least two of the tables. Include a date as one of your attributes and set the date format to report out like: Saturday, November 24, 2018.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 15

Use a nested subquery to find a pool of data and then the outer query is looking for records NOT IN the nested query.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 16

Use a subquery to find results that are greater than an average result in your nested query.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 17

Build an INNER JOIN between two tables and include an aggregate function in the Select clause. Must also include the use of Group By.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 18

Build a query that utilizes a LEFT OUTER JOIN. The result set should have parents that do not have children. (If you do not have this situation in your database, do an additional INSERT in the parent table in order to make the task work)

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 19

Build a query that utilizes a RIGHT OUTER JOIN. The result set should have children that do not have parents. (If you do not have this situation in your database, alter your database to allow a child table to have NULL values in the foreign key field. Then do an additional INSERT in the child table in order to make the task work).

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 20

Use UNION to join two tables together.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 21

Use INTERSECT to find common values between two tables.

#### Assigned to



#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

### Task 22

Make an update to a single record in one of your tables. Explain the update and then perform the task. Display the before, update, and after stmts/output.

#### Assigned to

Pranav Bhusari

#### Explanation

This SQL statment *updates* the `EMPLOYEE` table by *setting* the `salary` of all emloyees to 30 (thousand) *where* the `employeeID` reads as `0012      `.
In other words, this sets Pranav Bhusari's salary to 30.0 from a null value.

#### Before Query

```SQL
select * from employee
```

#### Before results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |0    |0.01 |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |2    |0.01 |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |3    |0.01 |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |5    |0.01 |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |6    |0.01 |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |2    |0    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |0    |0.01 |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |9    |0    |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |0    |0.01 |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |9    |0.01 |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |      |     |     |

#### SQL Statment

```SQL
update employee
set salary = 30
where employeeID = '0012      ';
```

#### Results

```
1 row updated.
```

#### Follow-up Query

```sql
select * from employee
```

#### Follow-up Results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |0    |0.01 |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |2    |0.01 |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |3    |0.01 |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |5    |0.01 |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |6    |0.01 |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |2    |0    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |0    |0.01 |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |9    |0    |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |0    |0.01 |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |9    |0.01 |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |


### Task 23

Update a set of records in one statement (more than one row should be updated). Explain the update and then perform the task. Display the before, update, and after stmts/output.

#### Assigned to

Pranav Bhusari

#### Explanation

Because it is the end of the year, I want to reset all of the bonuses of the employees on the table back to zero.

I can do this by running a SQL statment that *updates* the `EMPLOYEE` table by *setting* the `bonus` row to be zero for all records. (no where clause)

#### Before SQL Statment

```SQL
select * from employee;
```

#### Before SQL results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |0    |0.01 |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |2    |0.01 |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |3    |0.01 |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |5    |0.01 |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |6    |0.01 |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |2    |0    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |0    |0.01 |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |9    |0    |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |0    |0.01 |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |9    |0.01 |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |


#### SQL Statment

```SQL
update employee
set bonus = NULL;
```

#### Results

```
12 rows updated.
```

#### Follow-up Query

```SQL
select * from employee;
```

#### Follow-up Results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |


### Task 24

Add 2 rows to one of your tables. Run a query to display the newly added rows. Explain the update and then perform the task. Display the before, insert, and after stmts/output.

#### Assigned to

Pranav Bhusari

#### Explanation

Two new employees joined the company just today. To add them to the database, we must first complete a record in the `EMPLOYEE`s table first for each of them.
These SQL statments *insert* two records *into* the `EMPLOYEE` table. The *values* of these records are stated later in the query.

#### Before query

```
select * from employee
```

#### Before results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|
|0013      |Jack      |Smith   |18-APR-19|2055551337 |1 Infinite Loop                 |TECH                   |100   |0    |0    |
|0014      |John      |Smith   |18-APR-19|2055551338 |1 Infinite Loop                 |TECH                   |100   |0    |0    |
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |

#### SQL Statment

```SQL
INSERT INTO EMPLOYEE
  (
    EMPLOYEEID,
    FIRSTNAME,
    LASTNAME,
    HIREDATE,
    PHONENUMBER,
    ADDRESS,
    DEPARTMENT_DEPARTMENTID,
    SALARY,
    BONUS,
    RAISE)
VALUES
  (
    '0013      ',
    'Jack',
    'Smith',
    TO_DATE('2019-04-18 23:32:48', 'YYYY-MM-DD HH24:MI:SS'),
    '2055551337',
    '1 Infinite Loop',
    'TECH',
    100.00,
    0.00,
    0.00
  );

INSERT INTO EMPLOYEE
  (
    EMPLOYEEID,
    FIRSTNAME,
    LASTNAME,
    HIREDATE,
    PHONENUMBER,
    ADDRESS,
    DEPARTMENT_DEPARTMENTID,
    SALARY,
    BONUS,
    RAISE
  )
VALUES
  (
    '0014      ',
    'John ',
    'Smith',
    TO_DATE('2019-04-18 23:32:48',
    'YYYY-MM-DD HH24:MI:SS'),
    '2055551338',
    '1 Infinite Loop',
    'TECH',
    100.00,
    0.00,
    0.00
  );

commit;
```

#### Results

```
1 row inserted.


1 row inserted.

Commit complete.
```

#### Follow-up Query

```SQL
select * from employee
```

#### Follow-up Results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|
|0013      |Jack      |Smith   |18-APR-19|2055551337 |1 Infinite Loop                 |TECH                   |100   |0    |0    |
|0014      |John      |Smith   |18-APR-19|2055551338 |1 Infinite Loop                 |TECH                   |100   |0    |0    |
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |

### Task 25

Delete a row from one of your tables. Explain the deletion and then perform the task. Display the before, deletion, and after stmts/output.

#### Assigned to

Pranav Bhusari

#### Explanation

It looks like Jack got a better jobs on the day after. He left and they never looked back, not even an offer letter. Since they quit, we need to get rid of their record from the database.

This SQL statment *deletes* records *from* the `EMPLOYEE` table *where* the `employeeID` matches that of Jack.

#### Before Statment

```SQL
select * from employee;
```

#### Before Results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|
|0013      |Jack      |Smith   |18-APR-19|2055551337 |1 Infinite Loop                 |TECH                   |100   |0    |0    |
|0014      |John      |Smith   |18-APR-19|2055551338 |1 Infinite Loop                 |TECH                   |100   |0    |0    |
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |


#### SQL Statment

```SQL
delete from employee
where employeeid='0013      '
commit;
```

#### Results

```
1 row deleted.


Commit complete.
```

#### Follow-up Query

```SQL
select * from employee;
```

#### Follow-up Results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|
|0014      |John      |Smith   |18-APR-19|2055551338 |1 Infinite Loop                 |TECH                   |100   |0    |0    |
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |


### Task 26

Alter a table by adding a new column. Do a DESCRIBE after you have added the new column. Explain the update and then perform the task. Display the before, alter, and after stmts/output.

#### Assigned to

Pranav Bhusari

#### Explanation

DataTech needs to keep in touch with the times. I mean sure, phone numbers might do the job for the average law firm. Since DataTech is a cool tech company, however, we need a cool, new, and hip way to contact our employees: email.
This sql statment *alters* the `EMPLOYEE` table by *adding* a new `varchar` attribute names email with a length of 50.

#### Before Statment

```sql
DESCRIBE employee
```

#### Before results

|Name      |Null?     |Type    |
|----------|----------|--------|
|EMPLOYEEID|NOT NULL  |CHAR(10)|
|FIRSTNAME |          |VARCHAR2(50)|
|LASTNAME  |          |VARCHAR2(50 CHAR)|
|HIREDATE  |          |DATE    |
|PHONENUMBER|          |VARCHAR2(10 CHAR)|
|ADDRESS   |          |VARCHAR2(35 CHAR)|
|DEPARTMENT_DEPARTMENTID|          |CHAR(10)|
|SALARY    |          |NUMBER(9,2)|
|BONUS     |          |NUMBER(9,2)|
|RAISE     |          |NUMBER(2,2)|


#### SQL Statment

```SQL
alter table employee
  add email varchar(50);
```

#### Results

```
Table EMPLOYEE altered.
```

#### Follow-up Query

```SQL
describe employee;
```

#### Follow-up Results

|Name      |Null?     |Type    |
|----------|----------|--------|
|EMPLOYEEID|NOT NULL  |CHAR(10)|
|FIRSTNAME |          |VARCHAR2(50)|
|LASTNAME  |          |VARCHAR2(50 CHAR)|
|HIREDATE  |          |DATE    |
|PHONENUMBER|          |VARCHAR2(10 CHAR)|
|ADDRESS   |          |VARCHAR2(35 CHAR)|
|DEPARTMENT_DEPARTMENTID|          |CHAR(10)|
|SALARY    |          |NUMBER(9,2)|
|BONUS     |          |NUMBER(9,2)|
|RAISE     |          |NUMBER(2,2)|
|EMAIL     |          |VARCHAR2(50)|


### Task 27

Populate the new column for all records in the table. It can be the same value for all records. Explain the insert and then perform the task. Display the before, insert, and after stmts/output.

#### Assigned to

Pranav Bhusari

#### Explanation

To assign each employee with a unique email, you can concatenate their first and last names together.
The following SQL statment *updates* the `EMPLOYEE` table by *setting* the email to be the `firstname` of the employee concatenated with the `lastname` of the employee concatenated with the email domain "@dataTech.co".

#### Before Statment

```sql
select * from employee;
```

#### Before Results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|EMAIL|
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|-----|
|0014      |John      |Smith   |18-APR-19|2055551338 |1 Infinite Loop                 |TECH                   |100   |0    |0    |     |
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |     |
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |     |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |     |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |     |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |     |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |     |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |     |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |     |
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |     |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |     |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |     |


#### SQL Statment


```SQL
update employee
    set email = (firstname || lastname || '@dataTech.co' );
commit;
```

#### Results

```
13 rows selected.


13 rows updated.


Commit complete.
```

#### Follow-up Query

```SQL
select * from employee;
```

#### Follow-up Results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|EMAIL                        |
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|-----------------------------|
|0014      |John      |Smith   |18-APR-19|2055551338 |1 Infinite Loop                 |TECH                   |100   |0    |0    |John Smith@dataTech.co       |
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |ChristianChandler@dataTech.co|
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |PatrickBateman@dataTech.co   |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |HueyLewis@dataTech.co        |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |PaulAllen@dataTech.co        |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |Andrew Yang@dataTech.co      |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |DonaldSanders@dataTech.co    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |BernieTrump@dataTech.co      |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |AlexandriaRamerez@dataTech.co|
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |RicardoChandler@dataTech.co  |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |ChristianChantor@dataTech.co |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |Myles Lesser@dataTech.co     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |Pranav Bhusari@dataTech.co   |


### Task 28

Update a record using SUBSTR in the SET. Explain the update and then perform the task. Display the before, update, and after stmts/output.

#### Assigned to

Pranav Bhusari

#### Explanation

There was a small issue in the email assignments. Not all of the names were formateed properly. To combat this, `SUBSTR` is used to make the emails more consise and standard.

This sql statment *updates* the `EMPLOYEE` table by *setting* the email to the employees first initial concatenated with their last name concatenated with the email domain name (@dataTech.co).

#### Before Statment

```sql
select * from employee
```

#### Before Result

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|EMAIL                        |
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|-----------------------------|
|0014      |John      |Smith   |18-APR-19|2055551338 |1 Infinite Loop                 |TECH                   |100   |0    |0    |John Smith@dataTech.co       |
|0001      |Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |ChristianChandler@dataTech.co|
|0002      |Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |PatrickBateman@dataTech.co   |
|0003      |Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |HueyLewis@dataTech.co        |
|0004      |Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |PaulAllen@dataTech.co        |
|0005      |Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |Andrew Yang@dataTech.co      |
|0006      |Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |DonaldSanders@dataTech.co    |
|0007      |Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |BernieTrump@dataTech.co      |
|0008      |Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |AlexandriaRamerez@dataTech.co|
|0009      |Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |RicardoChandler@dataTech.co  |
|0010      |Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |ChristianChantor@dataTech.co |
|0011      |Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |Myles Lesser@dataTech.co     |
|0012      |Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |Pranav Bhusari@dataTech.co   |


#### SQL Statment

```SQL
update employee
    set email =
      (
        lower(substr(firstname, 1,1))
        ||
        lower(lastname)
        ||
        '@dataTech.co'
      );
commit;
```

#### Results

```
13 rows updated.


Commit complete.
```

#### Follow-up Query

```SQL
select * from employee;
```

#### Follow-up Results

|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|EMAIL                |
|----------|----------|--------|---------|-----------|--------------------------------|-----------------------|------|-----|-----|---------------------|
|0014|John      |Smith   |18-APR-19|2055551338 |1 Infinite Loop                 |TECH                   |100   |0    |0    |jsmith@dataTech.co   |
|0001|Christian |Chandler|06-APR-19|2025550139 |366 Brookside Court Florence    |TECH                   |100   |     |0.01 |cchandler@dataTech.co|
|0002|Patrick   |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120   |     |0.01 |pbateman@dataTech.co |
|0003|Huey      |Lewis   |02-APR-01|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60    |     |0.01 |hlewis@dataTech.co   |
|0004|Paul      |Allen   |06-SEP-18|2025550187 |8974 Argyle Court South Portland|TECH                   |100   |     |0.01 |pallen@dataTech.co   |
|0005|Andrew    |Yang    |11-OCT-15|2025550183 |8526 Gartner St. West Warwick   |HR                     |70    |     |0.01 |ayang@dataTech.co    |
|0006|Donald    |Sanders |27-NOV-01|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30    |     |0    |dsanders@dataTech.co |
|0007|Bernie    |Trump   |20-NOV-13|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100   |     |0.01 |btrump@dataTech.co   |
|0008|Alexandria|Ramerez |11-JUN-12|2025550132 |176 Mill Pond Ave.              |TECH                   |120   |     |0    |aramerez@dataTech.co |
|0009|Ricardo   |Chandler|27-SEP-13|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70    |     |0.01 |rchandler@dataTech.co|
|0010|Christian |Chantor |13-AUG-14|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30    |     |0.01 |cchantor@dataTech.co |
|0011|Myles     |Lesser  |09-APR-13|2023214030 |14 Ross Ade Dr.                 |REC                    |10    |     |     |mlesser@dataTech.co  |
|0012|Pranav    |Bhusari |13-JUN-12|2025551489 |15 Tarkington Bolevard          |REC                    |30    |     |     |pbhusari@dataTech.co |


### Task 29

Create an alternate key and an inversion entry for one of your tables. Run a query on the metadata to list the new indexes in your database.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL

```

#### Results

(Note: Import sql --> csv --> markdown for pretty tables)
```

```

#### Explanation

#### Follow-up Query

```SQL

```

#### Follow-up Results

```

```

### Task 30

Your choice. Build a query. Can be as simple or complex as you want. Run the query and display the results.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select to_char(sysdate, 'MM-DD-YYYY HH24:MI:SS') as CURRENT_TIME
from dual;
```

#### Results

|CURRENT_TIME|
|------------|
|04-18-2019 19:30:28|
