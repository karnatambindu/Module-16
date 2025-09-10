# Ex. No: 16B - Constructing and Printing an AVL Tree in Python

## AIM:
To write a Python program to construct an **AVL tree** and print the nodes of it using the appropriate packages and built-in function.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Define a function `getDictTree(tree)` to return the **dict_tree** of an AVL tree.

**Step 3**: Define a function `Construct_AVL(L)` to:
- Create an **AVL tree** from the list `L`.
- Get and print the **dict_tree** using `getDictTree(tree)`.

**Step 4**: Define a list `L` with integer values.

**Step 5**: Call `Construct_AVL(L)` to build the tree and print the result.

**Step 6**: End the program.

## PYTHON PROGRAM
```
from TreeAVL.AVL import AVL  #Write your code here

def getDictTree(self):
 return self.dict_tree

def Construct_AVL(L):
    tree=AVL(L)
    print(getDictTree(tree))
L=[10,20,30,40,50,25]
```

## OUTPUT
<img width="1281" height="205" alt="image" src="https://github.com/user-attachments/assets/63026add-41fe-48f9-95bf-7fed2b41c07f" />


## RESULT
Thus the program to construct an AVL tree and print the nodes of it has been implemented and executed successfully.
