Binary Search Trees, including self-balancing Red-Black Trees, store the values inserted into them in sorted order.

In this assignment, you will implement an iterator for your Red-Black Tree, that will enable you to retrieve the values stored in the tree in the (sorted) order that they are stored in. To achieve this, the iterator will follow an in-order traversal through the nodes of the tree.

You will implement the iterator for the Red-Black Tree in a new, instantiable class with the name RBTreeIterable that extends your RedBlackTree class from P104. An initial version of this RBTreeIterable class is part of the starter files of this assignment. Read and review the code and comments in the RBTreeIterable class before you start adding to it in the next step of this assignment.

___Requirements for the RBTreeIterable Class___

Modify the RBTreeIterable class so that it satisfies the following requirements:
- contains a field that stores the maximum for the iterator, or null if no maximum is set.
- contains a field that stores the minimum for the iterator, or null if no minimum is set.
- does not contain any additional fields besides the previous two.
- contains a setIteratorMin method that stores the minimum passed to it in the field for the minimum.
- contains a setIteratorMax method that stores the maximum passed to it in the field for the maximum.
- contains an iterator method that creates and returns a new iterator object by instantiating the inner class TreeIterator and passing the tree’s root reference and the currently set minimum and maximum to TreeIterator’s constructor.
- is clearly organized, consistently styled, and well commented.

___Requirements for the Inner TreeIterator Class___

Modify the inner TreeIterator class so that it satisfies the following requirements:

- contains a constructor that:
  * accepts the root node for the tree to iterate over, the start (minimum) value for the iterator, and the stop (maximum) value for the iterator as parameters.
  * stores the start (minimum) value passed to it in the min field of TreeIterator.
  * stores the stop (maximum) value passed to it in the max field of TreeIterator.
  * initializes the stack field for TreeIterator with a new, empty stack object.
  * calls updateStack for the argument root node to initialize the stack.
  * performs O(logn) work to finish setup, where n is the number of nodes in the tree.
- contains a updateStack method that:
  * accepts the root node of a tree as a parameter. That root node can either be the root node of an entire tree, or the root of a subtree within that bigger tree.
  * is a recursive method with one base case and two recursive cases.
  * reaches its base case and returns if the argument node is null.
  * calls itself recursively on the argument node’s right subtree if the value in the argument node is smaller than the start (minimum) point.
  * pushes the argument node onto the stack and calls itself recursively on the argument node’s left subtree if the value in the argument node is larger than or equal to the start (minimum) point.
- contains a next method that:
  * returns values from the tree in sorted, ascending order. Note that each call of next() returns a single value, values returned by multiple calls of next() are in ascending order.
  * returns only values that are equal to or larger than the set start point (minimum) and smaller than or equal to the set stop point (maximum).
  * implements an iterative in-order traversal through the nodes in the tree that contain values it returns.
  * uses the stack to find the next node to visit during the traversal.
  * calls updateStack to update the stack to contain more nodes when needed.
  * throws a NoSuchElementException if there are no more nodes to visit with values smaller than or equal to the set stop point (maximum).
  * runs in O(1) amortized time and in O(logn) worst case time, where n is the number or nodes in the tree. Do not implement this method by linearly walking through the entire tree from the smallest element until the start bound is reached. That process should occur only once during construction of the iterator object.
- contains a hasNext method that:
  * returns true if there are more nodes to visit with values smaller than or equal to the set stop point (maximum), and false otherwise.
  * is clearly organized, consistently styled, and well commented.

