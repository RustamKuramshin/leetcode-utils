# Super Lightweight Java Library For Debug And Testing LeetCode Problems :sunglasses:

## Description
A java library that will help you solve problems with leetcode. The library is represented by just one java class and does not require any external dependencies other than jdk.

## Features
* Built-in class of a singly linked list ListNode, supplemented with useful functions such as: printing a list.
* Built-in class of a doubly linked list Node, supplemented with useful functions such as: printing a list.
* Built-in binary search class TreeNode, supplemented with useful functions such as: initialization of a binary tree from a string representation of an integer level-order array, conversion of a binary tree into an array and vice versa.

All classes of leetcode's data structure (Node, ListNode and TreeNode) can be used in your code if you write a solution to the problem in your IDE.

## Usage
Run the following command in the directory with the code you need:
```shell
cd /path/to/your/code/directory

curl -O https://raw.githubusercontent.com/RustamKuramshin/leetcode-utils/main/src/main/java/leetcode/utils/LeetCodeUtils.java
```

Or manually copy the contents of the java class file from the following link [https://github.com/RustamKuramshin/leetcode-utils/blob/main/src/main/java/leetcode/utils/LeetCodeUtils.java](https://github.com/RustamKuramshin/leetcode-utils/blob/main/src/main/java/leetcode/utils/LeetCodeUtils.java).


If necessary, import the class into your java/kotlin code:
```java
import your.package_path.LeetCodeUtils;
```
Or just put the java library class next to your classes.

You can also make a static import of any leetcode data structure class to work with it in your code:
```java
import static your.package_path.LeetCodeUtils.TreeNode;

// ... your code

TreeNode root = TreeNode.ofArrayString("[2,1,3,null,4,null,7]");
```

## Documentation

### Singly Linked List

Class of a singly linked list:
```java
class ListNode {

    public int val;
    public ListNode next;

    public ListNode() {
    }

    public ListNode(int x) {
        val = x;
        next = null;
    }
    
    ...
}

// initialize it: new ListNode()
```
Print out your linked list:
```java
listNode.printListNode()
// will print [3, 2, 4, 5, 10]
```

### Doubly Linked List

Doubly linked list class:
```java
class Node { 
    
    public Node prev;
    public Node next;

    public int val;
    
    public Node() {
    }

    public Node(int val) {
        this.val = val;
    }
    
    ...
}

// initialize it: new Node()
```
Print out your linked list:
```java
node.printNode()
// will print [3, 2, 4, 5, 10]
```

### Binary Tree

Binary Tree class:
```java
class TreeNode {

    public int val;
    public TreeNode left;
    public TreeNode right;

    public TreeNode() {
    }

    public TreeNode(int val) {
        this.val = val;
    }
    
    ...
}

// initialize it: new TreeNode()
```
Get a binary tree from the string representation of the level-order array:
```java
TreeNode root = TreeNode.ofArrayString("[2,1,3,null,4,null,7]");
```
Or just from the array:
```java
TreeNode root = TreeNode.array2btree([2,1,3,null,4,null,7]);
```
Or turn your binary tree into a level-order array:
```java
Integer[] levelOrderArray = TreeNode.btree2array(root);
```

## Enjoy!