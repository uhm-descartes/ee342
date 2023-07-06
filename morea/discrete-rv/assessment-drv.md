---
title: "Problems in class"
published: true
morea_id: assessment-rv
morea_summary: "Random Variables"
morea_outcomes_assessed:
  - outcome-rv
morea_type: assessment
morea_start_date: "2023-09-18"
morea_labels:
---
# Problems in class

These problems will show you the power of formalism. You have
implicitly used random variables before, and it may not be clear why
we make this so formal. The first example is primarily to get our feet
wet. The next one, on Quicksort, shows the power of this approach.

1. **Coin Tosses** Suppose we have $$n$$ independent coin tosses, each
coin having a probability of showing heads to be $$p$$. In prior
modules, we worked out cases for a specific, small value of $$n$$, now
we can wade in a little deeper.
	 * Write a sample space for the experiment.
	 * For $$1\le i\le n$$, let $$X_i$$ be the indicator that the
      $$i$$'th coin toss is heads. Note the explanation of indicator
      from class, this will be very commonly reused. What is
      $${\mathbb E} X_i$$?
	 * Let $$N= X_1+ X_2 +\ldots + X_n$$. $$N$$ is now another random
      variable. What would be a good interpretation for this random
      variable?
	 * What is $${\mathbb E} N$$?  
     
	 Now we will pose a very similar looking problem, but we will only
	 specify the probability space partially. Specifying models
	 partially is quite realistic---in many applications, we cannot
	 truly get the full picture, but we still need to know what we can
	 infer from the partial model. For the following parts, we still
	 have $$n$$ coin tosses, each coin have a probability $$p$$ of
	 showing heads. But I do not tell you anything more about the
	 probability model, specifically, how the different coin tosses
	 depend on each other.
      * Can you come up with a probability model on the $$n$$ coin
	 tosses, but something different from the independent coin flips of
	 the previous part?
	  * Once again, for $$1\le i\le n$$, let $$X_i$$ be the indicator
      that the $$i$$'th coin toss is heads.  What is $${\mathbb E}
      X_i$$?
	  * Let $$N= X_1+ X_2 +\ldots + X_n$$. What is $${\mathbb E} N$$?  
     
	 Notice how we can answer the above questions even though we don't
	 have the full probability model.
    
2. **Quicksort** Let us go back to Quicksort from prior modules. In
   this episode, we will see the probability any two elements are
   directly compared (in any step) of the Quicksort algorithm run on
   $$n$$ elements, and thereby compute the average number of
   comparisons required for any sequence. Recall the probability space
   we wrote for this problem, but assume that the starting sequence is
   fixed. Equivalently, we are conditioning on the starting sequence.
   
   We will adopt the following notation: for $$1\le i\le n$$, we will
   denote by $$e_i$$, the $$i'$$th smallest element in the list. We may
   not know as soon as we see a sequence which element it is, but it
   is one of the elements in the list. 
   
   We want to know the probability that element $$e_i$$ and $$e_j$$
   are compared. To get this probability, we make the following
   observation: let $$S = \{ e_i, e_{i+1}, \ldots, e_{j-1},
   e_j\}$$. In the beginning, all elements of $$S$$ are in the same
   group (all $$n$$ elements are).  As long as no element of $$S$$ is
   chosen as the pivot, all elements of $$S$$ continue to be in the
   same group (and no element of $$S$$ is compared with any other
   element of $$S$$). The set $$S$$ gets split into two groups the
   moment an element of $$S$$ gets chosen as the
   pivot. And if so, during the split, $$e_i$$ and $$e_j$$ are
   compared directly only if one of $$e_i$$ or $$e_j$$ is chosen
   as the pivot. If not, $$e_i$$ and $$e_j$$ are never compared 
   directly in any future step (since they will now be in different groups).
   
   * What is the probability that, given that a pivot is chosen among
	 the elements of $$S$$, the pivot is either $$e_i$$ or $$e_j$$?
	 This is also the probability that $$e_i$$ and $$e_j$$ are
	 compared directly in any step of the Quicksort algorithm.
   * Let $$I(i,j)$$ be the indicator for whether $$e_i$$ and $$e_j$$ are ever
	 directly compared in the entire run of the Quicksort algorithm. What
	 is $${\mathbb E} I(i,j)$$?
	 
   Believe it or not, we now know the average running time of the Quicksort
   Algorithm. Let
   
   $$M= \sum_{1\le i\le n} \sum_{ i \le j\le n} I(i,j)$$
   
    * What is a good interpretation for $$M$$?
	* What is $${\mathbb E} M$$?
   
   And there you go! You have done the first grown-up analysis. $$M$$
   is random, and depends on the choice of pivots. Different random
   choices could lead to different values of $$M$$. But what we show
   is that the average value of $$M$$ is $${\mathcal O}(n\log n)$$,
   far smaller than the worst case value of $$n(n-1)/2$$ (where every
   pair of elements are compared). We haven't fully understood the
   ramifications of the expectation, but we will pick up this thread
   in later chapters.


