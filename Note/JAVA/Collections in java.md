[[Unit_2]]

*Collections in java is a part of java collection framework that is used to group multiple elements into a single unit like a container*
*Collections can perform all the operation in data like sorting inserting manipulating and deletion*
`EG: list,Queue,array-list,linked-list,hash set,tree set`


#### Collection interface 
- *add(E e) - Adds an element and returns true if the element is added*
- *public boolean addAll(Collection c)- Add all elements form an other collection c to this collection `returns ture if the collection changed as a result*
- *Public boolean remove(Object element) Removes a specific element from the collection `Returns true if the element is removed`*
- *Public boolean contains(Object  Element) Check if the element exists in the collection `returns true if the element is present*
- *public Iterator iterator() Returns an Iterator to loop through the elements in the collection*
#### Iterator interface
*It allows the programmer to loop (Traverse)through the elements in the collection in a forward direction*

- *public boolean hasNext()->Returns true if the collection has more elements*
	`To check if there are elements left before calling next()`
- public object next()-> Returns The next element in the iteration 
- public void remove()-> Removes the last element returned by `next()` from the collection 

#### Iterable interface 
- IT is a super-interface of all collection type in Java
- If a class implements itrable it can be looped using for-each loop
- You must add a method called iterator that returns an iterator
	`That iterator helps to move through elements one by one`

##### [[List Interface]]
