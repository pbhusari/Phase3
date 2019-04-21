# Phase 3 Select * Statments

## Team 11

Pranav Bhusari

Scott Luntz

Myles Lesser

Justin Walshager

Matt Quigley


## CNIT 272

Dawn Laux

Seciton 001


## Note

Tables may be out of order in results due to dataGrip reporting in hirearchical creation/deletion order instead of alphabetical selection order.

## SQL Statment

```sql
select * from INVOICELINE;

select * from PAYMENT;

select * from INVOICE;

select * from ACCOUNT;

select * from RECEVING_REPORT_LINE;

select * from RECEVING_RECIEPT;

select * from SHIPMENT;

select * from PURCHASE_ORDER_LINE;

select * from PURCHASE_ORDER;

select * from EMPLOYEE;

select * from DEPARTMENT;

select * from STOCKPILE;

select * from  INVENTORY_ITEM;

select * from  WAREHOUSE;


```

## Result

|ACCOUNTID |ACCOUNTNAME            |ACCOUNTNUMBER|ACCOUNTROUTINGNUMBER|ACCOUNTDESCRIPTION|
|----------|-----------------------|-------------|--------------------|------------------|
|1|Purdue Fed             |77687        |985                 |Personal          |
|2|Breem Hall             |87686        |112                 |Investor          |
|3|Pete Gregory Foundation|24828        |564                 |Investor          |
|4|Pied Piper             |15971        |546                 |Client            |
|5|Endframe               |31804        |329                 |Client            |
|6|DataTech               |22071        |684                 |Company           |
|7|FastFit                |64777        |645                 |Client            |
|8|SliceLine              |81634        |321                 |Client            |
|9|Optimoji               |31358        |215                 |Client            |
|10|Purdue Analytics       |6131         |798                 |Client            |


|DEPARTMENTID|BUILDING      |DESCRIPTION    |DUTIES                                                      |
|------------|--------------|---------------|------------------------------------------------------------|
|SHIP        |200 North Side|Shipping       |Send outgoing packages                                      |
|REC         |200 North Side|Receving       |Receving incoming packages                                  |
|ACCT        |200 North Side|Accounting     |Account for losses/gains                                    |
|MGMT        |120 South St  |Management     |Act as an intermediary between execs and low level employees|
|PAY         |120 South St  |Payment        |Draft invoices                                              |
|INV         |200 North Side|Inventory      |Update Inventory                                            |
|TECH        |110 South St  |Technology     |Keep tech working how its supposed to work                  |
|SALES       |100 South St  |Sales          |Meet potential customers and turn them into customers       |
|HR          |100 South St  |Human Resources|Fire people                                                 |
|EXEC        |100 South St  |Executive      |Make descisions about the company                           |


