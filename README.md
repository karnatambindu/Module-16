# Ex. No: 16A - Constructing and Printing an AVL Tree in Python

# AIM
To write a Python program to construct an AVL tree and print the nodes of it using the appropriate packages and built-in function.

# ALGORITHM

Step 1: Start the program.

Step 2: Define a function getDictTree(tree) to return the dict_tree of an AVL tree.

Step 3: Define a function Construct_AVL(L) to:

Create an AVL tree from the list L.
Get and print the dict_tree using getDictTree(tree).
Step 4: Define a list L with integer values.

Step 5: Call Construct_AVL(L) to build the tree and print the result.

Step 6: End the program.

# PYTHON PROGRAM
```
from TreeAVL.AVL import AVL  #Write your code here

def getDictTree(self):
 return self.dict_tree

def Construct_AVL(L):
    tree=AVL(L)
    print(getDictTree(tree))
L=[10,20,30,40,50,25]
```
# OUTPUT
<img width="1281" height="205" alt="Screenshot 2025-09-06 192618" src="https://github.com/user-attachments/assets/073a23a0-c8d5-4264-b641-702f8d31e9b9" />

# RESULT
Thus the program to construct an AVL tree and print the nodes of it has been implemented and executed successfully.

# Ex. No: 16B - Constructing and Balancing an AVL Tree in Python

# AIM
To write a Python program to construct an AVL tree, balance it, and print the nodes before and after balancing using the appropriate packages and built-in function.

# ALGORITHM

Step 1: Start the program.

Step 2: Define a method getDictTree(tree) to return the dict_tree or structure of the AVL tree.

Step 3: Define a method Construct_AVL(L) to:

Create a binary tree from the list L.
Print the tree before balancing.
Sort and reinsert the nodes in a balanced manner (simulating AVL behavior).
Print the tree after balancing.
Step 4: Create a list L of integers.

Step 5: Call Construct_AVL(L) to build and balance the tree.

Step 6: End the program.

# PYTHON PROGRAM
```
from TreeAVL.AVL import AVL

def getDictTree(self):
 return self.dict_tree

def Construct_AVL(L,N):
  tree = AVL(L)
  for i in N:
      tree.insertNode(i)
  print("AVL Tree Before Balancing\n",getDictTree(tree))
  tree.BalanceTree()
  print("AVL Tree After Balancing\n",getDictTree(tree))

```
# OUTPUT
<img width="1443" height="282" alt="Screenshot 2025-09-06 192952" src="https://github.com/user-attachments/assets/ea8d938e-c7f8-483b-8b4f-4618166aca1d" />

# RESULT
Thus the program to construct an AVL tree, balance it, and print the nodes has been implemented and executed successfully.

# Ex. No: 16C - Inserting Nodes in a B-Tree in Python

# AIM
To write a Python function def insert(self, k): to insert the nodes in a B-Tree.

# ALGORITHM

Step 1: Start the program.

Step 2: Define the BTreeNode class to represent a node:

Contains a list of keys.
Contains a list of children.
Indicates whether it is a leaf.
Step 3: Define the BTree class with:

Methods for inserting keys.
Handling node splitting.
Tree traversal and printing.
Step 4: Implement insert():

Insert a key into the tree.
Handle full root case and invoke node splitting if needed.
Step 5: Implement insert_non_full() to insert a key into a node that is not full.

Step 6: Implement split_child() to split a full child during insertion.

Step 7: Define print_tree() to recursively print the structure of the B-Tree.

