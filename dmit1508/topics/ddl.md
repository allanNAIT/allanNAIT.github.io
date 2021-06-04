---
layout: page
title: Data Definition Language (DDL)
---

## Basic Table Definition
* Data are stored in tables
* A table is a _2D array_ and consists of rows & columns:
  * Each `column` records **one attribute**
  * Each `row` records **all** attributes for **one instance**
* In SQL we use `CREATE TABLE` statements to create a table object in a database, which includes:
  * The `name` of the `table`
  * The `name` of each `column`
  * The [`data type`](../references/sql-data-types.md) of each `column`
  * Whether `NULL` is a **acceptable value** for the`column`
  * Any othere `CONSTRAINT`S that must hold **true** for a column

## CREATE TABLE Syntax

```sql
CREATE TABLE TableName (
    Column1 DATATYPE [IDENTITY [(seed, increment)]] | [NULL | NOT NULL] [<column constraints>],
    Column2 DATATYPE [IDENTITY [(seed, increment)]] | [NULL | NOT NULL] [<column constraints>],
    Column3 DATATYPE[IDENTITY [(seed, increment)]] | [NULL | NOT NULL] [<column constraints>],
    ...  
    [<table constraints>]
) 
```

OR

```sql
CREATE TABLE TableName (
    Column1 DATATYPE,
    Column2 DATATYPE,
    Column3 DATATYPE,
    ...  
) 
```

For example, using the ERD<br>
![create-table-example-erd.jpg](images/create-table-example-erd.jpg)

We can write the table creation SQL as follows:

```sql
-- Create the Customers table
CREATE TABLE Customers (
	CustomerNumber	       INT IDENTITY(1,1)	NOT NULL,
	LastName		VARCHAR(100)		NOT NULL,
	FirstName		VARCHAR(100)		NOT NULL,
	Phone			CHAR(8)		       NULL
)

-- Create the Orders table
CREATE TABLE Orders (
	OrderNumber		INT IDENTITY(1,1)	NOT NULL,
	OrderDate		SMALLDATETIME		NOT NULL,
	CustomerNumber	       INT			NOT NULL,
	Subtotal		MONEY			NOT NULL,
	GST			MONEY			NOT NULL,
	Total 	 		MONEY			NOT NULL
)

-- Create the Items table
CREATE TABLE Items (
	ItemNumber		INT IDENTITY(1,1)	NOT NULL,
	Description	       VARCHAR(100)		NOT NULL,
	CurrentPrice	       SMALLMONEY		NOT NULL
)

-- Create the ItemsOnOrder table
CREATE TABLE ItemOnOrder (
	OrderNumber		INT			NOT NULL,
	ItemNumber		INT			NOT NULL,
	Quantity		SMALLINT		NOT NULL,	
	Price			SMALLMONEY		NOT NULL,
	Amount 			MONEY			NOT NULL
)
```

## Verifying Your Table
After a table has been created, use the system Stored Procedure `SP_HELP` to list the table definition.

The syntax to run a Stored Procedure is:

```sql
EXEC ProcedureName [parameter1, parameter2, ...]
```

So, the syntax to run this Stored Procedure is:

```sql
EXEC SP_HELP Customers
```


### [DMIT1508 Home](../)