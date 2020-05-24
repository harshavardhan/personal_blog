---
title: "Poker Hand rank evaluation"
date: 2020-05-24T17:13:06+05:30
<!-- draft: true -->
description : "Notes on Kevin Suffecool's 5-card hand evaluator"
tags : [poker]
---

Recently when I was thinking of writing a Poker app for fun, I wondered how Poker engines evaluate hands quickly. Then I came across Kev's poker hand evaluator. I recommend you to go through [this](http://suffe.cool/poker/evaluator.html) well-written (original) article. 

Below is a summary. (Make sure you understand the details in the link mentioned above before reading any further)

As a pre-processing step, we try to enumerate all 5-card hands and assign them a number as its rank. The number of enumerated 5-card hands is $\binom{52}{5} = 2598960$. On counting the number of distinct ranked hands, we find that there are 7462 distinct ranked hands. ([Here](https://gist.github.com/harshavardhan/52cfa8c55e0a2a27f32f251147d965c7) is a code snippet I wrote to count the number of distinct ranked hands) 

When we have seven cards (2 in-hand cards + 5 board cards), we go through all of the available $\binom{7}{5} = 21$ hands and choose the best-ranked hand among them.

By storing the rank as a short (16 bits), with a lookup table of size 2598960 (5 MB), we can evaluate the rank of a 5-card hand by a single lookup. Note that hashing and lookup might be expensive. 

Imagine the case where the lookup table is a map. Each lookup takes $O(\log{}n)$ time. If we had a more simple hash function like mapping the cards to a number between $1$ and $52^5 \approx 4 \times 10^8$ (760 MB), we could get away with an $O(1)$ lookup at the expense of larger table size.

Now coming to Kev's method, we have an evaluation to find out if the hand is a flush. After that, we have an index evaluation. We use this index for looking up rank in the flush case (flushes array) or straight/high-card case (unique5 array). 

If both of them fail, we have a product evaluation, and then we binary search for the product among products array and then lookup the values array after finding the index in products array.

We tabulate below the sizes for the respective arrays.

| Array name | Size         |
|------------|--------------|
| flushes    | 7937 (16 KB) |
| unique5    | 7937 (16 KB) |
| products, values   | 4888 (10 KB) |

(When 5 bits are set among 13, the smallest is 31, and the largest is 7936. So we have a lookup table of size 7937. There are only 4888 distinct products)

Despite doing a binary search, we still managed to cut down the number of operations and reduce the memory footprint of the program considerably.

Paul Senzee [wrote](http://senzee.blogspot.com/2006/06/some-perfect-hash.html) a perfect hash to make the last step into an unordered map like lookup instead of a binary search, in fact speeding it up further.

This evaluator may not be so relevant in current day scenarios where having a large read-only lookup table in memory might not be so costly and problematic. 

Present-day evaluators use a 7-card table lookup directly instead of iterating through all possible 5-hands. One such famous evaluator is the *Two Plus Two hand evaluator* (130 MB in size), where you give the evaluator your 7-cards, and it returns the rank directly. (this particular evaluator works like a state machine)

Is doing evaluations like these on the client side a good idea to cut down server costs?

> TODO: Compare the performance of Kev's implementation with just a $\binom{52}{5}$ sized map lookup