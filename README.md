# C - Exploring Binary Trees

This collaborative project delves into the intricacies, benefits, and drawbacks of employing trees as fundamental data structures. We gain insights into classifying trees and mastering traversal techniques. Throughout our journey, we implement various types of binary trees, including binary, binary search, AVL, and Max Binary Heap trees.

## Testing :heavy_check_mark:

* [tests](./tests): Directory containing test files for all tasks, generously provided by ALX.

## Helper Functions :raised_hands:

* [binary_tree_print.c](./binary_tree_print.c): This C function elegantly prints binary trees in a visually appealing manner.

## Header File :file_folder:

* [binary_trees.h](./binary_trees.h): This header file encompasses all necessary definitions and prototypes for the project's types and functions.

Data Structures Overview
```
struct binary_tree_s
{
    int n;
    struct binary_tree_s *parent;
    struct binary_tree_s *left;
    struct binary_tree_s *right;
};

typedef struct binary_tree_s binary_tree_t;
typedef struct binary_tree_s bst_t;
typedef struct binary_tree_s avl_t;
typedef struct binary_tree_s heap_t;
```

Function Prototypes Summary

| File                             | Prototype                                                                                        |
| -------------------------------- | ------------------------------------------------------------------------------------------------ |
| `binary_tree_print.c`            | `void binary_tree_print(const binary_tree_t *tree)`                                              |
| `0-binary_tree_node.c`           | `binary_tree_t *binary_tree_node(binary_tree_t *parent, int value);`                             |
| `1-binary_tree_insert_left.c`    | `binary_tree_t *binary_tree_insert_left(binary_tree_t *parent, int value);`                      |
| `2-binary_tree_insert_right.c`   | `binary_tree_t *binary_tree_insert_right(binary_tree_t *parent, int value);`                     |
| `3-binary_tree_delete.c`         | `void binary_tree_delete(binary_tree_t *tree);`                                                  |
| `4-binary_tree_is_leaf.c`        | `int binary_tree_is_leaf(const binary_tree_t *node);`                                            |
| `5-binary_tree_is_root.c`        | `int binary_tree_is_root(const binary_tree_t *node);`                                            |
| `6-binary_tree_preorder.c`       | `void binary_tree_preorder(const binary_tree_t *tree, void (*func)(int));`                       |
| `7-binary_tree_inorder.c`        | `void binary_tree_inorder(const binary_tree_t *tree, void (*func)(int));`                        |
| `8-binary_tree_postorder.c`      | `void binary_tree_postorder(const binary_tree_t *tree, void (*func)(int));`                      |
| `9-binary_tree_height.c`         | `size_t binary_tree_height(const binary_tree_t *tree);`                                          |
| `10-binary_tree_depth.c`         | `size_t binary_tree_depth(const binary_tree_t *tree);`                                           |
| `11-binary_tree_size.c`          | `size_t binary_tree_size(const binary_tree_t *tree);`                                            |
| `12-binary_tree_leaves.c`        | `size_t binary_tree_leaves(const binary_tree_t *tree);`                                          |
| `13-binary_tree_nodes.c`         | `size_t binary_tree_nodes(const binary_tree_t *tree);`                                           |
| `14-binary_tree_balance.c`       | `int binary_tree_balance(const binary_tree_t *tree);`                                            |
| `15-binary_tree_is_full.c`       | `int binary_tree_is_full(const binary_tree_t *tree);`                                            |
| `16-binary_tree_is_perfect.c`    | `int binary_tree_is_perfect(const binary_tree_t *tree);`                                         |
| `17-binary_tree_sibling.c`       | `binary_tree_t *binary_tree_sibling(binary_tree_t *node);`                                       |
| `18-binary_tree_uncle.c`         | `binary_tree_t *binary_tree_uncle(binary_tree_t *node);`                                         |
| `100-binary_trees_ancestor.c`    | `binary_tree_t *binary_trees_ancestor(const binary_tree_t *first, const binary_tree_t *second);` |
| `101-binary_tree_levelorder.c`   | `void binary_tree_levelorder(const binary_tree_t *tree, void (*func)(int));`                     |
| `102-binary_tree_is_complete.c`  | `int binary_tree_is_complete(const binary_tree_t *tree);`                                        |
| `103-binary_tree_rotate_left.c`  | `binary_tree_t *binary_tree_rotate_left(binary_tree_t *tree);`                                   |
| `104-binary_tree_rotate_right.c` | `binary_tree_t *binary_tree_rotate_right(binary_tree_t *tree);`                                  |
| `110-binary_tree_is_bst.c`       | `int binary_tree_is_bst(const binary_tree_t *tree);`                                             |
| `111-bst_insert.c`               | `bst_t *bst_insert(bst_t **tree, int value);`                                                    |
| `112-array_to_bst.c`             | `bst_t *array_to_bst(int *array, size_t size);`                                                  |
| `113-bst_search.c`               | `bst_t *bst_search(const bst_t *tree, int value);`                                               |
| `114-bst_remove.c`               | `bst_t *bst_remove(bst_t *root, int value);`                                                     |
| `120-binary_tree_is_avl.c`       | `int binary_tree_is_avl(const binary_tree_t *tree);`                                             |
| `121-avl_insert.c`               | `avl_t *avl_insert(avl_t **tree, int value);`                                                    |
| `122-array_to_avl.c`             | `avl_t *array_to_av

l(int *array, size_t size);`                                                  |

