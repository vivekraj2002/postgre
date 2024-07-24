
<div style="text-align: center;">
  <h1>PostgreSQL</h1>
</div>

<div style="text-align: center;">
  <img src="./image/psql.jpg" alt="alt text" >
</div>

</br>


<h1 style="text-align: center;"> TAble of content </h1>

# PostgreSQL

1. [Introduction of PostgreSQL](#Introduction-of-PostgreSQL)
2. [What is Database](#What-is-Database)
3. [Database vs DBMS](#Database-vs-DBMS)
4. [What is RDBMS](#what-is-RDBMS)
5. [Installation of PostgreSQL](#Installation-of-PostgreSQL)
6. [What is CRUD](#What-is-CRUD)
7. [Datatypes and Constraint](#Datatypes-and-Constraint)
8. [Operators](#operators)
9. [Clause](#clause)
10. [JOINS](#JOINS)
11. [Conclusion](#Conclusion)
12. [Reference link](#Reference-link)


## Introduction of PostgreSQL

PostgreSQL is a powerful, open source object-relational database system that uses and extends the SQL language combined with many features that safely store and scale the most complicated data workloads.

Being an open-source software, its source code is available under PostgreSQL license, a liberal open source license. Anyone with the right skills is free to use, modify, and distribute PostgreSQL in any form. As it is highly stable, very low effort is required to maintain this DBMS.

## What is Database

A database is an organized collection of data, stored and accessed electronically. Databases are used to store and manage large amounts of structured and unstructured data, and they can be used to support a wide range of activities, including data storage, data analysis, and data management. 

<div style="text-align: center;">
  <img src="./image/database.png" alt="alt text" >
</div>

</br>

<!-- <div style="text-align: center;"> -->
  <img src="./image/table.png" alt="alt text" >
</div>

## Database vs DBMS

**Database:** A database is an organized collection of structured data or information, typically stored electronically in a computer system. It can include tables, queries, reports, views, and other objects that hold and manage data

Example :- Customer data (Name, Address & Contact No.)

</br>

**DBMS (Database Management System):** A Database Management System (DBMS) is software that helps manage and organize data. It lets users create, change, and query a database while also handling security and access controls.

A DBMS makes storing and retrieving data easy and efficient.

Example :- MySQL, PostgreSQL, MongoDB, Oracle Database. 
</br>

## What is RDBMS

A relational database management system (RDBMS) stores data in tables with rows and columns. It's widely used in industries due to its popularity. Each table has a key field called a primary key, which uniquely identifies each record. This primary key helps in referencing records easily. Examples of RDBMS include Oracle Database, MySQL, and Microsoft SQL Server.

## Installation of PostgreSQL

**Prerequisite for Installation**

The minimum hardware & software required to install and run PostgreSQL is:

  1. Pentium processor. </br>
  2. 4 GB of RAM.  </br>
  3. Ubuntu 20.04.6 LTS (Operating system) </br>
  4. 64 bit </br>
  5. 512 MB of HDD.</br>
  

**Steps for Installation of PostgreSQL**

***Step 1 :-***  Command for install PostgreSQL

``` sudo apt-get install postgresql```

### Output 

```
vivek@phdsec:~$ sudo apt-get install postgresql-16
Reading package lists... Done
Building dependency tree  	 
Reading state information... Done
postgresql-16 is already the newest version (16.3-1.pgdg20.04+1).
postgresql-16 set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 25 not upgraded
```

***Step 2 :-***  Import the repository signing key:

``` sudo apt install curl ca-certificates ```

### Output

``` sudo apt install curl ca-certificates
Reading package lists... Done
Building dependency tree  	 
Reading state information... Done
ca-certificates is already the newest version (20230311ubuntu0.20.04.1).
curl is already the newest version (7.68.0-1ubuntu2.22).
The following packages were automatically installed and are no longer required:
  linux-headers-5.15.0-105-generic linux-hwe-5.15-headers-5.15.0-105 linux-image-5.15.0-105-generic linux-modules-5.15.0-105-generic linux-modules-extra-5.15.0-105-generic
Use 'sudo apt autoremove' to remove them.
```
***Step3 :-*** Create the repository configuration file:

``` 
 sudo sh -c 'echo "deb [signed-by=/usr/share/postgresql-common/pgdg/apt.postgresql.org.asc] https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
```

***step4 :-*** ``` psql --version ```

### Output

``` vivek@phdsec:~$ psql --version
psql (PostgreSQL) 16.3 (Ubuntu 16.3-1.pgdg20.04+1)
```


## Installation of pgadmin

We can use pgAdmin to do everything from writing basic SQL queries to monitoring our databases and configuring advanced database architectures 

***Step1 :-*** Install the public key for the repository (if not done previously):

```curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg```


***Step2 :-*** Create the repository configuration file:

```
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```

### Output

```vivek@phdsec:~$ sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
Hit:1 https://brave-browser-apt-release.s3.brave.com stable InRelease
Hit:2 https://deb.nodesource.com/node_20.x nodistro InRelease            	 
Get:3 https://packages.microsoft.com/repos/code stable InRelease [3,590 B]    
Hit:4 http://in.archive.ubuntu.com/ubuntu focal InRelease                	 
Get:5 https://packages.microsoft.com/repos/code stable/main arm64 Packages [17.5 kB]
Get:34 http://security.ubuntu.com/ubuntu focal-security/universe Translation-en [208 kB]
Fetched 13.6 MB in 14s (1,006 kB/s)                                      	 
Reading package lists... Done
Building dependency tree  	 
Reading state information... Done
5 packages can be upgraded. Run 'apt list --upgradable' to see them.
N: Skipping acquire of configured file 'main/binary-i386/Packages' as repository 'https://brave-browser-apt-release.s3.brave.com stable InRelease' doesn't support architecture 'i386'
N: Skipping acquire of configured file 'main/binary-i386/Packages' as repository 'https://apt.postgresql.org/pub/repos/apt focal-pgdg InRelease' doesn't support architecture 'i386'
```



***Step3 :-*** ```sudo apt install pgadmin4```

### Output

``` 
vivek@phdsec:~$ sudo apt install pgadmin4
[sudo] password for vivek:
Reading package lists... Done
Building dependency tree  	 
Reading state information... Done
The following packages were automatically installed and  are no longer required:
  linux-headers-5.15.0-105-generic linux-hwe-5.15-headers-5.15.0-105
  linux-image-5.15.0-105-generic linux-modules-5.15.0-105-generic
  linux-modules-extra-5.15.0-105-generic
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  libapache2-mod-wsgi-py3 pgadmin4-desktop pgadmin4-server pgadmin4-web
The following NEW packages will be installed:
  libapache2-mod-wsgi-py3 pgadmin4 pgadmin4-desktop pgadmin4-server
pgadmin4-web
Setting up pgadmin4 (8.9) ...
Processing triggers for mime-support (3.64ubuntu1) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
Processing triggers for gnome-menus (3.36.0-1ubuntu1) ...
Processing triggers for desktop-file-utils (0.24-1ubuntu3) ...
```

***Step4 :-*** Configure the web server, if We installed pgadmin4-web

``` sudo /usr/pgadmin4/bin/setup-web.sh```

#### Output

```
vivek@phdsec:~$ sudo /usr/pgadmin4/bin/setup-web.sh
Setting up pgAdmin 4 in web mode on a Debian based platform...
Creating configuration database...
Email address: vivekraj746189@gmail.com
Password:
Retype password:
pgAdmin 4 - Application Initialisation
======================================

Creating storage and log directories...
We can now configure the Apache Web server for you. This involves enabling the wsgi module and configuring the pgAdmin 4 application to mount at /pgadmin4. Do you wish to continue (y/n)? y
The Apache web server is running and must be restarted for the pgAdmin 4 installation to complete. Continue (y/n)? y
Apache successfully restarted. You can now start      using     pgAdmin 4 in web mode at http://127.0.0.1/pgadmin4
```

   ***step5 :-*** Open file of pgadmin & change password

   Open file of pgadmin

   ```
   vivek@phdsec:~$ sudo -i -u postgres
   [sudo] password for vivek: 
   direct://
   postgres@phdsec:~$ psql
   psql (16.3 (Ubuntu 16.3-1.pgdg20.04+1))
   Type "help" for help.

   postgres=# ^C
   postgres=# 
   ```
  
   Change Password

   ```
   postgres=# \password
   Enter new password for user "postgres":
   Enter it again:
  ```
   ## What is CRUD

   CRUD stands for Create, Read, Update, and Delete. These are the four basic operations that can be performed on data in a database or a data store. Here’s a brief explanation of each operation:

   **Firstly we will create a database for creating a  table to perform CRUD operation**

   <div style="text-align: center;">
   <img src="./image/database1.png" alt="alt  text" >
   </div> </br>

   ***1. Create :-***

   This operation is used to add new records or data to a database.
   Example: 
   INSERT INTO table_name (column1, column2, ...)</br> VALUES (value1, value2, ...);

   **Input Query**

   <div style="text-align: center;">
   <img src="./image/Craete input.png" alt="alt    text" >
   </div>

   **Output**

   <div style="text-align: center;">
   <img src="./image/create output .png" alt="alt text" >
   </div>

   **Create a table & Insert values in table**

   INSERT INTO Raj (id, name, city) </br>
   VALUES </br>
   (101, 'Vivek', 'Noida'), </br>
   (102, 'Aditya', 'Delhi'), </br>
   (103, 'Nitish', 'Haryana');

   **Output**
    
   <div style="text-align: center;">
   <img src="./image/Create insert.png" alt="alt text" >
   </div>

   ***2. Read :-***

   This operation is used to Reading data from the database.
   Example: SELECT * FROM <table_name>  </br>

   SELECT * FROM Raj; (* means whole column & Row) </br>
   
   **Output** </br>

   <div style="text-align: center;">
   <img src="./image/Read.png" alt="alt text" >
   </div>   </br>

   SELECT name FROM Raj; (mention name column to read only name) </br>
    
   **Output** </br>

   <div style="text-align: center;">
   <img src="./image/name read.png" alt="alt text" >
   </div>


   ***3. Update :-***

   This operation is used to modify existing data in the database.
    Example: UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition; 
    </br>
   
   EX- UPDATE Raj  </br>
    SET city='Banglore' </br>
    WHERE  </br>
    name= 'Aditya'; </br>

   **Output** </br>

   <div style="text-align: center;">
   <img src="./image/update.png" alt="alt text" >
   </div>   </br>
   
   ***4. Delete :-***

   This operation is used to remove data from the database.
   Example: DELETE FROM table_name WHERE condition;

   EX- Delete FROM Raj </br>
   WHERE id=102; </br>

   **Output** </br>
    
   <div style="text-align: center;">
   <img src="./image/Delete.png" alt="alt text" >
   </div>
   </br>

   ## Datatypes and Constraint

   **Datatypes:-**

   An attribute that specifies the type of data in a column of our database-table.

   **Most widely used are**

   NUMERIC - INT DOUBLE FLOAT DECIMAL </br>
   STRING - VARCHAR  </br>
   DATE - DATE     </br>
   BOOLEAN - BOOLEAN   </br>
   
   EXAMPLE - DECIMAL (5,2) </br>

   - 155.38 (it means total 5 digits & after decimal 2 digits)

   **Constraint**

   A Constraint in PostgreSQL is a rule applied to a column.

   **Primary Key** 

   - The PRIMARY KEY constraint uniquely identifies each record in a table. </br>
   - Primary keys must contain UNIQUE values, and cannot contain NULL values. </br>
   - A Table can have only ONE primary key.

   EXAMPLE -</br> CREATE TABLE employees( </br> 
   emp_id SERIAL PRIMARY KEY, </br> 
	 fname VARCHAR(100) NOT NULL,  </br> 
	 lname VARCHAR(100) NOT NULL,  </br> 
	 email VARCHAR(100) NOT NULL UNIQUE, </br> 
	 dept  VARCHAR(50), </br> 
	 salary DECIMAL(10,2) DEFAULT 30000.00,  </br> 
	 hire_date DATE NOT NULL   </br> 
   DEFAULT CURRENT_DATE
    );
    </br>

   <div style="text-align: center;">
   <img src="./image/primary key .png" alt="alt text" >
   </div>

   ## Operators

   - ### Equal To 
   The `=` operator is used when you want to return all records where a column is equal to a specified value:
   ```
   SELECT * FROM employees
   WHERE dept = 'IT';
   ```
   **Output**

   <div style="text-align: center;">
   <img src="./image/operator.png" alt="alt text" >
   </div> </br>

   - ### Less Than
   The `<` operator is used when we want to return all records where a column is less than a specified value.
   ```
   SELECT * FROM Employees,
   WHERE Salary < 50000; 
   ```
   ### Other some operators are:
   `=`	Equal to  
   `<`	Less than  
   `>`	Greater than  
   `<=`	Less than or equal to  
   `>=`	Greater than or equal to  
   `<>`	Not equal to  
   `!=`	Not equal to  
   `AND`	Logical AND  
   `OR`	Logical OR  
   `IN`	Check if a value is between a range of values  
   `BETWEEN`	Check if a value is between a range of values  
   `IS NULL`	Check if a value is NULL  

   ## Clause

   - Where
   - Distinct
   - Order By
   - Limit
   - Like

   1. **Where**

   The WHERE clause is used in a PostgreSQL statement to filter data based on conditions specified in the WHERE clause. The WHERE clause can be used to filter data based on a single criteria or multiple criteria.

   Ex- 
   ```
   SELECT * FROM employees 
   WHERE dept = 'IT'  
   OR dept = 'HR'     
   OR dept = 'Finance'; 
   ```
   2. **Distinct**

   The DISTINCT statement is used to return only distinct (different) values.

   EX-
   ```
   SELECT DISTINCT fname FROM employees;
   ```

   **Order By**

   The ORDER BY keyword is used to sort the result in ascending or descending order.

   Ex- 
   ```
   SELECT * FROM employees ORDER BY fname;
   ```

   **Limit**

   The LIMIT clause is used to limit the maximum number of records to return.

   EX-
   ```
   SELECT * FROM employees LIMIT 3;
   ```
   **Like**

   The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

   The two wildcards used with the LIKE operator are:

   - % The percent sign represents zero, one, or multiple characters
   - _ The underscore sign represents one, single character
    
   ***To return records that starts with a specific letter or phrase, add the % at the end of the letter or phrase.***

   EX- 
   ```
   Select * FROM employees
   WHERE fname LIKE 'A%'; 
   ``` 

   ***Return all last name from a lname that starts with 'K' followed by one wildcard character, then 'ar' and then two wildcard characters.
   ***

   EX-
   ```
   Select * FROM employees 
   WHERE lname LIKE 'k__ar';
   ``` 
   
   
   ## JOINS

   JOIN operation is used to combine rows
   from two or more tables based on a related
   column between them.

   <div style="text-align: center;">
   <img src="./image/join.png" alt="alt text" >
   </div> </br>


   **Types of JOINS**

   - ***Cross Join :-***  Returns the Cartesian product of both tables. Every row from the first table is combined with every row from the second table.

    Example: Combine every employee with every department. </br>

   - ***Inner Join :-*** Returns only the rows where there is a match in both tables.

   Ex- Show employees and their department names, but only if they have a department. </br>

   - ***Left Join :-*** Returns all rows from the left table, and the matched rows from the right table. If there's no match, the result is NULL from the right side.

    Example: Show all employees and their department names, including employees without a department.</br>

   - ***Right Join :-*** Returns all rows from the right table, and the matched rows from the left table. If there's no match, the result is NULL from the left side.

    Example: Show all departments and their employees, including departments with no employees. </br>

   ## Conclusion
   
   PostgreSQL is a powerful free database known for its flexibility, reliability, and help from a large community. It works well for all kinds of projects, big or small, because it's stable, follows industry standards, and handles complicated jobs easily.

   
   ## Reference link 

   - [Posgress official documentation](https://www.postgresql.org/)

   - [Postgresql tutorial](https://www.geeksforgeeks.org/postgresql-tutorial/)











    
    
    
   
   

   
   

   
   











    
    


   









   




