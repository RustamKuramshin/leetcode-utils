# Super Lightweight Java Library For Debug And Testing LeetCode Problems :sunglasses:

## Description
A java library that will help you solve problems with leetcode. The library is represented by just one java class and does not require any external dependencies other than jdk.

## Features
* Built-in class of a singly linked list ListNode, supplemented with useful functions such as: printing a list.
* Built-in class of a doubly linked list Node, supplemented with useful functions such as: printing a list.
* Built-in binary search class TreeNode, supplemented with useful functions such as: **initialization of a binary tree from a string representation of an integer level-order array**, conversion of a binary tree into an array and vice versa.
* **A player of test cases for tasks with an integer cache.**

All classes of leetcode's data structure (Node, ListNode and TreeNode) can be used in your code if you write a solution to the problem in your IDE.

## Usage
Run the following command in the directory with the code you need:
```shell
cd /path/to/your/code/directory

curl -O https://raw.githubusercontent.com/RustamKuramshin/leetcode-utils/main/src/main/java/leetcode/utils/LeetCodeUtils.java
```

Or manually copy the contents of the java class file from the following link [https://github.com/RustamKuramshin/leetcode-utils/blob/main/src/main/java/leetcode/utils/LeetCodeUtils.java](https://github.com/RustamKuramshin/leetcode-utils/blob/main/src/main/java/leetcode/utils/LeetCodeUtils.java).

**REMOVE THE JAVA PACKAGE DECLARATION FROM THE JAVA CLASS FILE. OR SPECIFY THE NAME OF THE PACKAGE YOU NEED!**


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
#### Print out your linked list (takes into account cyclic (closed) linked lists):
```java
listNode.printListNode()
// will print [3, 2, 4, 5, 10]
```
#### Generate a random singly linked list with the specified parameters:
```java
ListNode listNode = ListNode.generateRandomListNode(30, 0, 100, ListNode.Order.ASCENDING);
```
#### Create a singly linked list from the string representation of the array:
```java
ListNode list = ListNode.ofArrayString("[-10,-3,0,5,9]");
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
#### Get a binary tree from the string representation of the level-order array:
```java
TreeNode root = TreeNode.ofArrayString("[2,1,3,null,4,null,7]");
```
#### Generate a binary tree of arbitrary size! It is possible to pass parameters specific to binary trees from the LeetCode tasks.
```java
TreeNode root = TreeNode.randomBinaryTreeBuilder()
        .nodesCount(5000) // Required number of binary tree nodes
        .minNodeVal(-1_000_000_000) // Minimum possible value of a binary tree node
        .maxNodeVal(1_000_000_000) // Maximum possible value of a binary tree node
        .mode(TreeNodeMode.BINARY_SEARCH_TREE) // Generation mode
        .build();
```
#### Beautiful binary tree printing
```java
root.printBinaryTree();
```
method will output:
```text
└── 2
    ├── -2
    │   ├── -8
    │   │   ├── -10
    │   │   └── -5
    │   └── -1
    │       ├── -2
    └── 4
        ├── 3
        └── 5
```
#### Method of inserting a new node into a binary tree
```java
root.addNode(node);
```
#### A method for obtaining the size of a binary tree. Returns the number of nodes.
```java
root.size();
```
#### The classic equals() and hashCode() methods, which will help compare two binary trees.
```java
root1.equals(root2);
```

### Test Case Player For Integer Cache Problems
A player of test cases for tasks in which you need to work with an integer cache.
The cache should follow the following interface:
```java
interface Cache {
    int get(int key);
    void put(int key, int value);
}
```
Create a text file in the resource directory with a sequence of cache methods from the test case:
```text
["LFUCache","put","put","put","put","put"]
```
Create a text file in the resource directory with the actual cache method parameters from the test case:
```text
[[10],[10,13],[3,17],[6,11],[10,5],[9,10]]
```
The number of methods and the number of sets of actual parameters must match!
Put these text files in the resource directory.


Call the static playTestCase() method of the CacheTestCasePlayer class. This will cause an instance of your cache class to be created and methods with parameters will be called as in the test case with leetcode!
The playTestCase() method needs to be passed a reference to your cache class, the path to the file with the sequence of cache methods and the path to the file with the parameters of these methods.
```java
CacheTestCasePlayer.playTestCase(LFUCache.class,"test-cases-data/p460/17/methods.txt", "test-cases-data/p460/17/data.txt");
```

## Enjoy! :man_technologist: