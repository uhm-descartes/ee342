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
   $${\mathbb P}(X_1, \ldots, X_n | p)$$. The ML principle asks to choose
   $$\hat{p}$$ in such a way that $$X_1, X_2, \ldots, X_n$$ is no less
   likely under the chosen $$\hat{p}$$ than under any other value
   $$p$$ for the parameter. Therefore we maximize, over $$p$$,
   $${\mathbb P}(X_1, \ldots, X_n | p)$$.
   
    * Find $$\hat{p} = \arg\max {\mathbb P}(X_1, \ldots, X_n | p)$$. Now
	 $$\hat{p}$$ is a function of the random variables $$X_1, \ldots,
	 X_n$$, and therefore a random variable itself. Express
	 $$\hat{p}$$ in terms of $$Y$$.

	* As noted above $$Y=X_1+\ldots + X_n$$. Find $$\hat{p} = \arg\max
     {\mathbb P}(Y | p)$$

	* What is $${\mathbb P}(X_1, \ldots, X_n | Y, p)$$? Note that this conditional
	  probability does not depend on $$p$$, namely that given $$Y$$,
	  $$X_1, \ldots, X_n$$ cannot give any further information about $$p$$.
	  For this reason, $$Y$$ is called a _sufficient statistic_ for
	  \iid Bernoulli trials. Whatever we can get about $$p$$ from
	  $$X_1, \ldots, X_n$$, we can get it from $$Y$$ alone.

   A flaw in the ML procedure is brought to light when $$Y=0$$ (or
   $$Y=n$$). Notice that when $$Y=0$$, $$\hat{p}=0$$, meaning that the
   ML model is Bernoulli 0 (and hence 0 probability of seeing a one
   ever). But, particularly if $$n$$ is small, the fact that we have
   not seen a one so far may be just coincidence, we shouldn't
   summarily exclude it from consideration altogether. It may be
   better to assign a small but non-zero value for the parameter. In
   that sense, the ML procedure is a little aggressive, and it perhaps
   overvalues the observations. This is the "unseen event" or "missing
   mass" problem.

2. **Bayesian approach** The Laplace estimator was the first approach
   to gauge probabilities of events that are unseen. This is better
   seen in what is known as the Bayesian context. Imagine now that
   $$p$$ is not a fixed quantity, but is a random variable
   itself. $$p$$ can take values in the interval $$[0,1]$$. Now we
   only know one continuous probability model, the one that assigns a
   uniform pdf on $$[0,1]$$. This is called the _prior_ on the
   parameter $$P$$, and represents our (subjective) prior belief.

   Let $$P$$ be a random variable uniformly distributed in $$[0,1]$$.
   As in the prior problem, given $$P$$, $$X_1, \ldots, X_n$$ are generated
   \iid $$P$$ and $$Y= X_1+\ldots + X_n$$ as before. This means of course that
   that $${\mathbb P}(X_1, \ldots, X_n | P) = P^Y (1-P)^{n-Y}$$. 
   

    * Find $$f( P | X_1, \ldots, X_n)$$ using Bayes Rule. To do this, use the
      Beta-Gamma integral, that says that for integral $$k$$, 
	  	
		$$ \int_{0}^1 x^k (1-x)^{n-k} dx = \frac{k!(n-k)!}{(n+1)!}.$$

	   This pdf $$f( P | X_1, \ldots, X_n)$$ represents our updated belief on
	   the parameter $$P$$ after seeing the data. Look at the visualizations
	   in the associated notebook. This is therefore called the _posterior_
	   belief on the parameter $$P$$.

	* In the Bayesian way of thinking, we don't just maximize
      $$f(P|X_1, \ldots, X_n)$$. We would like all models to participate,
      but rather weight them by the posterior on $$P$$. Show that the
      expectation of $$P$$ with respect to the posterior pdf is
      $$\frac{Y+1}{n+2}$$, \ie
	  
	  $$ \int_{0}^1 p f(p|X_1,\ldots, X_n) dp = \frac{Y+1}{n+2}. $$
	  
	  You have not seen all implications of calculations like the
      above yet. But the quantity above is called the conditional
      expectation of $$P$$ given $$X_1, \ldots, X_n$$. This is a
      _Bayesian_ estimate of the parameter. Different priors (other
      than the uniform one) yield potentially different estimates of
	  the parameter, but they share some similar characteristics, and
	  in the limit of increasing $$n$$, converge on the true value
	  for sensible priors. 
	  
   Note how the Bayesian estimate assigns a non-zero value to one even
   if the sample $$X_1, \ldots, X_n$$ contains all zeros, very different
   from what the ML estimate does. This value is $$\frac1{n+2}$$, and
   diminishes as $$n$$ increases, as we should expect. It hedges
   better than the ML. When $$Y$$ is a fraction of $$n$$, say $$\frac
   13 n$$, the Bayesian and the ML estimates differ by very little.

