[[UNIT 4]]
#### Transaction
A Transaction is a group of operations that are done together it include reading updating data  To make sure the database stays correct the system follows  ACID rules

### ACID properties

# A 
*Atomicity*
`All or nothing` If one part of the transaction fails then the whole thing is cancelled
# C
*Consistency* 
`Always valid` The database must remain correct before and after  the transaction
# I
*Isolation*
`transaction don't Interface` IF  multiple transaction are running simultaneously Each one should act as if its running alone 
# D
*Durability* 
`Change stayes forever`  If one transaction is done the change stays forever

#### States of transaction
##### active
The transaction has started and is running
##### Partially committed
The final step has been committed by the transaction has not been finalized
##### Failed
Something went wrong The transaction cannot finish properly

##### Aborted
Because of the failure the system undoes all the changes made by the transaction (Roll back)
After that:
`Restart (if the error was external)`
`Kill it (If there is no fix)`

##### Committed 
Everything worked and the changes are now permanent


**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUcgsrc7pRuu3ALv3SmkpeaZt3vmmy_E7nTlIArkozKpuEYP2V43t02kHKY7oZi3E-90ZaczpoH2MOJVJQ28HOxpW9DMijLG2A_r_JsNvWAYRldn4cWA3tSX5PmDz-Dyp3QoV93ahw=s2048?key=yVzr5OMXP_4HXzTRcc9_2A)**