---
layout: page
title: SQL Keywords
---

Here is a list of SQL Keywords that we will learn

## A
* `ALL` can be added to a `UNION` to include duplicates, or lets us compare to multiple values in a subquery.
* `ALTER PROCEDURE` replaces the previously saved query in a stored procedure.
* `ALTER TABLE` lets us make changes to a table that already exists, like adding an a new column or constraint. The DDL page explains exactly what types of changes we can make.
* `ALTER TRIGGER` replaces the SQL in an existing trigger with new logic.
* `ALTER VIEW` lets us replace the query defining a view with a new query.
* `AND` is used between two boolean expressions, if we need both expressions to be true. You need a full and complete expression on **both** sides of `AND`.
* `ANY` compares against any of the values: `WHERE Grade > ANY (SELECT Grade … )`
* `AVG()` is a function that returns the average of numeric values.

## B
* `BEGIN TRANSACTION` marks the beginning of a transaction. This is the point we come back to if the `TRANSACTION` is later `ROLL`ed `BACK`.
* `BETWEEN` will return records between 2 values, including those 2 values: e.g., `WHERE Mark BETWEEN 50 AND 100`

## C
* `COMMIT TRANSACTION` marks the end of the transaction, and makes everything that happened since `BEGIN TRANSACTION` permanent.
* `CONSTRAINT`s can be added to define the Primary Key, Foreign Key, any default values, or conditions a column has (e.g., what values are allowed, or what format the value must be in). More on constraints on the [DDL page](../ddl.md).
* `COUNT(*)` returns the number of rows in a query.
* `COUNT(ColumnName)` returns the number of non-null values in the specified column.
* `CREATE NONCLUSTERED INDEX` lets us create a new index, which speeds up data retrieval.
* `CREATE PROCEDURE` lets us create a set of SQL statements that is stored in the database, and can be run as needed. Check out the [Stored Procedures](../stored-procedues.md) page for more info.
* `CREATE TABLE` creates the structure for a new table in our database (see [DDL page](../ddl.md) for syntax)
  * `IDENTITY(seed, increment)` is what we add to each column that is a technical key (i.e., SQL will generate the value for us)
* `CREATE TRIGGER` creates a new trigger that will be executed by a specific kind of DML statement on a specific table. Learn more on the [Triggers page](../triggers.md).
* `CREATE VIEW` lets us save a specific query, and `SELECT` from that view just like we select from a table. More on the [Views page](../views.md).

## D
* `DATEADD(xx, n, date1)` adds `n` `xx` to `date1` (`n` may be negative). See the [Queries page](../queries.md) for possible values for `xx`.
  * e.g., `DATEADD(yy, 5, HireDate)` returns the date 5 years after the `HireDate`.
* `DATEDIFF(xx, date1, date2)` returns the number of `xx` from `date1` to `date2`. See the [Queries page](../queries.md) for possible values for `xx`.
  * e.g., `DATEDIFF(dd, OrderDate, ShipDate)` returns the number of days between `OrderDate` and `ShipDate`.
* `DATENAME(xx, date1)` returns a string representation of the `xx` of `date1`. See the [Queries page](../queries.md) for possible values for `xx`.
  * e.g., `DATENAME(dw, '2020-01-01')` returns `Wednesday`.
* `DATEPART(xx, date1)` returns integer representation of the `xx` of `date1`. See the [Queries page](../queries.md) for possible values for `xx`.
  * e.g., `DATEPART(mm, '2020-03-01')` returns `3` because March is the 3rd month of the year.
  * `YEAR(date1)` functions the same as `DATEPART(yy, date1)`
    * e.g., `YEAR('2020-03-01')` returns `2020`.
  * `MONTH(date1)` functions the same as `DATEPART(mm, date1)`
    * e.g., `MONTH('2020-03-01')` returns `3`.
  * `DAY(date1)` functions the same as `DATEPART(dd, date1)`
    * e.g., `DAY('2020-03-01')` returns `1`.
