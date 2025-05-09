[[Unit_2]]

*The final keyword is used to declare a variable,method,class as  constant `ie The contents cannot be changend by the programer after inizilied`*

Final method is inherited but cannot be overridden 

#### blank Final Variable
- *A final variable that is not initialized during  declaration is called a blank final variable*
- *The value must be initialized inside the constructor or the method in which the blank final variable is declared* 
#### Static blank final variable 
- *A static blank final variable is a static final variable that is declared with out  initializing value*
- *The value of the variable must be declared in a static block*
```
class test {
Static final int x;

static {

	x=100;
			}
				}
```


`If you declare a static parameter you cannot change its value`
