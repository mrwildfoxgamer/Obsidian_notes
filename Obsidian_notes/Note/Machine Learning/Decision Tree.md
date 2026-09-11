>It is a superviced learning algorithm
>It can be used for classification,Regression

*A decision tree has minaly 4 parts Root decision nodes branches and leaf node*

- **Root node** - It is the First/Top decision in the tree `it is also called the parent node and every other nodes branched from it are called child node`
- **Decision/internal node** - A node where another question/test is performed 
- **Branch** - The connection/path representing the result of a decision
- **lead Node** - The Final result/prediction node
- **pruning** - Removing unwanted branch from the tree
- **Splitting** - deviding the root node or sub node into different parts on the basis of some conditions
- **Entropy**- It measures the **impurity/uncertainty** of a collection of examples
- **Information Gains** - Information Gain tells us how useful an attribute is for splitting the data. `Information Gain = Entropy before split − Entropy after split
- **Gain index** - the measure how impure of mixed a group of data is  

`An attribute is simply a feature/characteristic of the data.`

`The ID3 algorithm builds the tree from the top down.`


## ID3

ID3 uses **top-down, greedy search** 
>**Greedy** means it chooses the best option **at the current step**, rather than searching through every possible complete tree.

Start with entire dataset
          ↓
Calculate entropy
          ↓
Calculate Information Gain
for each attribute
          ↓
Choose highest Information Gain
          ↓
Make it the root
          ↓
Split the dataset
          ↓
Repeat for each subset
          ↓
Stop when appropriate

### Tree pruning
A tree can become too large because it starts learning **noise and outliers** in the training data.

That causes:

> **Overfitting**

Pruning removes unnecessary branches to make the tree simpler and improve generalization.

#### Types of pruning
1. Pre-Pruning - Stop the tree before it becomes too large
	Grow tree
	   ↓
	Is split good enough?
	   ↓
	NO → Stop
	   ↓
	Make leaf
2. Post pruning - First allows the tree to grow to its maximum depth then Evaluates the branches and remove unnecessary branchs
