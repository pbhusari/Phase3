# Final Milestone SQL Statments

## Authors

Pranav Bhusari

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

Pranav Bhusari

#### SQL Statment

```SQL
select
   firstname,
   lastname,
   phonenumber
from
   employee
where
   Department_departmentid like 'TECH      ';
```

#### Results

|FIRSTNAME |LASTNAME|PHONENUMBER|
|----------|--------|-----------|
|John      |Smith   |2055551338 |
|Christian |Chandler|2025550139 |
|Paul      |Allen   |2025550187 |
|Bernie    |Trump   |2025550119 |
|Alexandria|Ramerez |2025550132 |

### Task 2

In a single table query, filter between two dates. Include appropriate attributes (including the date attribute used in the filter) that would make the query useful.


#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    invoiceid,
    issuedate
from
    invoice
where
    issuedate
        between
            to_date('01-01-2018', 'MM-DD-YYYY')
            and
            to_date('12-31-2018', 'MM-DD-YYYY');
```

#### Results

|INVOICEID |ISSUEDATE|
|----------|---------|
|9|12-AUG-18|


### Task 3

Use LIKE in a filter (with the % wildcard). Use LIKE in such a way that the filter cannot be accomplished with an equal sign. For example: where color like ‘b%’ to find all colors that start with b.

#### Assigned to

Pranav Bhuari

#### SQL Statement

```SQL
select
  INVOICEID,
  subject,
  ISSUEDATE
from
  invoice
WHERE
  subject like '%Pizza'
```

#### Results

|INVOICEID |SUBJECT        |ISSUEDATE|
|----------|---------------|---------|
|9|Sliceline Pizza|12-AUG-18|
|10|Sliceline Pizza|07-FEB-19|


### Task 4

In the select clause, calculate two attributes to make a temporary calculated column. Give it a column alias. For example: Select price, quantity, price * quantity AS TOTAL_PRICE.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    purchase_order_orderid,
    orderlineid,
    estimateditemprice * itemquantity as total_estimated_price
from
    purchase_order_line;
```

#### Results

|PURCHASE_ORDER_ORDERID|ORDERLINEID|TOTAL_ESTIMATED_PRICE|
|----------------------|-----------|---------------------|
|10                    |1          |105                  |
|10                    |2          |90                   |
|10                    |3          |100                  |
|10                    |4          |106                  |
|9                     |1          |88                   |
|9                     |2          |100                  |
|9                     |3          |100                  |
|1                     |1          |450                  |
|2                     |1          |3000                 |
|4                     |1          |630                  |
|7                     |1          |300                  |


### Task 5

Use NOT IN to filter out a list of values from an attribute in a single table query.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    accountid,
    accountname,
    accountdescription
from
    account
where
    accountID not in
                        (
                            select
                                account_accountid
                            from
                                payment
                        );
```

#### Results

|ACCOUNTID |ACCOUNTNAME|ACCOUNTDESCRIPTION|
|----------|-----------|------------------|
|5|Endframe   |Client            |
|6|DataTech   |Company           |
|7|FastFit    |Client            |
|8|SliceLine  |Client            |
|9|Optimoji   |Client            |

### Task 6

In the Select clause, use a Null Value function (NVL) on an attribute, and right justify another of your attributes in the same statement. Add * to fill the empty spaces in the right justified column, and choose an appropriate replacement for the null values.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    lpad(to_char(itemid), 5, '*') as item_id,
    lpad((description), 20, '*') as description,
    lpad(to_char(quantity), 5, '*') as quantity,
    lpad(nvl(to_char(weightpound), 'not applicable'), 5, '*') as weightpound
from
    inventory_item
```

#### Results

|ITEM_ID|DESCRIPTION         |QUANTITY|WEIGHTPOUND|
|-------|--------------------|--------|-----------|
|1      |***************Pizza|***10   |****3      |
|2      |*************Monitor|***10   |***20      |
|3      |****Desktop Computer|****3   |***20      |
|4      |*****Laptop Computer|****2   |****2      |
|5      |****EndFrame License|****2   |not a      |
|6      |********Raspberry pi|***30   |***.5      |
|7      |*****Micro USB Cable|***30   |***.5      |
|8      |*******32 GB SD Card|***30   |***.1      |
|9      |************1 TB SSD|****5   |***.1      |
|10     |*Thunderbolt Adapter|***10   |***.5      |



### Task 7

In your database, where you have a date stored (order date, event date, etc), find the oldestdate along with the other fields in that table. (ie, oldest order in the ORDER table, oldest event stored in the DB).

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    *
from
    employee
where
    hiredate =
            (
            select
                min(hiredate)
            from
                employee
            );

