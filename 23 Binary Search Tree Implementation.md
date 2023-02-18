Here's a program implementing search, insertion and printing functions of a binary tree:

```java
class Node {
  int value;
  Node left;
  Node right;
  Node(int value) {
    this.value = value;
  }
}

class BST {
  Node root;

  void insert(int value) {
    root = insert(root, value);
  }

  private Node insert(Node node, int value) {
    if (node == null) {
      return new Node(value);
    }
    if (value < node.value) {
      node.left = insert(node.left, value);
    } else {
      node.right = insert(node.right, value);
    }
    return node;
  }

  boolean search(int value) {
    return search(root, value);
  }

  private boolean search(Node node, int value) {
    if (node == null) {
      return false;
    }
    if (node.value == value) {
      return true;
    }
    if (value < node.value) {
      return search(node.left, value);
    } else {
      return search(node.right, value);
    }
  }

  void print() {
    print(root);
  }

  private void print(Node node) {
    if (node == null) {
      return;
    }
    print(node.left);
    System.out.println(node.value);
    print(node.right);
  }
}

public class Main {
  public static void main(String[] args) {
    int[] data = {7, 3, 2, 5, 4, 6, 1};
    BST bst = new BST();
    for (int value : data) {
      bst.insert(value);
    }
    bst.print();

    int searchValue = 4;
    boolean found = bst.search(searchValue);
    System.out.println("Value " + searchValue + " was " + (found ? "" : "not ") + "found.");
  }
}

```

Explanation of The Implementation:

```java
class Node {
  int value;
  Node left;
  Node right;
  Node(int value) {
    this.value = value;
  }
}
```

##### This is the definition of the Node class. It has three fields, `value` which is the value of the node, `left` which is a reference to the left child of the node and `right` which is a reference to the right child of the node. The constructor of the class takes in an integer value, and sets it to the `value` field of the node.

```java
class BST {
  Node root;
  void insert(int value) {
    root = insert(root, value);
  }
```

##### This is the definition of the BST class. It has two fields, `root` which is the root node of the binary search tree, and a method `insert` that takes in an integer `value` as its parameter. In the body of the method, it sets the value of `root` to the result of calling `insert` with `root` and `value` as its parameters.

```java
private Node insert(Node node, int value) {
    if (node == null) {
      return new Node(value);
    }
```

##### This is a private helper method `insert` which is used to insert a node in the BST. It takes in two parameters, `node` which is the node being passed to the method, and `value` which is the value of the node being inserted. If `node` is `null`, it means that we have reached the end of the tree and the new node can be inserted here. So the method returns a new node with the given `value`.

```java
    if (value < node.value) {
      node.left = insert(node.left, value);
    } else {
      node.right = insert(node.right, value);
    }
```

##### If `node` is not `null`, then the method checks whether the value of the node to be inserted is less than the value of the current node. If it is, it sets the value of the `left` child of the current node to the result of calling `insert` with the `left` child of the current node and the value to be inserted as its parameters. If the value of the node to be inserted is greater than or equal to the value of the current node, it sets the value of the `right` child of the current node to the result of calling `insert` with the `right` child of the current node and the value to be inserted as its parameters.

```java
    return node;
  }
```

##### Finally, the method returns the `node` that was passed to it.

```java
  boolean search(int value) {
    return search(root, value);
  }
```

#### Search method:


##### The `search` method in the `BST` class is used to determine if a given value exists within the BST. The method takes an integer value as input and returns a boolean indicating whether the value was found in the tree.


```java
boolean search(int value) {
    return search(root, value);
  }
```

##### This method is a wrapper function that calls the private method `search(Node node, int value)`. The `root` field of the `BST` instance is passed as the first argument to the private method.

```java
private boolean search(Node node, int value) {
    if (node == null) {
      return false;
    }
    if (node.value == value) {
      return true;
    }
    if (value < node.value) {
      return search(node.left, value);
    } else {
      return search(node.right, value);
    }
  }
```

