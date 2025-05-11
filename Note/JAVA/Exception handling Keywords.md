[[Unit_2]]
- try
- catch
- finally
- throw
- throws

##### Try

- *The try Keyword is used to enclose a block of code that might throw an error*
- *The try block must be inside a method*
- *A try block must be followed by a catch or a final block*
##### Catch block
- *The catch block is used to handle the exception*
- *Catch block must be used after the try block*
- *multiple catch blocks can be used right after a single try block*
##### Multi catch block
* *multi catch block in java helps you to catch multiple exceptions with a single catch block*
* *Different exceptions are joined with pipe operator "|"*
##### Finally
- *The finally block is used to execute a block of code whether exception is handled or not*
- Uses includes opening or closing a file or stream etc 

`It is posible to have try block with out catch by using finally `
##### Throw 
- *Throw key word is used to throw exceptions*
- *It can throw either checked or unchecked exceptions*
##### Throws 
- *Throws keyword is used to declare an exception*
- `If a method can throw a checked exception the programmer must declare it by using throws keyword`



| *Throw*                                   | *Throws*                                                  |
| ----------------------------------------- | --------------------------------------------------------- |
| IT is used to throw an exception          | It is used to declare an exception                        |
| Throw is followed by an instance (object) | Throw is followed by a class                              |
| Throw is used with in a method            | Throw is used with the method signature (before the "{}") |
| you cannot throw multiple exceptions      | You can declare multiple exceptions                       |
**ERROR vs Exception**

- ->*An error is an irrecoverable condition occurring during the runtime The errors cannot be repaired during Runtime The execution comes to a stop when an error occurs*
- ->*Exception occurs due to human error and in most case they are recoverable the execution does not stops when an exception occurs*
