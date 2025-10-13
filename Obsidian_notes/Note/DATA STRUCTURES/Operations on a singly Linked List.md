[[DSA]]

###### Code
```
#include <stdio.h>

struct node{

  int data;
  int next;

};

int main(){

 struct node linkedlist[10];

  for(int i=0;i<10;i++){
  
    printf("Enter the value of the linked list %d: ",i);
    scanf("%d",&linkedlist[i].data);
    
    if (i<9) {
       linkedlist[i].next=i+1;
 }else {
          linkedlist[i].next=-1;

 }
  }

  int head =0;

  printf("Values: \n");

  while(head!=-1){
    
    printf("%d\n",linkedlist[head].data);
    head= linkedlist[head].next;
  `` }

}
```
###### Operations
- Traversing
- [[Inserting]]
	1. inserting an element at the beginning of the list  
	2. Inserting an element at the end of the list
	3. inserting an element at the specified position in the list 
-  [[Deleting]]
	1. Deleting an element from the beginning of the list 
	2. Deleting an element at the end of the list
	3. Deleting an element at the specified position in the list 
- Copying - `To make a duplicate list`
- Merging - `Joining 1 or more list together to make it a larger list`
- Searching - `To find an element in the list`
- Count - `To get the number of elements`