```

#### Results

|EMPLOYEEID|FIRSTNAME|LASTNAME|HIREDATE |PHONENUMBER|ADDRESS              |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|EMAIL               |
|----------|---------|--------|---------|-----------|---------------------|-----------------------|------|-----|-----|--------------------|
|0002|Patrick  |Bateman |06-NOV-99|2025550101 |8287 Kent Ave. owosso|EXEC                   |120   |     |0.01 |pbateman@dataTech.co|


### Task 8

Use the Count function to group by an attribute in your database. Use Count appropriately, as there should not be a count of 1 in each row of the result set. Find an attribute that uses the same value more than once (ie, do not use count on a primary key…).

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    count(*), purchase_order_orderid
from
    purchase_order_line
group by
    purchase_order_orderid;
```

#### Results

|COUNT(*)|PURCHASE_ORDER_ORDERID|
|--------|----------------------|
|1       |1                     |
|4       |10                    |
|1       |2                     |
|1       |4                     |
|1       |7                     |
|3       |9                     |


### Task 9

Use the Sum function to add up a calculated column. For example: SUM(price*quantity) as TOTAL_ORDER.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    sum(esitmateditemprice * itemquantity) as TOTAL_ORDER_PROCE
from
    purchase_order_line;
```

#### Results

|TOTAL_ORDER_PROCE|
|-----------------|
|5069             |

### Task 10

Use the Average function on either a number or date in your database. Use Group by to group the average by one field in the result set. (ie, Average price of each equipment type)

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    department_departmentid,
    avg(salary)
from
    employee
group by
    department_departmentid;
```

#### Results

|DEPARTMENT_DEPARTMENTID|AVG(SALARY)                              |
|-----------------------|-----------------------------------------|
|TECH                   |104                                      |
|SHIP                   |60                                       |
|MGMT                   |70                                       |
|EXEC                   |120                                      |
|HR                     |70                                       |
|REC                    |23.33333333333333333333333333333333333333|
|PAY                    |30                                       |


### Task 11

Use HAVING to filter an aggregated function (use Count, Sum, Min, Max or Avg in a query)

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    department_departmentid,
    avg(salary)
from
    employee
group by
    department_departmentid
having
    avg(salary) >
                  (
                    select
                      avg(salary)
                    from
                      employee
                  );
```

#### Results

|DEPARTMENT_DEPARTMENTID|AVG(SALARY)|
|-----------------------|-----------|
|TECH                   |104        |
|EXEC                   |120        |


### Task 12

Build a SQL statement that filters with both a WHERE clause and a HAVING clause.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    MANUFACTURERER,
    avg(heightinches * widthinches * lengthinches) as volume
from
    inventory_item
where
    quantity > 5
group by
    MANUFACTURERER
having
    avg(heightinches * widthinches * lengthinches) >
                                                    (
                                                        select
                                                            avg(heightinches * widthinches * lengthinches)
                                                        from
                                                            inventory_item
                                                    );
```

#### Results

|MANUFACTURERER|VOLUME|
|--------------|------|
|Monoprice     |8662  |


### Task 13

Build an INNER JOIN between just two tables. The chosen attributes in the Select clause should come from both tables. Filter with at least two items in the WHERE clause.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    employee.firstname,
    employee.lastname,
    employee.DEPARTMENT_DEPARTMENTID,
    department.building
from
    employee inner join department
        on department.DEPARTMENTID =  employee.DEPARTMENT_DEPARTMENTID
where
    (employee.DEPARTMENT_DEPARTMENTID  in (select department_departmentid from employee))
    and
    (department.building like '%South St%');
```

#### Results

|FIRSTNAME |LASTNAME|DEPARTMENT_DEPARTMENTID|BUILDING    |
|----------|--------|-----------------------|------------|
|Patrick   |Bateman |EXEC                   |100 South St|
|Andrew    |Yang    |HR                     |100 South St|
|Ricardo   |Chandler|MGMT                   |120 South St|
|Donald    |Sanders |PAY                    |120 South St|
|John      |Smith   |TECH                   |110 South St|
|Bernie    |Trump   |TECH                   |110 South St|
|Christian |Chandler|TECH                   |110 South St|
|Paul      |Allen   |TECH                   |110 South St|
|Alexandria|Ramerez |TECH                   |110 South St|



### Task 14

Build a query that has to pull from at least 4 different tables. The attributes in the Select clause should come from at least two of the tables. Include a date as one of your attributes and set the date format to report out like: Saturday, November 24, 2018.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
       INVOICELINEID,
       ITEMTYPE,
       INVOICELINE.DESCRIPTION,
       QUANTITY,
       UNITPRICE,
       TAX,
       INVOICEID,
       ISSUEDATE,
       DUEDATE,
       SUBJECT,
       PURCHASE_ORDER_ORDERID,
       ORDERID,
       "Date",
       DELIVERYDATE,
       EMPLOYEE_EMPLOYEEID,
       EMPLOYEEID,
       FIRSTNAME,
       LASTNAME,
       to_char(HIREDATE, 'Day, Month, DD, YYYY'),
       DEPARTMENTID,
       BUILDING,
       DEPARTMENT.DESCRIPTION
from
    INVOICELINE inner join INVOICE I
        on INVOICELINE.INVOICE_INVOICEID = I.INVOICEID
    inner join PURCHASE_ORDER
        ON I.PURCHASE_ORDER_ORDERID = PURCHASE_ORDER.ORDERID
    inner join EMPLOYEE E
        on PURCHASE_ORDER.EMPLOYEE_EMPLOYEEID = E.EMPLOYEEID
    inner join DEPARTMENT
        on E.DEPARTMENT_DEPARTMENTID = DEPARTMENT.DEPARTMENTID;
```

