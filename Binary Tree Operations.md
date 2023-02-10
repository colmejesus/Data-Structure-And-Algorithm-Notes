
## Here's the structure of a Node, Binary Tree and their operations:

### TreeNode: A tree node is a data structure, part of a tree, it contains Data, Reference to the left and right nodes. Here are the operations supported by it:

getData(): Gets whatever data is stored in a node, on which the method is called. If you call `getData()` on a specific node, it will return the data stored in that node, whether it's the root node, the left child node, or the right child node.

setData(): It stores data inside the node, on which it is called, if you call `setData()` on a specific node it will store the data, you passed as the argument inside the mentioned node. 

Treenode getLeft(): It will return the reference to the left child node of the node on which this method is being called. 

Treenode GetRight(): It will return the reference to the right child node of the node on which this method is being called. 

setLeft(Treenode): It will set the passed node (the one you'll pass as an argument) as the left child node of the node you called this method on.

setRight(Treenode): It will set the passed node (the one you'll pass as an argument) as the right child node of the node you called this method on.

### Binary Search Tree: It is a type of binary tree that follows a particular traversal order. The operations supported by a Binary search tree are:

RootRef: A method used to retrieve the reference of the root node of the binary tree it is called on. 
insertNode(TreeNode n, int data): It inserts the data in the node you referenced as an argument in the method on the binary tree you called this method on.

deleteNode(TreeNode, int data): It will delete whatever node that comes under the mentioned `Treenode` passed as argument that has the specified `data` that has been passed as `int data` argument. 

preorder(Treenode), postorder(Treenode), inorder(Treenode), levelorder(Treenode): These methods will traverse the tree in the specified order taking `Treenode` argument as the root node and return the data in the traversed nodes in the order which they traversed, which can then be used for processing. 

search(key): this method will search the binary tree on which it is called which corresponds with the `key`, which is passed as argument, and if the node is found, the method will return a reference to that node, it allows users to quickly locate and retrieve a node with a specific value. 


## Binary Tree: Incursion (Recursion)

```java
TreeeNode insertNode(TreeNode n, int d){
	if(n==null){return new TreeNode(d);}
	else{
		if(d<n.getData()){
			TreeNode new_n=insetNode(n.getLeft(),d);
			n.setLeft(new_n);
			else{
				TreeNode new_n=insertNode(n.getRight(),d);
				n.setRight(new_n);
			}
		}
	
	
	}
	return n;
}
```




