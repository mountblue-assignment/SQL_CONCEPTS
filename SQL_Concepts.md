# SQL CONCEPTS !

Before continuing the  important concepts about ***SQL*** , firstly 
we should know about what is ***SQL*** .
So ***SQL*** ( Structured Query Language )  is standardized non - procedural   and also client /server language   that is used to manage relational databases (mostly useful for structured data) and perform operation on databases like  data definition , data retrieval , data manipulation etc .
It was developed in 1970s by **IBM**  and later it became standard of ANSI /ISO in 1980s .

The  SQL commands can be categorized as 

 1. **DDL (Data Definition Language) :**  These SQL commands are used to create and define the database structure .  e.g. CREATE , ALTER , DROP  ,RENAME , etc .
 2. **DML (Data Manipulation Language) :** These SQL commands are used to only manipulate data on databases . e.g.  INSERT , DELETE , UPDATE etc .

 3. **DQL (Data Query Language) :** These SQL commands are used to retrieve  the data in databases. e.g. SELECT etc . 
 4.  **DCL (Data Control language ) :**  These SQL commands are used to control and grant the access of databases . e.g. GRANT , REVOKE etc .
 5.  **TCL (Transaction Control Language) :** TCL is used to maintain consistency and manage the transaction in a database. e.g. COMMIT , ROLLBACK etc.

There are some important concepts related to SQL and Database that are necessary to  understand for databases:


## Normalization:

   Normalization is a database design technique that reduces data redundancy and eliminates Insertion, Update and Deletion Anomalies. In Normalization we divides larger tables into smaller tables and links them using relationships. Edgar Codd proposed the theory of normalization. 

There are various type of Normalization that are mostly used 
  - 1NF (First Normal Form)
-   2NF (Second Normal Form)
-   3NF (Third Normal Form)
-   BCNF (Boyce-Codd Normal Form)
-   4NF (Fourth Normal Form)

***1NF  :-***    Each table cell should contain a single value and  Each record needs to be unique.

 ***2NF :-***   For 2NF , It should be in 1NF and  All non-key attributes are functionally dependent on the entire primary key.

***3NF:-*** For 3NF ,  It should be in 2NF  .  There is no transitive dependency, meaning that non-key attributes are not dependent on other non-key attributes.

***BCNF :-*** It is stricter than 3NF . A table is in BCNF , if every functional dependency X -> Y , X is super key of table  
 
 ***4NF :-***   For 4NF , It should be in BCNF and has no multi-valued dependency.   A multi -value dependency  is dependency from A->B if for a single value of A, multiple values of B exists .



## Indexes :

Index is type of data structure that is used to  locate and access the data in database . and it  helps in reducing the search time of a database query.

 ### How to Create an Index :  
  General syntax for creating a basic index that applies on all database 

       CREATE INDEX index_name 
       ON table_name (column_name1 ,column_name2  ...)

### Types of Indexes :
  From the point of view of the characteristics of the index attribute:
-   Primary Index
-   Clustered Index
-   Secondary Index

 From the point of view of the number of index references to a data file:
  -  Dense Index
  -  Sparse Index
   
## Joins:
 We  use SQL Join  to fetch data from two or more tables, which is joined to show as single set of data. It is used for combining column from two or more tables by using values common to both tables.
`JOIN` Keyword is used in SQL queries for joining two or more tables.

###  Types of JOIN : 

Following are the types of JOIN that we can use in SQL:

-  **INNER JOIN** :  This is simple join where it takes  only the matching things from both lists, leaving out the rest.

- **LEFT JOIN (or LEFT OUTER JOIN)** : It retrieves all rows from the left ( first) table and the matching rows from the right ( second) table. If there are no matches, It puts  NULL values  for the columns from the right table.

-  **RIGHT JOIN (or RIGHT OUTER JOIN)** : It is similar to LEFT JOIN but retrieves all rows from the right table and the matching rows from the left table. If there are no matches , it puts NULL values  for the columns from the left table.

-  **FULL OUTER JOIN** : It retrieves all rows from both tables and puts NULL values for columns where there are no matches. 

 - **SELF JOIN** : Joins a table with itself to retrieve related information within the same table.