* `DECLARE` lets us create a new variable: e.g., `DECLARE @FirstName VARCHAR(10), @LastName VARCHAR(20)`.
* `DELETE` statements remove record(s) from a table. More on the [DML page](../dml.md). e.g., `DELETE FROM Student WHERE GraduationStatus = 'Y'`.
* `DISTINCT` can be added to a `SELECT` or `COUNT()` to only count **unique** rows or values.
* `DROP INDEX` deletes an index from the database.
* `DROP PROCEDURE` deletes a stored procedure.
* `DROP TABLE` deletes a table from the database: both its structure AND its contents.
  * If you DROP a table that has triggers associated with it, the triggers are dropped as well.
* `DROP TRIGGER` deletes a trigger from the database.
* `DROP VIEW` deletes a view from the database.

## E
* `EXEC ProcedureName ParameterName` is how we execute a stored procedure called ProcedureName with a parameter called ParameterName. Some SPs have no parameters, some have one, some have many: if we have multiple parameters, we separate them with commas like this: `EXEC ProcedureName Param1, Param2`.
  * e.g., `EXEC sp_help Customers` runs the `sp_help` on the `Customers` table.
  * e.g. `EXEC sp_helptext CustomerView` runs `sp_helptext` on the `CustomerView` view. It can also be used to get the definition of [triggers](../triggers.md)!

  ## G
* `GETDATE()` returns the current datetime (i.e., today’s date).
* `GO` is a batch terminator. It basically says, “Hey SQL, execute up to this point. Everything after this point is a separate batch.”

## I
* `IF` is a conditional statement: the code within an `IF` block will only run if its condition evaluates to true. Optionally, an `IF` statement may have an `ELSE` block: that code will only run if the original condition evaluates to **false**.
* `IF EXISTS (...)` will run the query in parentheses, and will return true if at least one record is returned. This is helpful to check if there are existing records to `UPDATE` or `DELETE` before trying to `UPDATE` or `DELETE` them.
* `IN` lets us check for an exact match within a list of values. e.g., `WHERE StudentID IN (20001, 20002, 20004)`.
* `INSERT` lets us add a new row (or rows) to a table. We can add using hardcoded values, the results of a subquery, or the results of a `SELECT` statement! More on the [DML page](../dml.md). Some examples:

```sql
    INSERT INTO Staff (FirstName,LastName)
    VALUES ('Bob','Smith'),
           ('Bob','Jones') -- inserting 2 rows in a single INSERT
```

```sql
    INSERT INTO Item (ItemID,
                      ItemName,
                      Cost,
                      Description)
    VALUES (123,
            'Whatchamacallit',
            SELECT AVG(Cost) FROM Item -- INSERTing a value from a subquery,
            NULL)
```

```sql
    INSERT INTO Student(FirstName,LastName)
    SELECT FirstName,Lastname FROM Employee
    -- this is essentially copying values from one table to another
```

## J
* `JOIN` lets us join data from multiple tables.
  * `table1 INNER JOIN table2` returns only **records that exist in both tables**.
    * If you are joining a parent to child, OR child to parent, you will only get **records for parents** that have child records.
  * `table1 LEFT JOIN table2` returns **all records in table1**, regardless of whether they exist in table2.
    * If you are joining parent to child, you will get **parents regardless of whether they have child records**.
    * If you are joining child to parent, you will get only child records, so you **should use `INNER JOIN` instead**.
  * `table1 RIGHT JOIN table2` returns **all records in table2**, regardless of whether they exist in table1.
    * If you qre joining parent to child, you will get only child records, so you **should use `INNER JOIN` instead**.
    * If you are joining child to parent, you will get **parents regardless of whether they have child records**.
  * `table1 FULL OUTER JOIN table2` returns all records that exist in either table.
    * If you are joining parent to child, you will get parents regardless of whether they have child records, so you **should use `LEFT JOIN` instead**.
    * If you are joining child to parent, you will get parents regardless of whether they have child records, so you **should use `RIGHT JOIN` instead**.
  * How to pick a `JOIN` type:
    | Joining Parent to Child | Joining Child to Parent
----|-------------------------|------------------------
`INNER` | only records for parents that have child records | only records for parents that have child records
`LEFT` | parents regardless of whether they have child records | use _`INNER JOIN`_ instead