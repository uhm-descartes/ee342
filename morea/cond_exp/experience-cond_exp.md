---
title: "Problems in Class"
published: true
morea_id: experience-cond_exp-prob
morea_type: experience
morea_summary: "CHANGE ME"
morea_start_date: "2023-11-08"
morea_labels:
---

# Problems in Class

1. **Bayesian approach** The
   [Laplace](https://en.wikipedia.org/wiki/Pierre-Simon_Laplace)
   estimator was the first approach to gauge probabilities of events
   that are unseen. Laplace had this
   [question](https://en.wikipedia.org/wiki/Sunrise_problem): given
   that we have seen the sun rise for the last $$n$$ days, what is the
   probability it will rise tomorrow?
      
   We will understand Laplace's estimator in the Bayesian
   context. Imagine now that the Bernoulli parameter is not a
   fixed quantity as we have seen it thus far, but is a random
   variable, which we will denote by $$P$$. The parameter can take
   values in the interval $$[0,1]$$. Now we only know one continuous
   probability model so far, the one that assigns a uniform pdf on
   $$[0,1]$$. Let us use this to model how the parameter is
   chosen. This probability model on the parameter is called the
   _prior_ on the parameter $$P$$, and represents our (subjective)
   prior belief.

   So we let $$P$$ be a random variable uniformly distributed in $$[0,1]$$.
   As in the prior problem, given $$P$$, $$X_1, \ldots, X_n$$ are generated
   \iid $$P$$ and $$Y= X_1+\ldots + X_n$$ as before. This means of course that
   that $${\mathbb P}(X_1, \ldots, X_n | P) = P^Y (1-P)^{n-Y}$$. 
   

    * Find $$f( P | X_1, \ldots, X_n)$$ using Bayes Rule. This step is
	  why the procedure is called "Bayesian". We know the data
	  generating models, $${\mathbb P}(X_1,\ldots, X_n|P)$$ as well as
	  the prior over $$P$$, and we need to invert the order of
	  conditioning with the Bayes rule. Thus far, we have only used
	  Bayes rule with discrete random variables. Here $$P$$ is
	  continuous, but the good news is that even when continuous
	  random variables are involved, the Bayes rule holds in the same
	  form as the discrete case, replacing pmfs/probabilities with
	  pdfs/evaluations of pdfs at points. Despite the fact that the
	  evaluation of a pdf at a particular point is **not** a
	  probability (and can be greater than 1). See Chapter 3.6 in the
	  text if you need to review this later. 
	  
	  For simplification, you may find the Beta-Gamma integral
	  useful---for integral $$k\ge 0$$,
	  	
		$$ \int_{0}^1 x^k (1-x)^{n-k} dx = \frac{k!(n-k)!}{(n+1)!}.$$

	   This pdf $$f( P | X_1, \ldots, X_n)$$ can be interpreted as our
	   updated belief on the parameter $$P$$ after seeing the
	   data. Look at the visualizations in the associated
	   notebook. This is therefore called the _posterior_ belief on
	   the parameter $$P$$.

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
	exactly $$r$$ times in $$X_1,\ldots, X_n$$. $$S_r(X_1,\ldots,
	X_n)$$ depends on $$X_1,\ldots, X_n$$ of course, but for the sake
	of notational convenience, we will abbreviate as just
	$$S_r$$. $$S_r$$ maps the sample space to a set (it is a more
	general kind of random variable, rather than just being real
	valued, but we will not worry too much about it). Show that
	
	$$ p(S_r) = \sum_{i\in S}p_i {\mathbf 1}
 ( \textrm{ element }i\textrm{ appeared exactly }r\textrm{ times in }X_1,\ldots, X_n ),$$
	
	where $$p_i$$ is the probability of element $$i\in S$$, and
    $${\mathbf 1} (statement)$$ is a binary valued function that
    evaluates to 1 when the statement is true, and 0 else. $$p(S_r)$$
    is therefore a random variable.
   
	* Let $$N_{n,r}$$ be the expected number of elements that appear
      exactly $$r$$ times in a sample of size $$n$$. Show that
	
	  $$ N_{n,r} = \sum_{i=1}^m {n \choose r} p_i^r (1-p_i)^{n-r}, $$
	
	  where $$p_i$$ is the probability of element $$i\in S$$.
	
	* Show that 
	
	  $${\mathbb E} p(S_r) = \frac{r+1}{n+1} {\mathbb E} N_{n+1,r+1}, $$
     
	 The Good Turing estimate replaces $${\mathbb E}N_{n+1,r+1}$$ by
	 the size of $$S_{r+1}$$, i.e. the number of elements in $$S$$
	 that show up exactly $$r+1$$ times in $$X_1,\ldots, X_n$$. The
	 estimate, which we will denote by $$\hat{p}$$, is therefore also
	 a random variable, and is given by
	 
	 $$ \hat{p}(S_r) \approx \frac{r+1}{n+1} |S_{r+1}|, $$
	 
	 where again $$|S_{r+1}|$$ represents the size of the set
	 $$S_{r+1}$$.  In particular, the estimate says that
	 the probability of the set of elements that never showed up in
	 $$X_1,\ldots, X_n$$ ($$r=0$$) is proportional to the number of elements
	 of $$S$$ that only showed up once in $$X_1,\ldots, X_n$$:
	 
	 $$ \hat{p}(S_0) \approx \frac{1}{n+1} |S_{1}|, $$
	 
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
   how he wished that the Apple logo was indeed designed to be a
   tribute to Turing. In 2009, after a long campaign by scientists and
   mathematicians who persisted despite several objections by the
   British parliament, Turing was reluctantly "pardoned".

