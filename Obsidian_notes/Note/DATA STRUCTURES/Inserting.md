[[DSA]]

1. Find a Free space 
	* We keep a variable available that stores the index of the first unused element in the array
2. Allocate a node
	- Take one free index `newIndex = available` and move available to the next free index
3. Set data and links
	1. 

#### Beginning 
At beginning:  Set `next[newIndex] = head; head = newIndex;` 
###### From

| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 1    |
| 1     | 20   | 2    |
| 2     | 30   | -1   |

###### To

| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 1    |
| 1     | 20   | 2    |
| 2     | 30   | -1   |
| 3     | 15   | 0    |
### At End
###### From
`temp =head;`
Traverse until `next[temp]== -1`
`next[temp]= newIndex`;

| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 1    |
| 1     | 20   | 2    |
| 2     | 30   | -1   |

###### To
| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 1    |
| 1     | 20   | 2    |
| 2     | 30   | 3    |
| 3     | 40   | -1   |

#### At any position 
Set `next[newIndex]=next[prev];`
	`next[prev]=newIndex;`
###### From

| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 1    |
| 1     | 20   | 2    |
| 2     | 30   | -1   |

###### TO

| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 3    |
| 1     | 20   | 2    |
| 2     | 30   | -1   |
| 3     | 15   | 1    |
head 0;


Temp beginning


