[[UNIT 4]]

- *The relational Algebra is a set of rules used to get data from a data base*
- *It helps to ask questions about the database*
- *You can get you answers in a table (called relations)*
- *You can use the results in more operations to get other answers*

$Select$ Operation - *it is used to  retrieve data from a subset of a single row from a relation that satisfies the section condition*

$Project$ Operation It is used to select only one specific column and ignore the rest of the column 

$Rename$ Operation It is used to rename a relation or an attribute or both

$Union$ $Intersection$ $Set-Difference$ ($MINUS$ or $EXCEPT$) These operations combine or compare two set of data
-  $Union$ Add all the rows from both sets
- $Intersection$ Keeps only the rows that appears in both 
- $Set-Difference$ removes rows in one set that are also in other set

`These works only if both sets have the same type of data ie same column`


$Cartesian-product$  ($Cross-Product$ or $Cross-join$) Combines every row from one set with every row from another creating all possible pairs 

`The tow sets doesnot need to have the same column`

$Join$ Operation - *It connects 2 tables based on the related data*
- *It combines rows from both tables into longer row if they meet a certain condition*
- *It is useful if your data is speared across different tables*
- `<condition> AND <condition> AND <Conditon>`

$DEVISION$ Operation - *It is denoted by  ÷ It is used to find a entry that match every enrty in the second table*

