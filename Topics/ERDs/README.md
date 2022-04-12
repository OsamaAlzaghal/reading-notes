# Introduction to Databases and ERDs
---
## What is a Database?
According to oracle.com, A database is an organized collection of structured information, or data, typically stored electronically in a computer system. A database is usually controlled by a database management system (DBMS).

![DB](https://bs-uploads.toptal.io/blackfish-uploads/components/seo/content/og_image_file/og_image/777046/0712-Bad_Practices_in_Database_Design_-_Are_You_Making_These_Mistakes_Dan_Social-754bc73011e057dc76e55a44a954e0c3.png)

## What is a  database management system (DBMS)?
---
A DBMS serves as an interface between the database and its end users or programs, allowing users to retrieve, update, and manage how the information is organized and optimized. It helps with controling the database and it is considered as an administrative assistant.

![DBMS](https://www.tutorialspoint.com/dbms/images/dbms_users.png)

---
## What is a Schema?
A database schema is like a skeletal structure representing a logical view of a whole database. It devises all the constraints applied to the data in a particular database.

---
## Why do we use schemas in databases?
Because they help developers visualize how a database should be structured.

---
## What do schemas look like?

![schema](https://www.i2p.es/wp-content/uploads/2020/04/HAMGR.png)

---

## Types of Keys in Database
+ Primary Key
+ Candidate Key
+ Alternate Key
+ Super Key
+ Composite Key
+ Foreign Key
+ Unique Key

---
### What is a Primary Key?
A primary key is a special relational database table column (or combination of columns) designated to uniquely identify each table record.

### What is a Foreign Key?
A Foreign Key is a field (or collection of fields) in one table, that refers to the PRIMARY KEY in another table. 

### What is a Composite Key?
Composite Key s a combination of two or more columns in a table that can be used to uniquely identify each row in the table.

**Note:** Uniqueness is only guaranteed when the columns are combined.

---
### Primary key vs Foreign key vs Composite key
The primary key will consist of one column, where the composite key will consist of two or more columns(attributes). Foreign key is an attribute which is a Primary key in its parent table but is included as an attribute in the host table.
[Source](https://www.analyticsvidhya.com/blog/2020/07/difference-between-sql-keys-primary-key-super-key-candidate-key-foreign-key/#:~:text=Alternate%20keys%20are%20those%20Candidate%20keys%20that%20were%20not%20chosen,attribute%20in%20the%20host%20table.)

---
## What are Relationships in a relational database?
![example](https://miro.medium.com/max/1400/1*KQhEvghLqZWiD0KMigPbFw.png)

### 1:1 relationship:
A one-to-one relationship is a relationship where a record in one table is associated with exactly one record in another table. 

![1:1](https://docs.magento.com/mbi/images/one-to-one.png)


### Many:Many relationship:
A many-to-many relationship occurs when multiple records in a table are associated with multiple records in another table.
**Note:** in the type of relationship, we create aa new table that has foreign keys from both students and classes tables to connect them in a many to many relationship.

![m:n](https://programmer.help/images/blog/47fda377baa78674da54df48888276b7.jpg)

### 1: Many or a Many:1 relationship:
One record in a table can be associated with one or more records in another table.

![1:m](https://vertabelo.com/blog/one-to-many-relationship/relationships.jpg)