# INTRODUCTION TO SQL

## Exercises

In this intro to SQL we will use an online SQL editor: [https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all)

There are already some tables in this Database: (Categories, Employees, OrderDetails	, Orders, Products, Shippers, and Suppliers). We are not going to use them, and if you want you can drop them by running `DROP TABLE [table name];`



## Dogs

Everyone loves dogs, so now we will now play around with some dogs.

First create a table called parents. It has two columns: 'parent' and 'child'. The first column indicates the parent of the child in the second column. We will use a new form of `CREATE TABLE` expression to produce this table.

	CREATE TABLE parents AS
	  SELECT "abraham" AS parent, "barack" AS child UNION
	  SELECT "abraham",           "clinton"         UNION
	  SELECT "delano",            "herbert"         UNION
	  SELECT "fillmore",          "abraham"         UNION
	  SELECT "fillmore",          "delano"          UNION
	  SELECT "fillmore",          "grover"          UNION
	  SELECT "eisenhower",        "fillmore";
	  

### Picture of the Dog Family Tree

(A = abrham, B = barack, etc.)

<center><img src="https://github.com/alexanderfo/data-x_public/raw/master/L12_SQL/imgs/family_tree.png" width="200" /></center>
	  
## Q1 Simple SELECTS (on the parents table)
1. SELECT all records in the table.
2. SELECT all children that have abraham as parent.
3. SELECT all children that have an 'e' in their name.
4. SELECT all siblings from the parents table (see picture below)

.

.

.

.
*These exercises are inspired by the Lectures in CS61A (Fall 2014).*
