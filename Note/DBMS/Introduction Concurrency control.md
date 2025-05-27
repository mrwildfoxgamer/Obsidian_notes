[[UNIT 4]]

*Concurrency means that multiple transactions can be ran together in the system*
- *These can Increase the utilization of the Processor and disk leading to better transaction throughput*
- *Reduce average response time for transaction as multiple transaction can run simultaneously*  

#### Deadlock
*A Deadlock happens when two or more transactions are waiting for each other to release resource but none of them ever proceed because they are stuck waiting* 



### Recovery
* *Recovery from transaction failure means the database is restored  to the most  state before the failure occurred*
* *The system stores different data related to the change made by different transactions in order to do the recovery they are stored in system log*


###### Extensive damage
`Disk crash,power failure,Hardware Malfunction`
The system restores the most recent backup copy of the data base from the archival storage 
it is then reapplies all the committed Transactions recorded in the log file up until the failure occurred  

##### Deferred update  and immediate update

It is a recovery technique where the database on disk is not physically updated until a transaction successfully reaches its commit point before committing all the changes are temporary in the local transaction workspace if a transaction fails before a commit has occurred  then   no changes has been done to the database hence no undo is needed this is why it is also called no undo  redo algorithm 