##### The private method `search(Node node, int value)` implements the search functionality of the BST. It takes a `Node` and an integer value as input and returns a boolean indicating whether the value was found in the subtree rooted at the given node.

The method first checks if the node is `null`, and if it is, it returns `false` as the value is not found in the tree. If the node is not `null`, the method checks if the value of the node is equal to the target value. If it is, the method returns `true`.

If the target value is less than the value of the current node, the method recursively calls itself with the left child of the current node. If the target value is greater than the value of the current node, the method recursively calls itself with the right child of the current node.

#### Print Method:

##### The most commonly used orders for tree traversal are In-order, Pre-order and Post-order. For this example, we'll use In-order traversal.

```java
void print() {
    print(root);
  }
  private void print(Node node) {
    if (node != null) {
      print(node.left);
      System.out.println(node.value);
      print(node.right);
    }
  }
```

##### This method is a wrapper function that calls the private method `print(Node node)`. The `root` field of the `BST` instance is passed as the first argument to the private method.

The private method `print(Node node)` implements the In-order traversal of the BST. It takes a `Node` as input and outputs the values of the nodes in the subtree rooted at the given node, in ascending order.

The method first checks if the node is `null`, and if it is, it simply returns. If the node is not `null`, the method first calls itself with the left child of the current node, effectively visiting all nodes in the left subtree.

Next, the value of the current node is outputted. Finally, the method calls itself with the right child of the current node, effectively visiting all nodes in the right subtree.


### Main function (How insertion works):

##### With the given unordered array `[7, 3, 2, 5, 4, 6, 1]`.

-   We start with an empty binary search tree, so the root of the tree is null.
-   Insert the first value, 7, into the tree. Since the root is null, we create a new node with value 7 and set it as the root. The left and right child of the root are both null.

```javascript
    7
   / \
null null
```

- Insert the next value, 3. Since the root is not null, we compare the value 3 with the value at the root, 7. 3 is less than 7, so we insert 3 as the left child of the root.
```javascript
    7
   / \
  3  null
 / \
null null
```

- Insert the next value, 2. Since the root is not null, we compare the value 2 with the value at the root, 7. 2 is less than 7, so we go left to the left child of the root, which has value 3. 2 is less than 3, so we insert 2 as the left child of the node with value 3.

```javascript
    7
   / \
  3  null
 / \
2  null
   / \
null null
```

- Insert the next value, 5. Since the root is not null, we compare the value 5 with the value at the root, 7. 5 is less than 7, so we go left to the left child of the root, which has value 3. 5 is greater than 3, so we insert 5 as the right child of the node with value 3.

```javascript
    7
   / \
  3  null
 / \
2   5
   / \
null null
```

- Insert the next value, 4. Since the root is not null, we compare the value 4 with the value at the root, 7. 4 is less than 7, so we go left to the left child of the root, which has value 3. 4 is greater than 3 and less than 5, so we insert 4 as the right child of the node with value 2.

```javascript
    7
   / \
  3  null
 / \
2   5
   / \
  4  null
 / \
null null
```

- Insert the next value, 6. Since the root is not null, we compare the value 6 with the value at the root, 7. 6 is less than 7, so we go left to the left child of the root, which has value 3. 6 is greater than 3 and less than 5, so we go right to the right child of the node with value 3, which has value 5. 6 is less than 5, so we insert 6 as the left child of the node with value 5.

```javascript
    7
   / \
  3  null
 / \
2   5
   / \
  4   6
 / \
null null
```

- Insert the next value, 1. Since the root is not null, we compare the value 1 with the value at the root, 7. 1 is less than 7, so we go left to the left child of the root, which has value 3. 1 is less than 3 and less than 2, so we insert 1 as the left child of the node with value 2.

```javascript
    7
   / \
  3  null
 / \
2   5
   / \
  1   6
```