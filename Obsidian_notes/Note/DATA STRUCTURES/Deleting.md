[[DSA]]

### Any position

*del = index of the node to be deleted*
*prev = index of the node before the one to delete*
`next[prev]=next[del]`;
`avail=del`;

##### From

| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 1    |
| 1     | 20   | 2    |
| 2     | 30   | 3    |
| 3     | 15   | -1   |

##### To

| Index | Data | Next             |
| ----- | ---- | ---------------- |
| 0     | 10   | 1                |
| 1     | 20   | 2                |
| 2     | 30   | -1               |
| 3     | 15   | avail(free node) |

#### Beginning
`head = next[head]`;
###### From

| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 1    |
| 1     | 20   | 2    |
| 2     | 30   | 3    |
| 3     | 15   | -1   |
###### To

| Index | Data | Next  |
| ----- | ---- | ----- |
| 0     | 10   | avail |
| 1     | 20   | 2     |
| 2     | 30   | 3     |
| 3     | 15   | -1    |

### END 
- Traverse Till the last node is found `temp==-1`
`next[prev]=-1`;
`next[temp]=avail`;

###### From
| Index | Data | Next |
| ----- | ---- | ---- |
| 0     | 10   | 1    |
| 1     | 20   | 2    |
| 2     | 30   | 3    |
| 3     | 15   | -1   |
###### TO
| Index | Data | Next  |
| ----- | ---- | ----- |
| 0     | 10   | 1     |
| 1     | 20   | 2     |
| 2     | 30   | -1    |
| 3     | 15   | avail |
