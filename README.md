Download Link: https://assignmentchef.com/product/solved-cs161-homework-1-single-boolean-lisp-function
<br>
An ordered tree is either a number n or a list (L m R), where

<ul>

 <li>L and R are ordered trees;</li>

 <li>m is a number;</li>

 <li>all numbers appearing in L are smaller than m; – all numbers appearing in R are larger than m.</li>

</ul>

Some examples of ordered trees: 3, (1 2 3), ((1 2 3) 7 8), ((1 2 3) 5 (6 8 (9 10 (11 12 13)))).

<ol>

 <li>Write a single Boolean LISP function, called TREE-CONTAINS, which takes two arguments N and TREE, and checks whether number N appears in the ordered tree TREE.</li>

</ol>

For example,




(TREE-CONTAINS 3 ‘((1 2 3) 7 8)) returns T

(TREE-CONTAINS 4 ‘((1 2 3) 7 8)) returns NIL




<ol start="2">

 <li>Write a single LISP function, called TREE-MIN, which takes one argument TREE, and returns the minimum number appearing in the ordered tree TREE.</li>

</ol>




For example,




(TREE-MIN ‘((1 2 3) 7 8)) returns 1




<ol start="3">

 <li>Write a single LISP function, called TREE-ORDER, which takes one argument TREE, and returns an pre-ordered list of the numbers appearing in the ordered tree TREE.</li>

</ol>




For example,




(TREE-ORDER 3) returns (3)

(TREE-ORDER ‘((1 2 3) 7 8)) returns (7 2 1 3 8)




<ol start="4">

 <li>Write a single LISP function, called SUB-LIST, that takes a list L and two non-negative integers</li>

</ol>

START and LEN, and returns the sub-list of L starting at position START and having length LEN. Assume that the first element of L has position 0.




For example,




(SUB-LIST ‘(a b c d) 0 3) returns (a b c)

(SUB-LIST ‘(a b c d) 3 1) returns (d)

(SUB-LIST ‘(a b c d) 2 0) return s NIL




<ol start="5">

 <li>Write a single LISP function, called SPLIT-LIST, that takes a list L, and returns a list of two lists L1 and L2, in that order, such that</li>

</ol>




–         L is the result of appending L1 and L2; –      Length of L1 minus length of L2 is 0 or 1.




For example,




(SPLIT-LIST ‘(a b c d)) returns ((a b) (c d))

(SPLIT-LIST ‘(a b c d e)) returns ((a b c) (d e))    NOTE: ((a b) (c d e)) is incorrect;  (SPLIT-LIST ‘(a b c d e f)) returns ((a b c) (d e f))




You can call the function SUB-LIST from SPLIT-LIST.







A binary tree is one in which each node has 0 or 2 children. A node that has 0 child is called a leaf node. A node that has 2 children is called an internal node. A binary tree can be represented as follows:




<ul>

 <li>A leaf node N is represented by atom N;</li>

 <li>An internal node N is represented by a list (L R), where L represents the left child of N and R represents the right child of N.</li>

</ul>




<ol start="6">

 <li>Write a single LISP function, called BTREE-HEIGHT, which takes a binary tree TREE, and returns the height of TREE. Note that the height of a binary tree is defined as the length of the longest path from the root node to the farthest leaf node.</li>

</ol>




For example,

<strong> </strong>

(BTREE-HEIGHT 1) returns 0

(BTREE-HEIGHT ‘(1 2)) returns 1

(BTREE-HEIGHT ‘(1 (2 3))) returns 2

(BTREE-HEIGHT ‘((1 2) (3 4))) returns 2

(BTREE-HEIGHT ‘((1 (2 3)) ((4 5) (6 7)))) returns 3

(BTREE-HEIGHT ‘(((1 2) (3 4)) ((5 6) (7 8)))) returns 3




<ol start="7">

 <li>Write a single LISP function, called LIST2BTREE, that takes a non-empty list of atoms LEAVES, and returns a binary tree such that</li>

</ol>




<ul>

 <li>The tree leaves are the elements of LEAVES;</li>

 <li>For any internal (non-leaf) node in the tree, the number of leaves in its left branch minus the number of leaves in its right branch is 0 or 1.</li>

</ul>




For example,




(LIST2BTREE ‘(1)) returns 1

(LIST2BTREE ‘(1 2)) returns (1 2)

(LIST2BTREE ‘(1 2 3)) returns ((1 2) 3)

(LIST2BTREE ‘(1 2 3 4)) returns ((1 2) (3 4))

(LIST2BTREE ‘(1 2 3 4 5 6 7)) returns (((1 2) (3 4)) ((5 6) 7))

(LIST2BTREE ‘(1 2 3 4 5 6 7 8)) returns (((1 2) (3 4)) ((5 6) (7 8)))




You can call the function SPLIT-LIST from LIST2BTREE.




<ol start="8">

 <li><strong>8</strong>. Write a single LISP function, called BTREE2LIST, that takes a binary tree TREE as input, and returns a list of atoms (assume TREE follows the constraints we defined earlier).</li>

</ol>




<ul>

 <li>As the input is a binary tree, each node has at most 2 children;</li>

 <li>This function is the inverse of LIST2BTREE. That is, (BTREE2LIST (LIST2BTREE X)) = X for all lists of atoms X.</li>

</ul>




For example,




(BTREE2LIST 1) returns (1)

(BTREE2LIST ‘(1 2)) returns (1 2)

(BTREE2LIST ‘((1 2) 3)) returns (1 2 3)

(BTREE2LIST ‘((1 2) (3 4))) returns (1 2 3 4)

(BTREE2LIST ‘(((1 2) (3 4)) ((5 6) 7))) returns (1 2 3 4 5 6 7)

(BTREE2LIST ‘(((1 2) (3 4)) ((5 6) (7 8)))) returns (1 2 3 4 5 6 7 8)

<ol start="9">

 <li><strong>9</strong>. Write a single Boolean LISP function, called IS-SAME, that takes two LISP expressions E1 and E2 whose atoms are all numbers, and checks whether the expressions are identical. In this question, you can only use ‘=‘ to test equality (you cannot use ‘equal’). Recall that a LISP expression is either an atom or a list of LISP expressions.</li>

</ol>




For example,




(IS-SAME  ‘((1 2 3) 7 8)  ‘((1 2 3) 7 8)) returns T

(IS-SAME  ‘(1 2 3 7 8)  ‘((1 2 3) 7 8)) returns NIL