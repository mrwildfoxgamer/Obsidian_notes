[[UNIT 4]]

*An  SQL Query must be Scanner parsed and validated*

- *The Scanner identifies the tokens (Keyword attributes and relation name)*
- *The parser checks  fro the query Syntax*
- *The validation process checks if all the attribute and relation names are valid and semantically meaningful names in the schema*
`An interanl representation of the query is then created as a tree data structure also called a tree query`
`It is also posible to represent the query by using a graph data structure calles a query graph`
- The DBMS must then devise an execution strategy or query plan for retrieving the result
`the process of choosing the sutab;e execution strategy is known as query optimization`

The code generator generates the code to executes the the plan and runtime database processor executes the code
 

**Query in high level language**
			↓
==Scanning parsing and validating==
			↓
	Immediate from of query
			↓
	  ==Query optimizer==
			↓ 
		Execution plan
			↓
	==Query code generator==
			↓
	code to execute the query
				↓
	==Runtime database processor==
				↓
		  Result of the query

