[[Unit_2]]

#### What is Interface
- Interface is a template that can be applied to a class 
- Interface Specifies what a class must do
- It is used to achieve abstraction and multiple inheritance 
- Interface cannot directly create an actual working thing like an object 
```
Interface is just a plan and class is where you build the thing on the plan
```

- The variables declared on an interface is public static and final by default and methods are public and abstract 
```
since java 8 static methond is inheritance is posible 
```

#### Relation between class and Interface
- Interface is a list of conditions that need to be  fulfilled and class is the one that fulfills  these conditions 

##### Class Extends Class 
- A class can inherits the properties of an other class using EXTENDS keyword. In which a child class can adopt the properties of a parent class 
##### Class Implements Interface
- In class Implements Interface a class is created that will fulfill all the requirements of the interface  
##### Interface Extends Interface 
- An interface can acquire the requirements of one or more parent interfaces using the Extends keyword 
##### Multiple inheritance 
- If a class inherits the properties of multiple parents class or a interface inherits properties of multiple parent interfaces its called multiple inheritance
##### Interface inheritance

- A class implements interface but one interface extends another interface

##### Marker Interface or tagged interface  
- it is a empty interface used to signal a the java compiler about  a specific capability of a class during runtime 