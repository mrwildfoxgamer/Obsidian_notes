[[UNIT 2]][[DBMS/UNIT 1|UNIT 1]]
- **Data Query:** Extracting information form the tables
- **Data Manipulation:** Insert update deleting records 
- **Data Definition:** Creating and modifying database objects like tables indexes and views 
- **Data control:** Mapping access to the data    

## Basic sql commands 
#### Data definition language (DDL)
- create: used to create new objects
- Alter: modifies existing objects
- Drop: deletes objects from the database
### Data manipulation language (DML)
- Select: retrieves data from one or more tables
- Insert: add new records to a table 
- Update: changes existing records 
- Delete: removes records form a table
### Data control language (DCL)
- Grand: provides user access privileges 
- Revoke:removes access privileges

## Fundamental database concepts 
### Relational database model
*Oracle database is built on the relational model where data is stored in tables that relate to one another through common key*
- **table** Basic units that store data in rows and columns
- **Primary keys** unique identifiers for table records 
- **foreign keys** columns that establish a link between two tables
### Schema
*A schema is the structures that represents the logical configurations of all the or part of a database* 
- `table views indexes:` The organization and relationships between data objects 
- `User permissions:` Which users can access or modify the schema objects 
- `constrains:` Rules enforced on the data (primary key)

### Data Independence
*Data independence refers to the separation between how data is stored and how it is accessed*
- **Logical data independence**: the ability to change the conceptual schema without affecting the external schema (user views)
- **Physical Data independence:** The capacity to change the internal schema (storage structures,file organization) which out affecting the conceptual schema 
*This separation allows databases administrators to optimize performance and storage without affecting how applications interacts with the data*

### Constraints and Data integrity
- `Not null` ensures a column cannot have null values
- `unique` Ensure all values in a column are distinct 
- `foreign key` Ensures referential integrity between two tables 

### Data modeling
*data modeling is the process of creating a data model for the data to be stored in a database*
- **Conceptual Models** Capturing high level business concepts and rules 
- **Logical Models** defines detailed structures including entities attributes and relationships 
- **Physical Models** Mapping the logical design to a physical implementation,considering storage indexing and performance.

### Database instance vs schema 
- **Database instance::** A data base instance refers to the actual running database system where memory structures and processes are actively managing  data
- **Database Schema** A schema is a blueprint or logical structure of a database defined by tables,views and relationships,while the schema remains static the instance can change with daily data operations 
### Data Types
*Every column in a table is assigned a datatype that defines the kind of data it can hold*

- **Ensuring data accuracy** enforcing the correct format and size
- **Optimizing Storage:** Allowing efficient storage and retrieval base on the expected values 
- Prevent incorrect data entry through type constraints
#### composite key
*A composite key is a type of primary key that consists of two or more columns used together to uniquely identify each record in a table*