# PYTHON PROGRAM
```
# Searching a key on a B-tree in Python


# Create a node
class BTreeNode:
  def __init__(self, leaf=False):
    self.leaf = leaf
    self.keys = []
    self.child = []


# Tree
class BTree:
  def __init__(self, t):
    self.root = BTreeNode(True)
    self.t = t

    # Insert node
  def insert(self, k):
    root = self.root
    if len(root.keys) == (2 * self.t) - 1:
      temp = BTreeNode()
      self.root = temp
      temp.child.insert(0, root)
      self.split_child(temp, 0)
      self.insert_non_full(temp, k)
    else:
      self.insert_non_full(root, k)

    # Insert nonfull
  def insert_non_full(self, x, k):
    i = len(x.keys) - 1
    if x.leaf:
      x.keys.append((None, None))
      while i >= 0 and k[0] < x.keys[i][0]:
        x.keys[i + 1] = x.keys[i]
        i -= 1
      x.keys[i + 1] = k
    else:
      while i >= 0 and k[0] < x.keys[i][0]:
        i -= 1
      i += 1
      if len(x.child[i].keys) == (2 * self.t) - 1:
        self.split_child(x, i)
        if k[0] > x.keys[i][0]:
          i += 1
      self.insert_non_full(x.child[i], k)

    # Split the child
  def split_child(self, x, i):
    t = self.t
    y = x.child[i]
    z = BTreeNode(y.leaf)
    x.child.insert(i + 1, z)
    x.keys.insert(i, y.keys[t - 1])
    z.keys = y.keys[t: (2 * t) - 1]
    y.keys = y.keys[0: t - 1]
    if not y.leaf:
      z.child = y.child[t: 2 * t]
      y.child = y.child[0: t - 1]

  # Print the tree
  def print_tree(self, x, l=0):
    print("Level ", l, " ", len(x.keys), end=":")
    for i in x.keys:
      print(i, end=" ")
    print()
    l += 1
    if len(x.child) > 0:
      for i in x.child:
        self.print_tree(i, l)

  

B = BTree(3)

for i in range(10):
    B.insert((i, 2 * i))
print("B Tree :")
B.print_tree(B.root)
n=int(input())
B.insert((n,))
print("\nB Tree after insertion")
B.print_tree(B.root)
```
# OUTPUT
<img width="1185" height="433" alt="Screenshot 2025-09-06 193314" src="https://github.com/user-attachments/assets/d9fbe981-9edc-4039-b341-005063deded6" />

# RESULT
Thus the program using Python function def insert(self, k): to insert the nodes in a B-Tree has been implemented and executed successfully.

# Ex. No: 16D - Inserting Elements in a B+ Tree in Python

# AIM
To write a Python function def insert(self, key, value): to insert elements into a B+ Tree.

# ALGORITHM

Step 1: Start the program.

Step 2: Define a BPlusTreeNode class to represent each node in the B+ Tree:

Store keys and corresponding values.
Maintain child pointers.
Track if the node is a leaf.
Step 3: Define a BPlusTree class to manage the overall structure:

Implement methods to insert new keys and values.
Handle node splitting when the node exceeds the allowed degree.
Step 4: Implement insert(self, key, value):

Locate the correct leaf node for insertion.
Insert key-value pair.
If the node overflows, split the node and propagate the split up if necessary.
Step 5: Implement methods to handle:

Finding the appropriate node for insertion.
Splitting full nodes.
Linking leaf nodes for fast range queries.
Step 6: Print the B+ Tree level-wise after insertion.

# PYTHON PROGRAM
```
class Node(object):

def __init__(self, order):
    
    self.order = order
    self.keys = []
    self.values = []
    self.leaf = True

def add(self, key, value):
    
    if not self.keys:
        self.keys.append(key)
        self.values.append([value])
        return None

    for i, item in enumerate(self.keys):
        
        if key == item:
            self.values[i].append(value)
            break

        
        elif key < item:
            self.keys = self.keys[:i] + [key] + self.keys[i:]
            self.values = self.values[:i] + [[value]] + self.values[i:]
            break

    
        elif i + 1 == len(self.keys):
            self.keys.append(key)
            self.values.append([value])

def split(self):
    
    left = Node(self.order)
    right = Node(self.order)
    mid = self.order // 2

    left.keys = self.keys[:mid]
    left.values = self.values[:mid]

    right.keys = self.keys[mid:]
    right.values = self.values[mid:]

  
    self.keys = [right.keys[0]]
    self.values = [left, right]
    self.leaf = False

def is_full(self):
 
    return len(self.keys) == self.order

def show(self, counter=0):
    
    print(counter, str(self.keys))

    
    if not self.leaf:
        for item in self.values:
            item.show(counter + 1)
class BPlusTree(object):

def __init__(self, order=8):
    self.root = Node(order)

def _find(self, node, key):
    
    for i, item in enumerate(node.keys):
        if key < item:
            return node.values[i], i

    return node.values[i + 1], i + 1

def _merge(self, parent, child, index):
    
    parent.values.pop(index)
    pivot = child.keys[0]

    for i, item in enumerate(parent.keys):
        if pivot < item:
            parent.keys = parent.keys[:i] + [pivot] + parent.keys[i:]
            parent.values = parent.values[:i] + child.values + parent.values[i:]
            break

        elif i + 1 == len(parent.keys):
            parent.keys += [pivot]
            parent.values += child.values
            break

def insert(self, key, value):
    
    parent = None
    child = self.root

    while not child.leaf:
        parent = child
        child, index = self._find(child, key)

    child.add(key, value)

    
    if child.is_full():
        child.split()

       
        if parent and not parent.is_full():
            self._merge(parent, child, index)

def retrieve(self, key):
   
    child = self.root

    while not child.leaf:
        child, index = self._find(child, key)

    for i, item in enumerate(child.keys):
        if key == item:
            return child.values[i]

    return None

def show(self):
    
    self.root.show()
def demo_node(): node = Node(order=4) node.add('a', 'alpha') node.add('b', 'bravo') node.add('c', 'charlie') node.add('d', 'delta') node.show()

print('\nSplitting node...')
node.split()
node.show()
def demo_bplustree(): print('B+ tree...')

bplustree = BPlusTree(order=4)
x=input()
y=input()
bplustree.insert('a', 'alpha')
bplustree.insert('b', 'bravo')
bplustree.insert('c', 'charlie')
bplustree.insert('d', 'delta')
bplustree.insert('e', 'echo')
bplustree.insert(x,y)
bplustree.show()
if name == 'main': demo_node() print('\n') demo_bplustree()
```
# OUTPUT
<img width="1195" height="485" alt="Screenshot 2025-09-06 193544" src="https://github.com/user-attachments/assets/0c703e70-67a1-42e9-aee4-5e15c47fe7dc" />
# RESULT
Thus the program using function def insert(self, key, value): to insert elements into a B+ Tree has been implemented and executed successfully.