|EMPLOYEEID|FIRSTNAME |LASTNAME|HIREDATE           |PHONENUMBER|ADDRESS                         |DEPARTMENT_DEPARTMENTID|SALARY|BONUS|RAISE|EMAIL                |
|----------|----------|--------|-------------------|-----------|--------------------------------|-----------------------|------|-----|-----|---------------------|
|0014|John      |Smith   |2019-04-18 23:32:48|2055551338 |1 Infinite Loop                 |TECH                   |100.00|0.00 |0.00 |jsmith@dataTech.co   |
|0001|Christian |Chandler|2019-04-06 19:23:30|2025550139 |366 Brookside Court Florence    |TECH                   |100.00|     |0.01 |cchandler@dataTech.co|
|0002|Patrick   |Bateman |1999-11-06 19:23:36|2025550101 |8287 Kent Ave. owosso           |EXEC                   |120.00|     |0.01 |pbateman@dataTech.co |
|0003|Huey      |Lewis   |2001-04-02 19:23:51|2025550107 |7778 High Point Ave. Willoughby |SHIP                   |60.00 |     |0.01 |hlewis@dataTech.co   |
|0004|Paul      |Allen   |2018-09-06 19:24:15|2025550187 |8974 Argyle Court South Portland|TECH                   |100.00|     |0.01 |pallen@dataTech.co   |
|0005|Andrew    |Yang    |2015-10-11 19:24:24|2025550183 |8526 Gartner St. West Warwick   |HR                     |70.00 |     |0.01 |ayang@dataTech.co    |
|0006|Donald    |Sanders |2001-11-27 19:24:32|2025550133 |9498 Vermont Ave. Oak Park      |PAY                    |30.00 |     |0.00 |dsanders@dataTech.co |
|0007|Bernie    |Trump   |2013-11-20 19:24:47|2025550119 |9837 Wild Rose Lane Metairie    |TECH                   |100.00|     |0.01 |btrump@dataTech.co   |
|0008|Alexandria|Ramerez |2012-06-11 19:25:17|2025550132 |176 Mill Pond Ave.              |TECH                   |120.00|     |0.00 |aramerez@dataTech.co |
|0009|Ricardo   |Chandler|2013-09-27 19:25:28|2025550167 |279 Galvin St. Sicklerville     |MGMT                   |70.00 |     |0.01 |rchandler@dataTech.co|
|0010|Christian |Chantor |2014-08-13 19:25:36|2025550137 |15 Railroad Ave. Lenoir         |REC                    |30.00 |     |0.01 |cchantor@dataTech.co |
|0011|Myles     |Lesser  |2013-04-09 19:39:28|2023214030 |14 Ross Ade Dr.                 |REC                    |10.00 |     |     |mlesser@dataTech.co  |
|0012|Pranav    |Bhusari |2012-06-13 19:39:34|2025551489 |15 Tarkington Bolevard          |REC                    |30.00 |     |     |pbhusari@dataTech.co |


|ITEMID    |DESCRIPTION        |QUANTITY|HEIGHTINCHES|WIDTHINCHES|LENGTHINCHES|WEIGHTPOUND|MANUFACTURERER  |
|----------|-------------------|--------|------------|-----------|------------|-----------|----------------|
|1|Pizza              |10      |1           |24         |24          |3          |Sliceline       |
|2|Monitor            |10      |9           |16         |3           |20         |LG              |
|3|Desktop Computer   |3       |12          |6          |12          |20         |MSI             |
|4|Laptop Computer    |2       |5           |12         |2           |2          |Dell            |
|5|EndFrame License   |2       |            |           |            |           |EndFrame        |
|6|Raspberry pi       |30      |5           |3          |1           |0.5        |Raspi Foundation|
|7|Micro USB Cable    |30      |2           |5          |2           |0.5        |Monoprice       |
|8|32 GB SD Card      |30      |1           |2          |1           |0.1        |Sandisk         |
|9|1 TB SSD           |5       |2           |3          |5           |0.1        |Sandisk         |
|10|Thunderbolt Adapter|10      |2           |5          |2           |0.5        |Monoprice       |
|11|Headphones         |10      |12          |32         |12          |5          |Monoprice       |
|12|Ultrawide Monuitors|10      |50          |20         |30          |10         |Monoprice       |
|13|gaming PC          |12      |20          |6          |12          |50         |MSI             |

|INVOICEID |ISSUEDATE          |DUEDATE            |SUBJECT                           |PURCHASE_ORDER_ORDERID|
|----------|-------------------|-------------------|----------------------------------|----------------------|
|1|2014-04-07 19:31:06|2014-05-07 19:31:06|Purdue Analytics Consultation Sale|1                     |
|2|2014-05-08 19:31:34|2014-06-08 19:31:34|DataTech Equipement Purchase      |2                     |
|3|2014-09-15 19:32:13|2014-11-15 19:32:13|DataTech Server Lease             |3                     |
|4|2014-10-07 19:32:54|2014-11-07 19:32:54|DataTech Employee Laptops         |4                     |
|5|2014-12-05 19:33:23|2015-01-05 19:33:23|DataTech Fake SQL Data            |5                     |
|6|2015-01-08 19:34:41|2015-10-08 19:34:41|Pied Piper Legal Fees             |6                     |
|7|2016-08-09 19:35:31|2016-11-09 19:35:31|Endframe License                  |7                     |
|8|2017-09-11 19:35:48|2017-10-11 19:35:48|Optimoji Messaging Service        |8                     |
|9|2018-08-12 19:36:08|2018-09-12 19:36:08|Sliceline Pizza                   |9                     |
|10|2019-02-07 19:36:52|2019-03-07 19:36:52|Sliceline Pizza                   |10                    |