## Task List :page_with_curl:

* **0. New Node**
  * [0-binary_tree_node.c](./0-binary_tree_node.c): This C function creates a
  new binary tree node with a given parent and value.
  * It returns a pointer to the new node, or `NULL` on failure.

* **1. Insert Left**
  * [1-binary_tree_insert](./1-binary_tree_insert): This C function inserts a
  node as the left child of another.
  * It returns a pointer to the new node, or `NULL` on failure.
  * If the given `parent` already contains a left node, the new node takes its
  place and the old left child becomes the left child of the new node.

* **2. Insert Right**
  * [2-binary_tree_insert_right.c](./2-binary_tree_insert_right.c): This C function
  inserts a node as the right child of another.
  * It returns a pointer to the new node, or `NULL` on failure.
  * If the given `parent` already contains a right node, the new node takes its
  place and the old right child becomes the right child of the new node.

* **3. Delete**
  * [3-binary_tree_delete.c](./3-binary_tree_delete.c): This C function deletes
  an entire binary tree.

* **4. Is Leaf**
  * [4-binary_tree_is_leaf.c](./4-binary_tree_is_leaf.c): This C function checks
  if a given node is a leaf.
  * It returns `1` if the node is a leaf, `0` otherwise.

* **5. Is Root**
  * [5-binary_tree_is_root.c](./5-binary_tree_is_root.c): This C function checks
  if a given node is a root.
  * It returns `1` if the node is a root, `0` otherwise.

* **6. Pre-order Traversal**
  * [6-binary_tree_preorder.c](./6-binary_tree_preorder.c): This C function
  traverses a tree using pre-order traversal.

* **7. In-order Traversal**
  * [7-binary_tree_inorder.c](./7-binary_tree_inorder.c): This C function
  traverses a tree using in-order traversal.

* **8. Post-order Traversal**
  * [8-binary_tree_postorder.c](./8-binary_tree_postorder.c): This C function
  traverses a tree using post-order traversal.

* **9. Height**
  * [9-binary_tree_height.c](./9-binary_tree_height.c): This C function returns
  the height of a binary tree.

* **10. Depth**
  * [10-binary_tree_depth.c](./10-binary_tree_depth.c): This C function returns
  the depth of a given node in a binary tree.

* **11. Size**
  * [11-binary_tree_size.c](./11-binary_tree_size.c): This C function returns
  the size of a binary tree.

* **12. Leaves**
  * [12-binary_tree_leaves.c](./12-binary_tree_leaves.c): This C function returns
  the number of leaves in a binary tree.

* **13. Nodes**
  * [13-binary_tree_nodes.c](./13-binary_tree_nodes.c): This C function returns
  the number of nodes in a binary tree with at least one child.

* **14. Balance Factor**
  * [14-binary_tree_balance.c](./14-binary_tree_balance.c): This C function
  returns the balance factor of a binary tree.

* **15. Is Full**
  * [15-binary_tree_is_full.c](./15-binary_tree_is_full.c): This C function
  checks if a binary tree is full.
  * It returns `1` if a tree is full, `0` otherwise.

* **16. Is Perfect**
  * [16-binary_tree_is_perfect.c](./16-binary_tree_is_perfect.c): This C function
  checks if a binary tree is perfect.
  * It returns `1` if a tree is perfect, `0` otherwise.

* **17. Sibling**
  * [17-binary_tree_sibling.c](./17-binary_tree_sibling.c): This C function
  returns a pointer to the sibling of a given node in a binary tree.
  * It returns `NULL` if no sibling is found.

* **18. Uncle**
  * [18-binary_tree_uncle.c](./18-binary_tree_uncle.c): This C function
  returns a pointer to the uncle of a given node in a binary tree.
  * It returns `NULL` if no uncle is found.