#### Results

|INVOICE_INVOICEID|INVOICELINEID|ITEMTYPE|DESCRIPTION                           |QUANTITY|UNITPRICE|TAX |INVOICEID |ISSUEDATE          |DUEDATE            |SUBJECT                           |PURCHASE_ORDER_ORDERID|ORDERID   |Date               |DELIVERYDATE       |EMPLOYEE_EMPLOYEEID|EMPLOYEEID|FIRSTNAME|LASTNAME|TO_CHAR(HIREDATE,'DAY,MONTH,DD,YYYY')|DEPARTMENTID|BUILDING      |DESCRIPTION|
|-----------------|-------------|--------|--------------------------------------|--------|---------|----|----------|-------------------|-------------------|----------------------------------|----------------------|----------|-------------------|-------------------|-------------------|----------|---------|--------|-------------------------------------|------------|--------------|-----------|
|1                |1            |Service |Consultation Fee                      |2       |15       |0   |1|2014-04-07 19:31:06|2014-05-07 19:31:06|Purdue Analytics Consultation Sale|1                     |1|2014-04-07 19:31:06|2014-04-10 19:31:16|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|1                |2            |Product |Monitors Sold                         |3       |150      |0.08|1|2014-04-07 19:31:06|2014-05-07 19:31:06|Purdue Analytics Consultation Sale|1                     |1|2014-04-07 19:31:06|2014-04-10 19:31:16|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|2                |1            |Product |Desktop Computers                     |10      |666      |0.08|2|2014-05-08 19:31:34|2014-06-08 19:31:34|DataTech Equipement Purchase      |2                     |2|2014-05-08 19:31:34|2014-05-11 19:31:43|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|3                |1            |Service |Server Space Rent                     |12      |0.5      |0   |3|2014-09-15 19:32:13|2014-11-15 19:32:13|DataTech Server Lease             |3                     |3|2014-09-15 19:32:13|2014-09-09 19:32:22|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|4                |1            |Product |Laptops Sold For DataTech Equipment   |2       |300      |0.08|4|2014-10-07 19:32:54|2014-11-07 19:32:54|DataTech Employee Laptops         |4                     |4|2014-10-07 19:32:54|2014-10-11 19:33:02|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|5                |1            |Service |Fake data population                  |5       |75       |0   |5|2014-12-05 19:33:23|2015-01-05 19:33:23|DataTech Fake SQL Data            |5                     |5|2014-12-05 19:33:23|2014-12-18 19:33:52|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|6                |1            |Service |Pied Piper Legal Fees, lawyer hours   |10      |1000     |0   |6|2015-01-08 19:34:41|2015-10-08 19:34:41|Pied Piper Legal Fees             |6                     |6|2015-01-08 19:34:41|2019-01-11 19:34:52|0002               |0002|Patrick  |Bateman |Saturday , November , 06, 1999       |EXEC        |100 South St  |Executive  |
|7                |1            |Product |Endframe licensing fee for 2 computers|2       |150      |0.08|7|2016-08-09 19:35:31|2016-11-09 19:35:31|Endframe License                  |7                     |7|2016-08-09 19:35:31|2016-08-14 19:35:41|0002               |0002|Patrick  |Bateman |Saturday , November , 06, 1999       |EXEC        |100 South St  |Executive  |
|8                |1            |Service |Messaging service, quantity per client|30      |10       |0.01|8|2017-09-11 19:35:48|2017-10-11 19:35:48|Optimoji Messaging Service        |8                     |8|2017-09-11 19:35:48|2017-09-13 19:35:59|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|9                |1            |Product |Pizza                                 |10      |5        |0.08|9|2018-08-12 19:36:08|2018-09-12 19:36:08|Sliceline Pizza                   |9                     |9|2018-08-12 19:36:08|2018-08-11 19:36:43|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|10               |1            |Product |Pizza                                 |10      |5        |0.08|10|2019-02-07 19:36:52|2019-03-07 19:36:52|Sliceline Pizza                   |10                    |10|2019-02-07 19:36:52|2019-02-14 19:36:58|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|10               |2            |Product |Pizza                                 |10      |5        |0.08|10|2019-02-07 19:36:52|2019-03-07 19:36:52|Sliceline Pizza                   |10                    |10|2019-02-07 19:36:52|2019-02-14 19:36:58|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|10               |3            |Product |Pizza                                 |10      |5        |0.08|10|2019-02-07 19:36:52|2019-03-07 19:36:52|Sliceline Pizza                   |10                    |10|2019-02-07 19:36:52|2019-02-14 19:36:58|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|10               |4            |Product |Pizza                                 |10      |5        |0.08|10|2019-02-07 19:36:52|2019-03-07 19:36:52|Sliceline Pizza                   |10                    |10|2019-02-07 19:36:52|2019-02-14 19:36:58|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|9                |2            |Product |Pizza                                 |10      |5        |0.08|9|2018-08-12 19:36:08|2018-09-12 19:36:08|Sliceline Pizza                   |9                     |9|2018-08-12 19:36:08|2018-08-11 19:36:43|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|9                |3            |Product |Pizza                                 |10      |5        |0.08|9|2018-08-12 19:36:08|2018-09-12 19:36:08|Sliceline Pizza                   |9                     |9|2018-08-12 19:36:08|2018-08-11 19:36:43|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |
|9                |4            |Product |Pizza                                 |10      |5        |0.08|9|2018-08-12 19:36:08|2018-09-12 19:36:08|Sliceline Pizza                   |9                     |9|2018-08-12 19:36:08|2018-08-11 19:36:43|0003               |0003|Huey     |Lewis   |Monday   , April    , 02, 2001       |SHIP        |200 North Side|Shipping   |


