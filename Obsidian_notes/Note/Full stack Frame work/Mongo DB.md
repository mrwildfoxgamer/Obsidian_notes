[[Obsidian_notes/Note/Full stack Frame work/UNIT 1|UNIT 1]]

*IT is an open-source no SQL database that stores data in json-like format*

- Schema Flexibility - *No predefined schema can easily change with requirements*
- Horizontal scalability - *built-in sharding distributes data across multiple devices*
- Replication - copies of your data is stored on other servers for backup and safety
- Rich query Language - You can search and filter data in powerful ways
- ACID transaction - data stays correct and consistent even if something fails 
- Geo-spatial support - You can store and search location data 
- Full-Text streams - *you can search words in side text easily*
- Change streams - The database can notify your app when data changes
- Could ready architecture - Easy integration with major cloud providers like AWS Azure etc designed for could deployment

	`Sharding = splitting big data into smaller parts and storing them on different servers.`


* Mongo DB uses BSON format to store data 
	* Binary JSON extends json with more data types ` date,object,binarydata, decimal numbers etc`
	* ```
	  {
     "_id": ObjectId(...),
     "name": "John Doe",
     "age": 30,
     "email": "john@example.com"
   }
	  ```
* Nested Documents- *it is the ability to store an object inside another object*
* Arrays - you can store multiple values in one filed
1. Maximum Document size 16 mb
2. Field names are case sensitive
3. Documents are stored in collections 



| Mongo DB                                            | SQL DB                             |
| --------------------------------------------------- | ---------------------------------- |
| Data are stored in collection (groups of docuemnts) | Data are stored inRows and columns |
| Json like objects                                   | Records in table                   |
| Field key value pair                                | Colunm attribute in table          |
| Embedded docs                                       | Joins-related tables               |
| Schema Flexible dynamic                             | Schema fixed prededined            |

## Disadvantages of Mongo DB 
- Memory Consumption due to storage format and indexing
- Data duplication
- Limited transaction support
- Steep learning curve
- Not ideal for complex joins


## Uses
- Mobile applications due to flexible schema and offline sync 
- Social media 
- E-commerce 
- Location based services-geo spacial quires for maps and location tracking
- Real-time Analytics
- Content management
- Gaming
- IoT applications


## Mongo DB architecture
- It uses Wired tiger as storage engine
	- It stores data on disk and support data compression and document-level locking for better performance
- Mongos for Query Router
	- Used in distributed systems
	- It send queries to the correct shard
- Replica sets used for backup and high availability
	- Primary->handles all write operations
	- Secondary->Copies data from primary
	- `If primary failes the secondary becomes the new primary`
- Sharding Splits data into smaller parts (shards) these data is distributed across multiple machines reach shard usually has its own replica set

| Embedded Docuemnts          | Rederences                  |
| --------------------------- | --------------------------- |
| Data stored together        | Data stored seprately       |
| Faster read                 | Needs lookup                |
| Best for small realted data | Best for large complex data |


## When not to use Mongo DB
- Complex multi-table Transactions
- Strict schema enforcement
- Legacy system integration
- Small scale applications
- Financial systems