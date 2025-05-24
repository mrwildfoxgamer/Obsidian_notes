[[DBMS]]
#### Normalization


- *It is the process of structuring database to reduce data redundancy and improve integrity  It involves splitting the table and defining relationships*
- *rather than storing the data in a single table the data is spited and stored in multiple tables and a relation is setup*
#### Anomalies 
Anomalies is the problem that occurs in a database due to poor planing un-normalized database where all the data is stored in one table

- **Insert** - It occurs when you cannot insert a data into a table with out an other  data present in the table 
- Delete - It occurs when data is lost because of the deletion of some other data
- Update - it exists when one or more instance  of duplicate data is updated but not all

#### Functional Dependency 
 IT is written as x->y which means if 2 rows has the value same in a column then it also has the same value in another column

  ```
  eg if EMPID -> EMPNAME 
  That means 2 rows has the same EMPID then both of these rows must also has the   same EMPNAME 
```

#### Armstrong's AXIOMS Rules
- **Reflexivity** - if a is a set of attributes and b is a sub set of a then a holds b (a->b)
- **Augmentation** - If a holds b and c is a set of attributes then ac holds bc (AC -> BC)
- **Transitivity**- IF a hold b and b holds c then a hold c 
#### Closure of an attribute Set ({x}⁺)
*It means all attributes can be locally derived from a given attribute set x using a set of functional dependencies*
```
If you know the EMPID with it you can find the rest of the information about the employee 
```

- used to find Candidate keys 
- checking for normalization
- Ensuring data dependency are preserved during decomposition

#### Closure of a Relation CLP(R)


*It refers to the smallest relation that include the original relation and satisfies a given property*
- It is denoted by CLp(R)
#### Lossless decomposition 
*When a table is split into multiple tables later it can be joined back together to get the original table with out any data loss*

- no data is lost during decomposition 
- you can rebuilt the original table using `JOIN`
- It ensures data integrity
#### 1 NF (1st normal form )
A table is in 1NF if 
- *Each cell contains only one value*
- *No repeting group or list in a single cell*
1NF is the `1st step`  in organizing data properly 

### 2 NF
*A table is in 2 NF if its already in 1 NF *
- A table is 2 NF if all the elements in a table is fully dependent on a primary key in it 

- this reduces repetition 
- make the database more organized 
#### 3 NF

A table is in 3 NF if its already in 2 NF 
NO non -prime attribute should depend on another non prime attribute which itself depends on the primary key



- **Primary key**: A unique identifier for each row (e.g., `StudentID`).
    
- **Non-prime attribute**: An attribute (column) that is **not part of any candidate key** (e.g., `DepartmentName`).
    
- **Transitive dependency**: When a non-prime attribute depends **indirectly** on the primary key **via another non-prime attribute**.

#### Boyce-CoDD Normal Form (BCNF)
A realtion is in BCNF if 

- For every functional dependecny X-> A x must be a super key
```
If somthing determines another attribure The somthing must be able to uniquely identify a row 
```
