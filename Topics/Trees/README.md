# Trees
## Tree components
+ Node - A Tree node is a component which may contain its own values, and references to other nodes.
+ Root - The root is the node at the beginning of the tree.
+ K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
+ Left - A reference to one child node, in a binary tree.
+ Right - A reference to the other child node, in a binary tree.
+ Edge - The edge in a tree is the link between a parent and child node.
+ Leaf - A leaf is a node that does not have any children
+ Height - The height of a tree is the number of edges from the root to the furthest leaf.

![img](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)

## Traversals
1. Depth First: Depth first traversal is where we prioritize going through the depth (height) of the tree first.

	Methods for depth first traversal:
	+ Pre-order: root >> left >> right
	+ In-order: left >> root >> right
	+ Post-order: left >> right >> root
	
	![img](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Preorder-from-Inorder-and-Postorder-traversals.jpg)
	
	Traversal Pseudocode: here is the pseudocode for all three of the depth first traversals:
	+ Pre-order: 
		```
		ALGORITHM preOrder(root)
		// INPUT <-- root node
		// OUTPUT <-- pre-order output of tree node's values

    	OUTPUT <-- root.value

    	if root.left is not Null
      	    preOrder(root.left)

   		if root.right is not NULL
      	    preOrder(root.right)
       	  
		```
		---
		+ In-order:
		```
		ALGORITHM inOrder(root)
		// INPUT <-- root node
		// OUTPUT <-- in-order output of tree node's 	values

    	if root.left is not NULL
        	inOrder(root.left)

    	OUTPUT <-- root.value

    	if root.right is not NULL
        	inOrder(root.right)
		```
		---
		+ Post-order:
		```
		ALGORITHM postOrder(root)
		// INPUT <-- root node
		// OUTPUT <-- post-order output of tree node's values

    	if root.left is not NULL
        	postOrder(root.left)

    	if root.right is not NULL
        	postOrder(root.right)

    	OUTPUT <-- root.value
		```
2. Breadth First: It starts at the tree root and explores all nodes at the present depth prior to moving on to the nodes at the next depth level. Breadth first traversal uses a queue (instead of the call stack via recursion) to traverse the width/breadth of the tree.
	+ Pseudocode:
	```
	ALGORITHM breadthFirst(root)
	// INPUT  <-- root node
	// OUTPUT <-- front node of queue to console

  	Queue breadth <-- new Queue()
  	breadth.enqueue(root)

  	while ! breadth.is_empty()
    	node front = breadth.dequeue()
    	OUTPUT <-- front.value

    	if front.left is not NULL
      	breadth.enqueue(front.left)

    	if front.right is not NULL
      	breadth.enqueue(front.right)
	```
---
## K-ary Trees
It's a type of trees that has more than 2 child nodes. In this type of tree we use K to refer to the maximum number of children that each Node is able to have.

![img](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/KaryTree1.png)

---
## Binary Search Trees
A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.

### Steps for searching inside a BST:
We will start with this tree:

![img](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BST1.PNG)

So starting from the root, each time we will compare the current node with the value we are searching for, if our value is less than the current node, it we go left, else it will go right and so on until it reaches the searched node or the end of the tree.

![img](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BST2.PNG)

**Note:** Binary Search Tree’s insertion and search operations is O(h) or O(h) which represents the height of my tree and for space O(1) since we don't need any additional space. In a balanced (or “perfect”) tree, the height of the tree is log(n). In an unbalanced tree, the worst case height of the tree is n.

Resources: [Code Fellows](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html).      