|INVOICE_INVOICEID|INVOICELINEID|ITEMTYPE|DESCRIPTION                           |QUANTITY|UNITPRICE|TAX |
|-----------------|-------------|--------|--------------------------------------|--------|---------|----|
|1                |1            |Service |Consultation Fee                      |2       |15       |0   |
|1                |2            |Product |Monitors Sold                         |3       |150      |0.08|
|2                |1            |Product |Desktop Computers                     |10      |666      |0.08|
|3                |1            |Service |Server Space Rent                     |12      |0.5      |0   |
|4                |1            |Product |Laptops Sold For DataTech Equipment   |2       |300      |0.08|
|5                |1            |Service |Fake data population                  |5       |75       |0   |
|6                |1            |Service |Pied Piper Legal Fees, lawyer hours   |10      |1000     |0   |
|7                |1            |Product |Endframe licensing fee for 2 computers|2       |150      |0.08|
|8                |1            |Service |Messaging service, quantity per client|30      |10       |0.01|
|9                |1            |Product |Pizza                                 |10      |5        |0.08|
|10               |1            |Product |Pizza                                 |10      |5        |0.08|
|10               |2            |Product |Pizza                                 |10      |5        |0.08|
|10               |3            |Product |Pizza                                 |10      |5        |0.08|
|10               |4            |Product |Pizza                                 |10      |5        |0.08|
|9                |2            |Product |Pizza                                 |10      |5        |0.08|
|9                |3            |Product |Pizza                                 |10      |5        |0.08|
|9                |4            |Product |Pizza                                 |10      |5        |0.08|


|ACCOUNT_ACCOUNTID|PAYMENTID |METHOD           |PAYMENTDATE        |PAYMENTRECIVETIME  |PAYMENTAMOUNT|INVOICE_INVOICEID|
|-----------------|----------|-----------------|-------------------|-------------------|-------------|-----------------|
|10               |1|Client Checking  |2014-04-07 21:31:06|2019-04-10 22:10:27|516          |1                |
|1                |10|Credit Card      |2019-02-07 21:36:52|2019-02-07 22:36:52|113          |10               |
|2                |11|Checking         |2019-02-07 21:36:52|2019-02-07 22:36:52|113          |10               |
|1                |2|Investor Checking|2014-05-08 21:31:34|2014-05-08 23:31:34|7192.8       |2                |
|3                |3|Investor Checking|2014-09-15 21:32:13|2019-04-10 22:11:25|6            |3                |
|2                |4|Investor Checking|2014-10-07 21:32:54|2019-04-10 22:11:22|648          |4                |
|3                |5|Investor Checking|2014-12-05 21:33:23|2019-04-10 22:11:19|375          |5                |
|2                |6|Investor Checking|2015-01-08 21:34:41|2019-04-10 22:11:15|500          |6                |
|3                |12|Investor Checking|2015-01-08 21:34:41|2019-04-10 22:11:15|500          |6                |
|2                |7|Investor Checking|2016-08-09 21:35:31|2019-04-10 22:11:10|324          |7                |
|2                |8|Investor Checking|2016-08-09 22:35:31|2019-04-13 22:05:19|203          |8                |
|4                |13|Checking         |2016-08-09 22:35:31|2019-04-13 22:05:19|203          |8                |
|1                |9|Credit Card      |2018-08-16 19:36:08|2018-08-16 20:36:08|108          |9                |
|1                |14|Credit Card      |2018-08-16 19:36:08|2018-08-16 20:36:08|108          |9                |