# Ex. No: 16E - Perform Left Rotation in AVL Tree and Insert '7'

# AIM
To write a Python function def leftRotate(self, z): to perform the left rotation operation in an AVL Tree and insert the element '7' into it.

# ALGORITHM

Step 1: Start the program.
Step 2: Define the TreeNode class to represent each node in the AVL Tree:
Key value
Left and right child pointers
Height of the node
Step 3: Define the AVL_Tree class to manage AVL operations.
Step 4: In the insert() method:
Insert the key using standard Binary Search Tree logic.
Update the height of the current node.
Calculate the balance factor to detect imbalance.
Based on balance factor and key position, perform necessary rotations.
Step 5: Define leftRotate(z) method:
Let y = z.right and T2 = y.left
Make z the left child of y
Assign T2 as the right child of z
Update heights of z and y
Return y as the new root of the subtree
Step 6: Insert the key '7' using the insert() method. If it causes imbalance, perform appropriate rotation.
Step 7: Display the tree using preOrder() traversal to show the structure after insertion and rotation.
Step 8: End the program.
# PYTHON PROGRAM
```
class TreeNode(object):
	def __init__(self, val):
		self.val = val
		self.left = None
		self.right = None
		self.height = 1

class AVL_Tree(object):
	def insert(self, root, key):
		if not root:
			return TreeNode(key)
		elif key < root.val:
			root.left = self.insert(root.left, key)
		else:
			root.right = self.insert(root.right, key)

	
		root.height = 1 + max(self.getHeight(root.left),
						self.getHeight(root.right))

		balance = self.getBalance(root)

		if balance > 1 and key < root.left.val:
			return self.rightRotate(root)

	
		if balance < -1 and key > root.right.val:
			return self.leftRotate(root)

		
		if balance > 1 and key > root.left.val:
			root.left = self.leftRotate(root.left)
			return self.rightRotate(root)
   
		if balance < -1 and key < root.right.val:
			root.right = self.rightRotate(root.right)
			return self.leftRotate(root)

		return root

	def leftRotate(self, z):
	    y=z.right
	    t1=y.left
	    
	    y.left=z
	    z.right=t1
	    
	    z.height=1+max(self.getHeight(z.left),self.getHeight(z.right))
	    y.height=1+max(self.getHeight(y.left),self.getHeight(y.right))
	    return y

	
	def getHeight(self, root):
		if not root:
			return 0

		return root.height

	def getBalance(self, root):
		if not root:
			return 0

		return self.getHeight(root.left) - self.getHeight(root.right)

	def preOrder(self, root):

		if not root:
			return

		print("{0} ".format(root.val), end="")
		self.preOrder(root.left)
		self.preOrder(root.right)


myTree = AVL_Tree()
root = None


 
root = myTree.insert(root, 13)
root = myTree.insert(root, 10)
root = myTree.insert(root, 15)
root = myTree.insert(root, 5)
root = myTree.insert(root, 11)
root = myTree.insert(root, 16)
root = myTree.insert(root, 7)

 # WRITE YOUR CODE HERE 


print("Preorder traversal of the constructed AVL tree is")
myTree.preOrder(root)
print()

```
# OUTPUT
<img width="1201" height="259" alt="Screenshot 2025-09-06 193912" src="https://github.com/user-attachments/assets/6452a7e5-6512-462f-b979-53d69f22ce3d" />
# RESULT
Thus the program using Python function def leftRotate(self, z): to perform the left rotation operation in an AVL Tree has been implemented and executed successfully.
