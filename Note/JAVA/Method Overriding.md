[[Unit_2]]
*Method overloading means when a child class has a same method with the same name return datatype same number of arguments as the parent class
Its also called runtime polymorphism* 

#### Advantages of method overriding
- *The child class can edit and modify the contents of the method without editing the code of the parent class*
- *this is helpful when the parent class have multiple child class  each child class can add its on implementation without editing the source code of the parent class*

#### Dynamic method Dispatch
- *When a parent class reference is used to call a method on a child object  java decides at runtime which version of the method is to be used*
>   [REFERANCE](https://chatgpt.com/share/681e191f-1600-8005-bfa9-b4c2e91190b8)

#### Dynamic method dispatch
*Dynamic method dispatch is how java correctly specify which implementation of the overridden method should be run during the runtime based on which object it is referring to*



| Method overloading                                | Method Overriding                        |
| ------------------------------------------------- | ---------------------------------------- |
| Parameter must be different and name must be same | Both name and parameter must be the same |
| Compile time polymorphism                         | Run-Time polymorphism                    |
| Increase readability of the code                  | Increase re-usability of the code        |
#### Rules for method overriding
- *The arguments should be the same type and the number of arguments must be the same*
- *If the parent class is public then the child class also should be public*
- *A method declared final or static cannot be overriden*
- *Constructs cannot be overriden*
