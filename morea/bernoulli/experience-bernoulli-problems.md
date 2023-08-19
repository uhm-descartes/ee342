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

	* What is $${\mathbb P}(X_1, \ldots, X_n | Y, p)$$? This question
	  anticipates the next module. Note that this conditional
	  probability does not depend on $$p$$, namely that given $$Y$$,
	  $$X_1, \ldots, X_n$$ cannot give any further information about
	  $$p$$.  For this reason, $$Y$$ is called a _sufficient
	  statistic_ for \iid Bernoulli trials. Whatever we can get about
	  $$p$$ from $$X_1, \ldots, X_n$$, we can get it from $$Y$$ alone.

   A flaw in the ML procedure is brought to light when $$Y=0$$ (or
   $$Y=n$$). Notice that when $$Y=0$$, $$\hat{p}=0$$, meaning that the
   ML model is Bernoulli 0 (and hence 0 probability of seeing a one
   ever). But, particularly if $$n$$ is small, the fact that we have
   not seen a one so far may be just coincidence, we shouldn't
   summarily exclude it from consideration altogether. It may be
   better to assign a small but non-zero value for the parameter. In
   that sense, the ML procedure is a little aggressive, and it perhaps
   overvalues the observations. This is the "unseen event" or "missing
   mass" problem. We will look at it in the next module.


2. **Communication Link** We have looked at a basic Binary Symmetric
   Channel. Here is a Binary Erasure Channel, more in line with the
   engineering approach to sending data in packets on the Internet. In
   a binary erasure channel, the input is a bit. Given an input bit,
   the output equals the input with probability $$1-\epsilon$$ or an
   erasure with probability $$\epsilon$$. For the sake of notation, we
   will denote an erasure by the number $$\frac12$$. In this case, if
   you see a bit at the output, you know the channel introduced no
   error. If you see an erasure, you do not know what the input
   is. Let the input be $$X$$, taking values in $$\{0,1\}$$, and the
   output is $$Y$$, taking values in $$\{0,1,$$\frac12$$\}$$. Assume
   $$X$$ is Bernoulli $$p$$.

    * Let $$E = {\mathbb 1}(|X_Y|>0)$$. Note that $$E$$ is an
      indicator for an erasure (it is 1 if there is an erasure and 0
      if not). Show that $$E$$ is independent of $$X$$
	* What is the conditional distribution on $$X$$ given (i) $$Y=0$$,
      (ii) $$Y=\frac12$$, and (iii) $$Y=1$$.
   
   Consider a variation of the above. The channel is used $$n$$ times,
   and the channel acts on each input bit as described above
   independently of what happened in other channel uses (I need to
   specify this, since there are other ways the channel could behave
   and still be consistent with the prior information). There is an
   oracle with the BEC who tells the transmitter whether or not the
   input bit goes through or whether it was erased. Consider the
   following natural oracle-aided communication strategy: the
   transmitter retransmits a bit till it goes through. Depending on
   how many erasures happen among the $$n$$ channel uses, the number
   of bits that make it across the receiver changes. Let $$Z_i$$ be a
   Bernoulli variable that indicates if an erasure happened in the
   $$i'$$th channel use. Let $$R_n$$ denote the number of transmitted
   bits. 
   
   The rate of transmission is defined to be $$\lim_{n\to\infty}
   \frac{{\mathbb E} R_n}n$$.
  
    * Show that $${\mathbb E} R_n = n(1-\epsilon)$$. Therefore, the
      rate of transmission of information is $$1-\epsilon$$.
	
   Incidentally, it can be shown (though it is a lot harder) that you
   can achieve arbitrarily close to this rate even without an
   oracle. And more remarkably, it can also be shown that no scheme
   can do better than this. The quantity $$1-\epsilon$$ is called
   the _capacity_ of a channel, the maximum amount of information
   that we could push through. It is a fundamental limit associated
   with channels. 
   
   Most of you have probably never seen a telephone dialup modem,
   which used the voice range of the telephone line to carry internet
   data. The capacity of such a channel, calculated using the same
   theory as above, was 56k bits/second. This is a fundamental speed
   limit, and no technology can circumvent the 56k barrier on the
   voice range of a telephone channel. Therefore, DSL was developed to
   incorporate frequencies outside the voice range. Today, the speed
   increases Hawaii Telecom touts for DSL typically results from
   shortening distances to the first digital link in the provider
   infrastructure. Similarly, the evolution from the 2G -> 3G -> 4G ->
   5G networks with increasing communication speeds resulted in
   figuring out ever more creative ways to build effective channels
   with greater capacities, for example, by using more antennas,
   packet or message switching.

   

   
   
   
