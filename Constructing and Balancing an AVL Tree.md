# Ex. No: 16A - Constructing and Balancing an AVL Tree in Python

## AIM:
To write a Python program to construct an **AVL tree**, balance it, and print the nodes **before and after balancing** using the appropriate packages and built-in function.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Define a method `getDictTree(tree)` to return the `dict_tree` or structure of the AVL tree.

**Step 3**: Define a method `Construct_AVL(L)` to:
- Create a binary tree from the list `L`.
- Print the tree **before balancing**.
- Sort and reinsert the nodes in a balanced manner (simulating AVL behavior).
- Print the tree **after balancing**.

**Step 4**: Create a list `L` of integers.

**Step 5**: Call `Construct_AVL(L)` to build and balance the tree.

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
<img width="1281" height="205" alt="image" src="https://github.com/user-attachments/assets/6fb8b03c-6cf1-4412-8cfb-2204c6e42b10" />

# RESULT
Thus the program to construct an AVL tree and print the nodes of it has been implemented and executed successfully.


