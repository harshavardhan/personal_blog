---
title: "Why (not to) ask DSA qns in dev interviews"
date: 2021-03-11T23:18:31+05:30
<!-- draft: true -->
description: "Logging some questions I was asked"
tags: [dsa]
---

I'll let you all know my views on the post title some other day

Here are some questions I was asked (with ideas for some) sorted by most interesting to me

---

Given an array of n _unique_ non-negative integers, find out the smallest non-negative number which is not present in the array in $O(n)$ time

_(Idea)_ Observe that if array is of length n, our answer will be atmost n. If we find an element x lying in [0,n-1], we'll try to place x in its indexed position by swapping it with arr[x]. If x is greater than n-1, we'll leave it in its current index (might get swapped later to some random index). Finally we'll find the minimum index i such that i != arr[i]. If no such index is found, answer is n

---

Given an almost sorted array which is generated by k swaps from an (increasingly) sorted array, find how to sort this array better than the usual $O(n\log{}n)$ sorting

_(Hint)_ Try to do it in $O(n + k\log{}k)$ time

_(Idea)_ Find the probably swapped elements. You can get 2k such elements. Sort them in $k\log{}k$ time and merge with the remaining sorted array similar to linear merge of two sorted arrays in mergesort (You can find this described in detail [here](https://stackoverflow.com/a/62791654))

---

Simulate a 2 player tic-tac-toe. For a general $n*m$ grid, check if runtime of your code is $O(nm)$

---

_(From a friend)_ In an organization, process an input stream of triplets of the form :

- <set_manager,M,B> : indicates that M is the direct manager of B

- <set_peer,A,B> : indicates that A and B have the same direct manager

- <is_manager,M,A> : print whether M is the direct manager of A

_(Hint)_ If you think the solution is obvious, work this example out

- set_peer 1 2
- set_manager 10 11
- set_peer 1 11

is_manager 10 2 should return true

---

Implement an LRU cache with size capacity with get and put functions

- get(key)
- put(key,value)

---

Trapping rain water problem

_(Followup)_ 2D trapping rain water

---

Given two (increasingly) sorted arrays a and b, we wish to print the common elements between two. Note that the sorted arrays can have repeated elements and we wish to print a repeated element x only c times where c is the minimum among number of times x is found in a and b

_(Idea)_ Similar to linear merge of two sorted arrays in mergesort by using two pointers

_(Followup)_ If length of b is small, do it in $O(b \log{}a)$ time

_(Idea)_ We try to binary search each element x of b in a. To account for repeated elements, if x exists we'll have to find the least index l and the highest index h of x. If x occurs y times in b, we'll output x for $min(y,h-l+1)$ times

---

Given two strings a and b, find out if string b is an anagram of some substring of a

_(Idea)_ b is an anagram of substring c of a if frequencies of each character in b and c match. We'll start with a b.length() window of a and check if the frequencies of characters match. If they don't match, we'll move the window to the right by 1 and update the frequencies in $O(1)$

---

Implement binary exponentiation for a float

_(Followup)_ Extend to exponent < 0

---

Given an alphanumeric string with also some ( and ), try to print a valid bracketed string using minimum number of character deletions

---

> Most of these qns are common interview ones - not so original and can be easily found on the internet
