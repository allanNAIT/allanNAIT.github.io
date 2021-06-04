---
layout: page
title: Data Definition Language (DDL)
---

## Topics on this page:
* [Basic Table Definition](#basic)
* [CREATE TABLE Syntax](#create)
* [Verifying Your Table](#verify)
* [DROP Statement](#drop)
* [Constraints](#constraints)
  * [PK Constraints](#pk)
  * [FK Constraints](#fk)
  * [CHECK Constraints](#check)
  * [LIKE Operator](#like)
  * [Testing a CHECK Constratint](#testing)
  * [DEFAULT Constraint](#default)
* [Practice](#practice)

## <a ID="basic">Basic Table Definition</a>
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

## <a ID="create">CREATE TABLE Syntax</a>

```sql
CREATE TABLE TableName (
    Column1 DATATYPE [IDENTITY [(seed, increment)]] | [NULL | NOT NULL] [<column constraints>],
    Column2 DATATYPE [IDENTITY [(seed, increment)]] | [NULL | NOT NULL] [<column constraints>],
    Column3 DATATYPE [IDENTITY [(seed, increment)]] | [NULL | NOT NULL] [<column constraints>],
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

## <a ID="verify">Verifying Your Table</a>
After a table has been created, use the system Stored Procedure `SP_HELP` to list the table definition.

The syntax to run a Stored Procedure is:

```sql
EXEC ProcedureName [parameter1, parameter2, ...]
```

So, the syntax to run this Stored Procedure is:

```sql
EXEC SP_HELP Customers
```

## <a ID="drop">DROP Statement</a>
The `DROP TABLE` statement is used to **delete** a table (both is data and its definition). The syntax is:

```sql
DROP TABLE TableName
```

e.g., to drop the `Items` table:

```sql
DROP TABLE Items
```

**Practice**:
![ddl-practice-create.png](images/ddl-practice-create.png)

1. Create a script that will create the 3 tables above:<br>
    <ol type="a">
        <li>Use appropriate data types</li>
        <li>Do not worry about defining `PK`s or `FK`s</li>
        <li>Do not allow `NULL`s in any column</li>
        <li>`EmployeeID`s are 11 characters long</li>
        <li>Use the identity property for ProjectNumber in the Project table, but not in the EmployeeOnProject table (why?)</li>
    </ol>
2. List the table definition
3. Save your script

## <a ID="constraints">Constraints</a>
Constraints are used for:
1. Define the `PK`
  * This is defined by the [`PRIMARY KEY`](#pk)
2. Define **relationships**
  * This is defined by the [`FOREIGN KEY`](#fk) constraint
3. Define **defualt values**
  * Defined by the [`DEFAULT`](#default) constraint
4. Define the **domain of valid values**
  * Defined by the [`CHECK`](#check) constraint
5. Ensure that **all values in a column are unique**

### <a ID="pk">PK Constraints</a>

### <a ID="fk">FK Constraints</a>

### <a ID="check">CHECK Constraints</a>

### <a ID="like">LIKE Operator</a>

### <a ID="testing">Testing a CHECK Constraint</a>

### <a ID="default">DEFAULT Constraint</a>

## <a ID="practice">Practice</a>

### [DMIT1508 Home](../)