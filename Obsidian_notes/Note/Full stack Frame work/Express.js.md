*Express is a minimalist web application framework with this module you can create anything from large complex application to simple websites*
*It simplifies the development of server side applications by offering an easy-to-use API for routing midleware and http utilities it also supports builtin rust API's*


## Working of Express.js
1. Client sends request
	+ User sends a HTTP request to the server
2. Middle-ware runs
	+ The request passes through middle-ware
		+ Logging
		+ authentication
		+ modifying request data
3. Route is matched
	+ Express checks the URL and method to find the correct route
4. Application Logic runs
	+ The route runs the main code of the application
5. Response is sent
	+ after the processing the server sends a response back to the client
6. Error handling
	+ If something goes wrong error middle-ware handles it so that the server does not crash 
`Client → Middleware → Route → Application Logic → Response`

## Advantages of Express.js

+ Easily integrable with template engines
+ flexible and Robust Routing
+ Minimalist code
+ Huge list of 3rd party modules

`Routing means deciding what the server should do when a user requests a specofic url`

| Methods | Use         |
| ------- | ----------- |
| GET     | get data    |
| POST    | send data   |
| PUT     | update data |
| DELETE  | delete data |
`Handler:a function that executes when the route is accessed`
`Path: defines the endpoint where the request is handled`