|ORDERID   |Date               |DELIVERYDATE       |EMPLOYEE_EMPLOYEEID|
|----------|-------------------|-------------------|-------------------|
|1|2014-04-07 19:31:06|2014-04-10 19:31:16|0003               |
|2|2014-05-08 19:31:34|2014-05-11 19:31:43|0003               |
|3|2014-09-15 19:32:13|2014-09-09 19:32:22|0003               |
|4|2014-10-07 19:32:54|2014-10-11 19:33:02|0003               |
|5|2014-12-05 19:33:23|2014-12-18 19:33:52|0003               |
|6|2015-01-08 19:34:41|2019-01-11 19:34:52|0002               |
|7|2016-08-09 19:35:31|2016-08-14 19:35:41|0002               |
|8|2017-09-11 19:35:48|2017-09-13 19:35:59|0003               |
|9|2018-08-12 19:36:08|2018-08-11 19:36:43|0003               |
|10|2019-02-07 19:36:52|2019-02-14 19:36:58|0003               |
|11|2017-07-08 19:45:48|2019-07-10 19:45:56|0003               |


|PURCHASE_ORDER_ORDERID|ORDERLINEID|ESITMATEDITEMPRICE|ITEMQUANTITY|INVENTORY_ITEM_ITEMID|
|----------------------|-----------|------------------|------------|---------------------|
|10                    |1          |10.5              |10          |1                    |
|10                    |2          |9                 |10          |1                    |
|10                    |3          |10                |10          |1                    |
|10                    |4          |10.6              |10          |1                    |
|9                     |1          |8.8               |10          |1                    |
|9                     |2          |10                |10          |1                    |
|9                     |3          |10                |10          |1                    |
|1                     |1          |150               |3           |2                    |
|2                     |1          |600               |5           |3                    |
|4                     |1          |315               |2           |4                    |
|7                     |1          |150               |2           |5                    |

|RECEVINGRECIEPTID|SHIPMENT_SHIPMENTID|EMPLOYEE_EMPLOYEEID|SHIPPINGDOCK|DATERECIVED        |
|-----------------|-------------------|-------------------|------------|-------------------|
|RR1              |1                  |0010               |Dock A      |2014-04-11 19:31:06|
|RR2              |4                  |0010               |Dock A      |2014-04-17 19:31:06|
|RR3              |5                  |0012               |Dock C      |2014-04-26 19:31:06|
|RR4              |6                  |0012               |Dock C      |2014-10-18 19:32:54|
|RR5              |7                  |0010               |Dock A      |2014-10-22 19:32:54|
|RR6              |8                  |0012               |Dock C      |2016-08-18 19:35:31|
|RR7              |9                  |0012               |Dock C      |2017-07-21 19:45:48|
|RR8              |10                 |0012               |Dock C      |2017-08-08 19:45:48|
|RR9              |2                  |0011               |Dock C      |2014-09-09 19:31:06|
|RR10             |3                  |0011               |Dock D      |2014-09-16 19:31:06|


|RECEVINGREPORTLINEID|RECEVINGRECIEPTID|ITEMDESCRIPTION                       |ITEMQUANTITY|ITEMPRICE|
|--------------------|-----------------|--------------------------------------|------------|---------|
|1                   |RR9              |Pizza                                 |9           |4        |
|4                   |RR9              |Pizza                                 |10          |5        |
|3                   |RR9              |Pizza                                 |8           |4.99     |
|2                   |RR9              |Pizza                                 |10          |5        |
|1                   |RR7              |Endframe licensing fee for 2 computers|2           |150      |
|1                   |RR4              |Laptops Sold For DataTech Equipment   |2           |300      |
|1                   |RR2              |Desktop Computers                     |10          |666      |
|1                   |RR10             |Pizza                                 |15          |5        |
|4                   |RR10             |Pizza                                 |10          |5        |
|3                   |RR10             |Pizza                                 |10          |5        |
|2                   |RR10             |Pizza                                 |10          |5        |


