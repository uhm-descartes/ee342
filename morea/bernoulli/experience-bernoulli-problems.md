---
title: "Problems in Class"
published: true
morea_id: experience-bernoulli-problems
morea_type: experience
morea_summary: "Illustration of the Bernoulli Family"
morea_start_date: "2023-10-02"
morea_labels:
---

# Problems in Class

1. **Maximum Likelihood** The Maximum Likelihood, usually abbreviated
   as ML, is going to be our first foray into statistical estimation.
   We have learnt that if $$X_1, X_2, \ldots, X_n$$ are independent
   copies of a Bernoulli $$p$$ random variable, $$Y= X_1+X_2+\ldots+
   X_n$$ is a Binomial random variable with parameters $$n$$ and
   $$p$$. We flip this around, and ask: if we saw only the \iid
   observations, $$X_1, X_2,\ldots, X_n$$, could we estimate what $$p$$ is?

   If $$X_1, X_2, \ldots, X_n$$ are generated \iid Bernoulli $$p$$,
   let the probability of $$X_1, X_2, \ldots, X_n$$ be denoted as
   $$\prob(X_1\upto X_n | p)$$. The ML principle asks to choose
   $$\hat{p}$$ in such a way that $$X_1, X_2, \ldots, X_n$$ is no less
   likely under the chosen $$\hat{p}$$ than under any other value
   $$p$$ for the parameter. Therefore we maximize, over $$p$$,
   $$\prob(X_1\upto X_n | p)$$.
   
    * Find $$\hat{p} = \arg\max \prob(X_1\upto X_n | p)$$. Now
	 $$\hat{p}$$ is a function of the random variables $$X_1\upto
	 X_n$$, and therefore a random variable itself. Express
	 $$\hat{p}$$ in terms of $$Y$$.

	* As noted above $$Y=X_1+\ldots + X_n$$. Find $$\hat{p} = \arg\max
     \prob(Y | p)$$

	* What is $$\prob(X_1\upto X_n | Y, p)$$? Note that this conditional
	  probability does not depend on $$p$$, namely that given $$Y$$,
	  $$X_1\upto X_n$$ cannot give any further information about $$p$$.
	  For this reason, $$Y$$ is called a _sufficient statistic_ for
	  \iid Bernoulli trials. Whatever we can get about $$p$$ from
	  $$X_1\upto X_n$$, we can get it from $$Y$$ alone.

   A flaw in the ML procedure is brought to light when $$Y=0$$ (or
   $$Y=n$$). Notice that when $$Y=0$$, $$\hat{p}=0$$, meaning that the
   ML model is Bernoulli 0 (and hence 0 probability of seeing a one
   ever). But, particularly if $$n$$ is small, the fact that we have
   not seen a one so far may be just coincidence, we shouldn't
   summarily exclude it from consideration altogether. It may be
   better to assign a small but non-zero value to $$p$$. In that
   sense, the ML procedure is a little aggressive on the data, and it
   perhaps overvalues the observations. This is the "unseen event"
   problem.

2. The Laplace estimator was the first approach to gauge probabilities
   of events that are unseen. This is better seen in what is known
   as the Bayesian context. Imagine now that $$p$$ is not a fixed
   quantity, but is a random variable itself. $$p$$ can take values
   in the interval $$[0,1]$$. Now we only know one continuous probability
   model, the one that assigns a uniform pdf on $$[0,1]$$.

   Let $$P$$ be a random variable uniformly distributed in $$[0,1]$$.
   As in the prior problem, given $$P$$, $$X_1\upto X_n$ are generated
   \iid $$P$$ and $$Y= X_1+\ldots + X_n$$ as before. This means
   that $$\prob(X_1\upto X_n | P) = P^Y (1-P)^{n-Y}$$. 
   

    * Find $$f( P | X_1\upto X_n)$$ using Bayes Rule. To do this, use the
      Beta-Gamma integral, that says that for integral $$k$$,

	  $$ \int_{0}^1 x^k (1-x)^{n-k} dx = \frac{k!(n-k)!}{(n+1)!}.$$

	* Therefore, 


3. **Good-Turing estimation** Here is a remarkable story on how the
   prolific statistian
   [I.J. Good](https://en.wikipedia.org/wiki/I._J._Good) and
   [A. M. Turing](https://en.wikipedia.org/wiki/Alan_Turing) (aka
   Benedict Cumberbatch from Imitation Game) broke the German Enigma
   code, shortening the war by several years. This estimator attempts
   to use \iid samples of a discrete random variable to assign a
   probability to an element that is yet unseen. Let us formalize this.

  
   
   
   Another story: in its initial years, Apple was often asked if its
   logo (an apple with a bite taken out) was a tribute to
   A.M. Turing. Turing was homosexual, and was "convicted" for it,
   chemically castrated, and publicly humiliated. A combination of
   this and other factors led to his suicide in 1954 at the age of 41,
   where a half-eaten apple was found at his side.  Turns out it was a
   coincidence. When Steve Jobs was asked about it, he replied, “God,
   we wish it were.”  It was only in 2009 that, after a long campaign
   by scientists and mathematicians that persisted after several
   objections by the British parliament, Turing was reluctantly
   "pardoned".



   

