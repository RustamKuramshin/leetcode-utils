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
import static leetcode.utils.LeetCodeUtils.TreeNode;

// ... your code

TreeNode root = TreeNode.ofArrayString("[2,1,3,null,4,null,7]");
```

## Enjoy!