|SHIPMENTID|Date               |PURCHASE_ORDER_ORDERID|SUPPLIER        |FULFILMENTMETHOD|DROPLOCATION|PRICEPERPOUND|WEIGHT|
|----------|-------------------|----------------------|----------------|----------------|------------|-------------|------|
|1|2014-04-07 19:31:06|1                     |Alibaba         |Over Land       |Warehouse   |1            |20    |
|4|2014-04-07 19:31:06|9                     |Berts Pizza     |Delivery        |Office      |5            |1     |
|5|2014-04-07 19:31:06|10                    |Berts Pizza     |Delivery        |Office      |5            |1     |
|6|2014-10-07 19:32:54|4                     |Yang's Laptops  |Over Land       |Warehouse   |0.5          |10    |
|7|2014-10-10 19:32:54|4                     |Yang's Laptops  |Over air        |Office      |2            |10    |
|8|2016-08-09 19:35:31|7                     |EndFrame        |Electronic      |Office      |0            |0     |
|9|2017-07-08 19:45:48|11                    |Sandisk Consumer|Over Land       |Warehouse   |0.75         |3     |
|10|2017-07-08 19:45:48|11                    |Sandisk Consumer|Over Land       |Office      |0.75         |3     |
|2|2014-04-07 19:31:06|10                    |Berts Pizza     |Delivery        |Office      |5            |1     |
|3|2014-04-07 19:31:06|1                     |Alibaba         |Over Land       |Warehouse   |1            |20    |
|11|2014-05-08 19:31:34|2                     |Alibaba         |Over Land       |Warehouse   |2            |10    |


|INVENTORY_ITEM_ITEMID|WAREHOUSE_WAREHOUSEID|LASTINVENTORYCHECKDATE|QUANTITY|
|---------------------|---------------------|----------------------|--------|
|1                    |9                    |2019-04-05 17:29:16   |5       |
|1                    |9                    |2019-04-06 17:29:48   |5       |
|1                    |2                    |2019-04-06 17:29:54   |7       |
|2                    |3                    |2019-04-05 17:29:57   |6       |
|2                    |3                    |2019-04-03 17:30:02   |20      |
|2                    |4                    |2019-03-08 17:30:32   |10      |
|7                    |7                    |2019-04-03 17:30:43   |2       |
|1                    |6                    |2019-01-06 17:30:49   |7       |
|1                    |10                   |2019-04-07 17:35:36   |3       |


|WAREHOUSEID|STREETADDRESS           |STATE|CITY           |ZIPCODE |NAME                                 |DATEESTABLISHED    |
|-----------|------------------------|-----|---------------|--------|-------------------------------------|-------------------|
|1          |617 Gann Rd             |TN   |Milan          |38358   |FIrst warehouse                      |1998-04-08 17:24:54|
|2          |612 2nd St              |NC   |Fairmont       |28340   |DateaTech WorldHub                   |2013-04-13 17:25:00|
|3          |13137 E 2nd St          |IA   |Moulton        |52572   |DataTech MainStorage                 |2001-09-15 17:25:12|
|4          |10600 E 640th S         |IN   |Hudson         |46747   |DataTech Consumer Resources Warehouse|2005-10-22 17:25:30|
|5          |12546 Oxnard St         |CA   |North Hollywood|91606|DataTech Furniture Storage           |2016-10-23 17:25:42|
|6          |2215 73rd St E #LOT 147,|FL   |Palmetto       |34221   |DataTech SmartWareHouse              |2006-06-19 17:26:14|
|7          |15853 Lawton St         |MI   |Detroit        |48238|DataTech GreenHouse                  |2014-09-12 17:26:34|
|8          |223 S Fraley St         |PA   |Kane           |16735|DataTech SmartGreenHouse             |2015-10-08 17:26:24|
|9          |11539 Padgett Switch Rd |AL   |Irvington      |36544   |DataTechPizzaStorage                 |2019-08-14 17:26:43|
|10         |611 N Cottage Ave       |MT   |Miles City     |59301   |DataTech Technology resource center  |2019-04-06 17:26:52|