* **19. Lowest Common Ancestor**
  * [100-binary_trees_ancestor.c](./100-binary_trees_ancestor.c): This C function
  returns a pointer to the lowest common ancestor node of two given nodes
  in a binary tree.
  * It returns `NULL` if no common ancestor is found.

* **20. Level-order Traversal**
  * [101-binary_tree_levelorder.c](./101-binary_tree_levelorder.c): This C function
  traverses a binary tree using level-order traversal.

* **21. Is Complete**
  * [102-binary_tree_is_complete.c](./102-binary_tree_is_complete.c): This C function
  checks if a binary tree is complete.
  * It returns `1` if the tree is complete, `0` otherwise.

* **22. Rotate Left**
  * [103-binary_tree_rotate_left.c](./103-binary_tree_rotate_left.c): This C function
  performs a left-rotation on a binary tree.
  * It returns a pointer to the new root node of the tree after rotation.

* **23. Rotate Right**
  * [104-binary_tree_rotate_right.c](./104-binary_tree_rotate_right.c): This C function
  performs a right-rotation on a binary tree.
  * It returns a pointer to the new root node of the tree after rotation.

* **24. Is BST**
  * [110-binary_tree_is_bst.c](./110-binary_tree_is_bst.c): This C function
  checks if a binary tree is a valid binary search tree.
  * It returns `1` if the tree is a valid BST, `0` otherwise.

* **25. BST - Insert**
  * [111-bst_insert.c](./111-bst_insert.c): This C function inserts a value into
  a binary search tree.
  * It returns a pointer to the new node, or `NULL` on failure.
  * If the tree is `NULL`, the value becomes the root node.
  * The value is ignored if it is already present in the tree.

* **26. BST - Array to BST**
  * [112-array_to_bst.c](./112-array_to_bst.c): This C function builds a binary
  search tree from an array.
  * It returns a pointer to the root node of the created tree, or `NULL` on failure.

* **27. BST - Search**
  * [113-bst_search.c](./113-bst_search.c): This C function searches for a value
  in a binary search tree.
  * If the value is found in the BST, it returns a

 pointer to the matched node.
  * Otherwise, it returns `NULL`.

* **28. BST - Remove**
  * [114-bst_remove.c](./114-bst_remove.c): This C function removes a node from
  a binary search tree.
  * It returns a pointer to the new root node of the tree after deletion.
  * If the node to be deleted has two children, it is replaced with its first
  in-order successor.

* **29. Big O #BST**
  * [115-O](./115-O): This text file contains the average time complexities of
  binary search tree operations (one answer per line):
    * Inserting the value `n`.
    * Removing the node with the value `n`.
    * Searching for a node in a BST of size `n`.

* **30. Is AVL**
  * [120-binary_tree_is_avl.c](./120-binary_tree_is_avl.c): This C function checks if
  a binary tree is a valid AVL tree.
  * If the tree is a valid AVL tree, it returns `1`.
  * Otherwise, it returns `0`.

* **31. AVL - Insert**
  * [121-avl_insert.c](./121-avl_insert.c): This C function inserts a value into
  an AVL tree.
  * It returns a value to the inserted node, or `NULL` on failure.

* **32. AVL - Array to AVL**
  * [122-array_to_avl.c](./122-array_to_avl.c): This C function builds an AVL tree
  from an array.
  * It returns a pointer to the root node of the created AVL tree, or `NULL` on failure.
  * Duplicate values are ignored.

* **35. Big O #AVL Tree**
  * [125-O](./125-O): This text file contains the average time complexities of AVL tree
  operations (one answer per line):
    * Inserting the value `n`.
    * Removing the node with the value `n`.
    * Searching for a node in an AVL tree of size `n`.

* **41. Big O #Binary Heap**
  * [135-O](./135-O): This text file contains the average time complexities of
  binary heap operations (one answer per line):
    * Inserting the value `n`.
    * Extracting the root node.
    * Searching for a node in a binary heap of size `n`.

## Authors
<details>
    <summary>Suara Ayomide</summary>
    <ul>
    <li><a href="https://www.github.com/aysuarex">Github</a></li>
    <li><a href="https://www.twitter.com/Aysuarex">Twitter</a></li>
    <li><a href="mailto:aysuarex@gmail.com">e-mail</a></li>
    </ul>
</details>
<details>
    <summary>Jozinna Chioma</summary>
    <ul>
    <li><a href="https://www.github.com/chioma2000">Github</a></li>
    <li><a href="https://www.twitter.com/jozinnachioma">Twitter</a></li>
    <li><a href="mailto:chichipeace2000@yahoo.ca">e-mail</a></li>
    </ul>
</details>
