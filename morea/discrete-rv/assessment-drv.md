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
     Now we have a very similar looking problem, but we will only
	 specify the probability space partially. Specifying models
	 partially is quite realistic---in many applications, we cannot
	 truly get the full picture, but we still need to know what we can
	 infer from the partial model. For the following parts, we still
	 have $$n$$ coin tosses, each coin have a probability $$p$$ of
	 showing heads. But I do not tell you anything more about the
	 probability model, specifically, how the different coin tosses
	 depend on each other.
      * Can you come up with a probability model on the $$n$$ coin
	 tosses different from the independent coin flips of the previous
	 parts?
	  * Once again, for $$1\le i\le n$$, let $$X_i$$ be the indicator
      that the $$i$$'th coin toss is heads.  What is $${\mathbb E}
      X_i$$?
	  * Let $$N= X_1+ X_2 +\ldots + X_n$$. What is $${\mathbb E} N$$?  
     Notice how we can answer the above questions even though we don't
	 have the full probability model.
    
2. Let us go back to Quicksort from prior modules. In this episode, we
   will see the probability any two elements are directly compared (in
   any step) of the Quicksort algorithm run on $$n$$ elements. Recall
   the probability space we wrote for this problem.
   
   We will adopt the following notation: for $$1\le i\le n$$, we will
   denote by $$i$$, the $$i'$$th smallest element in the list. We may
   not know as soon as we see a sequence which element it is, but it
   is one of the elements in the list. 
   
   We want to know the probability that element $$i$$ and $$j$$ are
   compared. 
   
   