### Task 15

Use a nested subquery to find a pool of data and then the outer query is looking for records NOT IN the nested query.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    DEPARTMENTID
from
     DEPARTMENT
where
    (DEPARTMENTID  in (select department_departmentid from employee))
```

#### Results

|DEPARTMENTID|
|------------|
|EXEC        |
|HR          |
|MGMT        |
|PAY         |
|REC         |
|SHIP        |
|TECH        |



### Task 16

Use a subquery to find results that are greater than an average result in your nested query.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    INVOICELINEID,
    DESCRIPTION,
    QUANTITY * UNITPRICE * (TAX + 1) as total_price
from INVOICELINE
where QUANTITY * UNITPRICE * (TAX + 1) > (select avg(QUANTITY * UNITPRICE * (TAX + 1)) from INVOICELINE);
```

#### Results

|INVOICELINEID|DESCRIPTION                        |TOTAL_PRICE|
|-------------|-----------------------------------|-----------|
|1            |Desktop Computers                  |7192.8     |
|1            |Pied Piper Legal Fees, lawyer hours|10000      |



### Task 17

Build an INNER JOIN between two tables and include an aggregate function in the Select clause. Must also include the use of Group By.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    INVOICEID, subject, sum(quantity*UNITPRICE) as invoice_subtotal
from
     INVOICE inner join INVOICELINE I on INVOICE.INVOICEID = I.INVOICE_INVOICEID
group by
    invoiceid, subject
```

#### Results

|INVOICEID |SUBJECT                           |INVOICE_SUBTOTAL|
|----------|----------------------------------|----------------|
|1|Purdue Analytics Consultation Sale|480             |
|3|DataTech Server Lease             |6               |
|6|Pied Piper Legal Fees             |10000           |
|8|Optimoji Messaging Service        |300             |
|5|DataTech Fake SQL Data            |375             |
|10|Sliceline Pizza                   |200             |
|4|DataTech Employee Laptops         |600             |
|2|DataTech Equipement Purchase      |6660            |
|7|Endframe License                  |300             |
|9|Sliceline Pizza                   |200             |



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

Pranav Bhusari

#### SQL Statment

```SQL
select
    manufacturerer
from
    inventory_item
union
select
    accountName
from
    account;
```

#### Results

|MANUFACTURERER         |
|-----------------------|
|Breem Hall             |
|DataTech               |
|Dell                   |
|EndFrame               |
|Endframe               |
|FastFit                |
|LG                     |
|MSI                    |
|Monoprice              |
|Optimoji               |
|Pete Gregory Foundation|
|Pied Piper             |
|Purdue Analytics       |
|Purdue Fed             |
|Raspi Foundation       |
|Sandisk                |
|Seagate                |
|SliceLine              |
|Sliceline              |



### Task 21

Use INTERSECT to find common values between two tables.

#### Assigned to

Pranav Bhusari

#### SQL Statment

```SQL
select
    description
from
    inventory_item
intersect
select
    itemdescription
from
    receving_report_line;
```

#### Results

|DESCRIPTION|
|-----------|
|Pizza      |


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
