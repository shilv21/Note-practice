# Grokking Algorithms Notes

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Grokking Algorithms is a book which introduces and visualizes some basic Algo. Therefore, this note will be in the following schema:

  - Idea of the algorithm
  - Time complexity
  - Further information

# Big O notation!

  - Big O notation is special notation that tells you how fast an algorithm is. 
  - Algorithm times are measured in terms of growth of an algorithm.
  - The constant in Big O notation can matter sometimes. That’s why
    quicksort is faster than merge sort.
  - Some common Big O run times:
    • O(log n), also known as log time. Example: Binary search.
    • O(n), also known as linear time. Example: Simple search.
    • O(n * log n). Example: A fast sorting algorithm, like quicksort
    (coming up in chapter 4).
    • O(n<sup>2</sup>). Example: A slow sorting algorithm, like selection sort
    (coming up in chapter 2).
    • O(n!). Example: A really slow algorithm, like the traveling
salesperson (coming up next!).

# Data structure
When you want to store multiple elements, use an **array**, **hash table**, **tree** , or a **linked list**.
There are some other useful data structure: **Inverted indexes**.
  - **Arrays** allow fast reads.
  - **Linked list** allow fast inserts and deletes.
  - **Hash tables** have really fast search, insert, and delete. **Hash tables** are good for modeling relationships from one item to another item.
  - **Binary search tree** is aimed at searching with  O(log n) time on average
and O(n) time in the worst case but a lot faster for insertions and deletions on average.
  - **Inverted indexes** is a useful data structure: a hash that maps words to places where they appear.

# Basic Algorithms

## Binary Search
  - Binary search is an algorithm; its input is a sorted list of elements. With
binary search, you guess the middle number and eliminate half the
remaining numbers every time
  - Binary search runs in logarithmic time O(log _n_)

## Recursion
  - Recursion is when a function calls itself.
  - Every recursive function has two cases: the base case
    and the recursive case.
  - A stack has two operations: push and pop.
  - All function calls go onto the call stack.
  - The call stack can get very large, which takes up a lot of memory.

## Devide & Conquer | Quick Sort
### Devide & Conquer
D&C algorithms are recursive algorithms. To solve a problem using D&C, there are two steps:
1. Figure out the base case. This should be the simplest possible case.
2. Divide or decrease your problem until it becomes the base case.

### Quick Sort
Quicksort is a sorting algorithm. It’s much faster than selection sort
and is frequently used in real life. Here are the steps:

>  1. Pick a pivot.
>  2. Partition the array into two sub-arrays: elements less than the pivot
and elements greater than the pivot.
>  3. Call quicksort recursively on the two sub-arrays

In the worst case, quicksort takes O(n<sup>2</sup>) time. In the average
case, quicksort takes O(_n_ log _n_) time. In practice, it hits the average case way more often than the worst case.

## Breadth-first search
- Breadth-first search tells you if there’s a path from A to B.
- If there’s a path, breadth-first search will find the shortest path.
- If you have a problem like “find the shortest X,” try modeling your
    problem as a graph, and use breadth-first search to solve.
- A directed graph has arrows, and the relationship follows the
    direction of the arrow (rama -> adit means “rama owes adit money”).
- Undirected graphs don’t have arrows, and the relationship goes both
    ways (ross - rachel means “ross dated rachel and rachel dated ross”)
- Breadth-first search is used to calculate the shortest path for
an unweighted graph.

## Dijkstra's algorithm
There are four steps to Dijkstra’s algorithm:
> 1.Find the “cheapest” node. This is the node you can get to in the least
amount of time.
> 2.Update the costs of the neighbors of this node. I’ll explain what I
mean by this shortly.
> 3.Repeat until you’ve done this for every node in the graph.
> 4.Calculate the final path.

Dijkstra’s algorithm is used to calculate the shortest path for
a weighted graph.
Dijkstra’s algorithm works when all the weights are positive.
If you have negative weights, use the Bellman-Ford algorithm

## Greedy Algorithm
Greedy Algorithm solves NP-problem using an approximation technique. Here are some notes:
- Greedy algorithms optimize locally, hoping to end up with a global
optimum.
- NP-complete problems have no known fast solution.
- If you have an NP-complete problem, your best bet is to use an
approximation algorithm.
- Greedy algorithms are easy to write and fast to run, so they make
good approximation algorithms.

## Dynamic Programming
Dynamic programming is an approximation solution. Dynamic programming starts by
solving subproblems and builds up to solving the big problem.
- Dynamic programming is useful when you’re trying to optimize
something given a constraint.
- You can use dynamic programming when the problem can be
broken into discrete subproblems.
- Every dynamic-programming solution involves a grid.
- The values in the cells are usually what you’re trying to optimize.
- Each cell is a subproblem, so think about how you can divide your
problem into subproblems.
- There’s no single formula for calculating a dynamic-programming
solution

## K-nearest neighbors
KNN is approximation solution which is used for classification and regression and involves looking at the k-nearest neighbors. It calculates the distance between a considered point and a set of nearest points to predict considered point's value. Here are some notes:
- KNN require feature extraction which means converting an item (like a fruit or a user) into a list of numbers that can be compared.
- KNN is used for recommended system,classification and regression.
- Picking good features is an important part of a successful KNN
algorithm.



## The Fourier Transform
Given a smoothie, the Fourier transform will tell you the
ingredients in the smoothie. Or, to put it another way, given a song, the
transform can separate it into individual frequencies.

## Parallel algorithms
Parallel algo is about scalability and working with a lot of data. It makes multiple cores solution. It is hard to design because a couple of reasons:
- Overhead of managing the parallelism
- Load balancing

## Map Reduce
There’s a special type of parallel algorithm that is becoming increasingly
popular: the distributed algorithm. 
- MapReduce uses these two simple concepts to run queries about data across multiple machines. When you have a large dataset (billions of rows), MapReduce can give you an answer in minutes where a traditional database might take hours.
- You can use it through the popular open source tool
Apache Hadoop.

## Bloom filters and HyperLogLog
This is lookup algorithm. Hash table is the first choice but when there is so much data, you need to get creative!
### Bloom filter
- Bloom filters offer a solution. Bloom filters are probabilistic data
structures. They give you an answer that could be wrong but is probably
correct.
- Bloom filters are great because they take up very little space.

### HyperLogLog
- HyperLogLog approximates the number of unique elements in a set.
Just like bloom filters, it won’t give you an exact answer, but it comes
very close and uses only a fraction of the memory a task like this would
otherwise take.
- If you have a lot of data and are satisfied with approximate answers,
check out probabilistic algorithms! 

## SHA algorithms
- Another hash function is a secure hash algorithm (SHA) function.
- SHA is actually a family of algorithms: SHA-0, SHA-1, SHA-2, and
SHA-3. As of this writing, SHA-0 and SHA-1 have some weaknesses.
If you’re using an SHA algorithm for password hashing, use SHA-2 or
SHA-3. The gold standard for password-hashing functions is currently
bcrypt (though nothing is foolproof). 
- SHA has another important feature: it’s locality insensitive: **Locality-sensitive hashing**. It is usefull when you want to check for similar items.

## Diffie-Hellman key exchange
Diffie-Hellman encryptes a message. It has two keys: a public key and a private key

## Linear Programming
- Linear programming is used to maximize something given some
constraints.
- Linear programming uses the Simplex algorithm. 



