[[Full stack]]
*NPM or node package manager is the package manager for Node.js and JavaScript*


*Package contains all the files required for a module and modules are the JavaScript libraries that can be included in the Node.js projects as needed*
npm can install dependencies from package.json and in package.json the developer can select with version of the module should be included in the project they can also decide with packages auto updates and with does not 
`npm install`*is used to install all dependencies*
`npm add <packagename>` *is used to add new dependencies to the JSON file*

*npm is an online repo for node.js modules which can be either browsed via the web or installed via CLI it also manages version and dependencies for a node.js project*

`npm update`-used to update dependencies
`npm init`-to create a node project

`Modules in node.js provide functionalities which can be used through the node.js application`
```
package.json is also used to store metadata like name project version discription etc
```
Dev dependency-used for testing libraries during the development
dependency-used when shipping the final packaged product 

`Require function is used to import available pakages into a node.js project ``requre(package)``  `
`export is used to export a node.js function so that it can be used in another project ``module.export(module name)`` `


### how node works
1. Node accepts request
	- Client send request
	- node recevies it
2. Single Thread
	- Node.js works mainly on one main thread
	- it doens not create a new thread for every request
3. event loop
	- If a task takes time node send it to the background
	- Node continues handling other request
4. Thread concept
	- A thread is a sequence of information executed by CPU
	- Node uses background threads for I/O
	- But javascript runs on one single main thread
5. Non - Blocking
	- One slow request will Not block others

object in node.js an object stores data in key-vaule pairs 
	key is the name of the poperty
	value is the data stored in the property

object are similar to variables and it contains values the values are stoed in key value pairs
`name address` key
`bob west virgina` value

`Buffer is a data type used to store binary data`
Repl terminal is a interactive terminal like bash terminal it is used for the following tasks read eval print loop etc

* **Browser Apis**  it provide extra features to JavaScript like setTimeout() xhmlhttrequest etc
* **Heap**- The heap is where the objects and variables are stored in the memory
* **call back queue** When an async task finishes its callback goes here
* **Event loop** - IT connects every thing it checks if the call stack is empty
	* if empty it takes the first callback queue and moves it to the call stack to run