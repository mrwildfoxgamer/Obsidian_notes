[[Unit_2]]
#### Stream 
*Stream is a pipeline for processing items from a collection*
- *Processes items one by one*
- Allows you to perform actions like filtering changing  or combining items 
- Does not change the original Data
- Make the code cleaner and easier to understand and process

##### Character Stream
- *They are designed to handle characters (formatted texts) Use Unicode encoding* 
- *They are suitable  for working with Text data such as reading and writing files that contains text*
##### Byte Stream 
- *They are used to handle raw binary data in the form of bytes*
- *Byte stream require explicit encoding and decoding when working with text data*
- Suitable for low level io operations such as  reading and writing to network sockets


##### Classes

###### Byte Stream
- *Byte stream classes read and write 8-but data*
- Using bytestream classes we can save video audio characters etc 
- Java.io package contains these classes 

##### Input stream
- *This type of data stream read data from a source*
- An input stream can read data from file network connection or any other I/O device
##### Output stream
- *The output stream Write the data into a dsetination*
#### Character stream
- *It is used for 16 bit unicode input and output operations*
- It can be helpfull in copying a text file containing characters  from one file to another that is using stream
- Can work with array chat String and Unicode characters of length 16bits 
- Mainly used to read data from a source and  write them to a destination
###### Two classes Reader class & Writer class

