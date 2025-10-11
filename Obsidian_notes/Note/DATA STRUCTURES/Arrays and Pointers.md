[[DSA]]

*Array are used to store multiple values in a single variable instead on separate variable for each value*

`size of operator is used to find the size of an array`


### Multidimensional Array

*multidimensional array are arrays that has more than one dimensional ie`the array can scale in multiple axis`*

### Pointers

*Pointers are used to store memory address of a variable*
`& is used to fetch the memory address`
`* is called the derefrance opperator used to access the value of a variable the pointer is pointing to`

#### Advantages of Using pointers 

- Using pointers to pass the data between functions can be more efficient  
- pointers are used to create dynamic data structures like Linked List  graph and tree
- Using pointers can reduce the size of the code base and improve performance 
- pointers are used when working with files and memory managements
- Arithmetic operations can be performed via pointers 


### Relation between array and pointers 

*The name of the array is a pointer to the first element of an array*

- To access the next elements of the array you can increase the value of the pointer by adding values to it ie`ptr+1,ptr+2 etc`


### Pointers and Structures

*Using pointer to structure can make the code  more efficient when passing structs to a functions or changing the values*

- *To access the members of a struct you can must use the -> operator*
- To use a pointer to a struct you can use ( * )
```
struct car{
char name;
char brand;
}
int main(){
struct car car1=("camry",toyota);
struct car*p=&car1


printf("%s %s",p->name,p->brand);
}
``` 