## Aggregations and Filters in Queries:

we can use Aggregations and filters to take specific data that we need in our future operations like we wan

- **Aggregations: -**  Aggregations help us summarize and understand large sets of data. For example, we  can calculate averages, totals, counts, or other group of rows of data  which are often more meaningful than individual data points.
e.g.  COUNT , SUM , MAX , MIN   etc . 

-  **Filters : -**  With the help of filter we can select set of data that meets certain condition . Using filter we can take relevant data and excluding irrelevant information . 
e.g.  WHERE clause with condition 



## Transaction : -

 A transaction can be defined as  group of tasks that are logically related . The main operation of transaction are :

 - Read (A) : - Read operation read the value of A from the database and store it in buffer of main memory .
 - Write (A) :- 	Write operation write the value of A  from buffer to database.

A transaction in a DBMS must follow ACID property : - 


##  ACID Property :

  In the DBMS ,  ACID is an acronym that represents Atomicity ,  Consistency , Isolation , Durability  that is used to ensure accuracy , completeness and data integrity .
  
   -  **Atomicity:** - According to this property, a transaction must be treated as an atomic (single) unit that means either all of the its operation must be executed or none of them . If something goes wrong during transaction  ,  the whole transaction is rolled back . 
  -  **Consistency:** Consistency ensure that the database must remain in a consistent state after any transaction .the database must follow certain rules and constraints to maintain data integrity. 
  
  - **Isolation:** According to this property , all concurrent  transaction should not interfere with each other when one transaction is being processed . It means when one transaction is using any resources at that time other transaction should not able to take that resources for  any operation .
  
  -  **Durability:**   Durability ensure that once the changes made by transaction are  committed that changes must be saved   and wont be lost , even if the something failure  happens .

## Locking Mechanism:
Locking Mechanism is protocol in DBMS  that we use to lock the objects ,  control and manage access to shared resources, such as database records, during concurrent operations . 
Multiple transactions may request a lock on a data item at same time , Hence, we require a mechanism to manage the locking requests made by transactions .
So basically Locking is just a  protocol where each and every operation is  locked before the transaction and  released  after the completion of operations 

In database management systems, various types of locking mechanisms are used to control concurrent access that are : 

 - Shared Lock (S-Lock) 
 - Exclusive Lock (X-Lock) 
 - Schema Lock 
 - Table-Level Lock



## Database Isolation Levels:
Database isolation levels determine how concurrent transactions should  interact with each other . There are common isolation levels :
- **Read Uncommitted**: It allows one transaction to visible  its  uncommitted changes to others.
- **Read Committed**: It ensures that only committed changes are visible to other transactions.
- **Repeatable Read**: This level of isolation ensures a high level of data consistency by preventing non-repeatable reads, which means that once a transaction reads a set of data, it can be sure that the data won't change until the transaction is finished.
- **Serializable**  − It determines that all concurrent transactions must be executed serially.



## Triggers:

Triggers are database objects that automatically execute a specified action (e.g., a SQL statement) when certain events, such as INSERT, UPDATE, or DELETE operations, occur in a table. 

   **Types Of  Trigger : -**  
   
 1.  **DDL Trigger :**   DDL triggers respond to changes in the database structure or schema.

2.  **DML Trigger :**  DML triggers respond to data manipulation operations like INSERT, UPDATE, or DELETE statements that modify data in tables. 
3.  **Logon Triggers :**  Logon triggers execute in response to a user's connection attempt to the database. They can be used to control or monitor user access to the database.


## CAP Theorem

The CAP theorem states that while you can want for all three properties (C, A, and P), you can only achieve two of them at any given time , The CAP theorem, also known as Brewer's theorem.

- **Consistency ( C )** :  A system is said to be consistent if all nodes see the same data at the same time. Simply, if we perform a read operation on a consistent system, it should return the value of the most recent write operation.

-  **Availability ( A )** :  A system is said to be consistent if the system remains responsive and accessible to users even in the time of  network failures or node crashes .
 
 - **Partition Tolerance ( P )** :  This condition states that the system does not fail, if messages are dropped or delayed between nodes in a system . It provide  ability to continue functioning .