3. **Good-Turing estimation** Here is a remarkable story on how the
   prolific statistian
   [I.J. Good](https://en.wikipedia.org/wiki/I._J._Good) and
   [A. M. Turing](https://en.wikipedia.org/wiki/Alan_Turing) (aka
   Benedict Cumberbatch from Imitation Game) broke the German Enigma
   code, shortening the war by several years. This estimator attempts
   to use \iid samples of a discrete random variable to assign a
   probability to an element that is yet unseen. Let us formalize this.
   The story of the Enigma code breaking is provided at the end.
   
   Suppose we have a pmf $$p$$ on a large countable set $$S$$. Let
   $$X_1,\ldots, X_n$$ be generated \iid from the probability law
   $$p$$. While the description below will apply to any $$S$$ and
   $$n$$, it is interesting to think of the case where the size of
   $$S$$ is $$\gg n$$, and thus we cannot expect to see every element
   of $$S$$ in $$X_1,\ldots, X_n$$. The question is: what is the
   probability of the set of elements that never showed up in the
   observation $$X_1,\ldots, X_n$$.

	* Let $$S_r(X_1,\ldots, X_n)$$ be the set of elements that show up
	exactly $$r$$ times in $$X_1,\ldots, X_n$$. $$S_r(X_1,\ldots, X_n)$$
	depends on $$X_1,\ldots, X_n$$ of course, but for the sake of notational
	convenience, we will abbreviate as just $$S_r$$. Show that
	
	$$ p(S_r) = \sum_{i\in S}p_i {\mathbf 1}
 ( \textrm{ element }i\textrm{ appeared exactly }r\textrm{ times in }X_1,\ldots, X_n ),$$
	
	where $$p_i$$ is the probability of element $$i\in S$$, and $${\mathbf 1}
(statement)$$ is a binary valued function that evaluates to 1 when the statement is true, and 0 else.
   
	
	* Find $${\mathbb E} p(S_r)$$
	
	* Let $$N_{n,r}$$ be the expected number of elements that appear exactly $$r$$ times in a sample of size $$n$$. Show that
	
	$$ N_{n,r} = \sum_{i=1}^m {n \choose r} p_i^r (1-p_i)^{n-r}, $$
	
	where $$p_i$$ is the probability of element $$i\in S$$.
	
	* Show that 
	
	 $${\mathbb E} p(S_r) = \frac{r+1}{n+1} {\mathbb E} N_{n+1,r+1}, $$
     
	 The Good Turing estimate replaces $${\mathbb E}N_{n+1,r+1}$$ by the size of 
	 $$S_{r+1}$$, i.e. the number of elements in $$S$$ that
	 show up exactly $$r+1$$ times in $$X_1,\ldots, X_n$$ as an approximation
	 for $$p(S_r)$$. Namely
	 
	 $$ p(S_r) \approx \frac{r+1}{n+1} |S_{r+1}|, $$
	 
	 where as always $$|S_{r+1}|$$ represents the size of the set
	 $$S_{r+1}$$.  In particular, the estimate says that
	 the probability of the set of elements that never showed up in
	 $$X_1,\ldots, X_n$$ ($$r=0$$) is proportional to the number of elements
	 of $$S$$ that only showed up once in $$X_1,\ldots, X_n$$:
	 
	 $$ p(S_0) \approx \frac{1}{n+1} |S_{1}|, $$
	 
	 The above is the celebrated Good-Turing estimate of the "missing mass".
	 
   **The Enigma story** The Germans had an encryption
   machine called the Enigma. The encrypting and decrypting side had
   identical machines.  Set to a password, the encrypting machine
   would produce a cipher for any plaintext message typed on it. Set
   to the same password, the decrypting machine would produce the
   original plaintext message when the cipher was typed into it. But
   without the password or the Enigma machine, the cipher appeared to
   be gibberish, and it was very hard to discern the original
   plaintext from the cipher.
   
   The Germans, wary of weak passwords, had a "dictionary" of strong
   passwords.  Passwords were distributed securely (physically), and
   were changed frequently. Turing's team had access to some physical
   Enigma machines and the dictionary, which were captured from the
   Germans. The question was figuring out which password was used. 
   
   Turing's team performed a few brute force decryptions (trying all
   passwords). This not very useful since by the time the password was
   found, the messages were dated and a new password was in effect.
   But they noticed that passwords were not truly chosen randomly, and
   some very favored more than others. The question became variants
   of: given the history of password choices, what is the probability
   that the current password is one that has never been seen before?
   
   **Another story** In its initial years, Apple was often asked if
   its logo (an apple with a bite taken out) was a tribute to
   A.M. Turing. Turing was homosexual, and was "convicted" for it,
   chemically castrated, and publicly humiliated after WW2. A
   combination of this and other factors led to his suicide in 1954 at
   the age of 41, where a half-eaten apple was found at his side.
   Turns out it was a coincidence and Steve Jobs would lament later
   how he wished the logo was a tribute to Turing. In 2009, after a
   long campaign by scientists and mathematicians who persisted after
   several objections by the British parliament, Turing was
   reluctantly "pardoned".



   

