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