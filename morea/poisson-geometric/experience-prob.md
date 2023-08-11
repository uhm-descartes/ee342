---
title: "Problems in Class"
published: true
morea_id: experience-pg-prob
morea_type: experience
morea_summary: "Geometric and Poisson random variables"
morea_start_date: "2023-10-09"
morea_labels:
---

# Problems in Class

1. Let $$X$$ and $$Y$$ be independent Geometric $$p$$ random variables. Show that 

	$$\prob(X = i | X+Y = n) = \frac1{n-1}, \qquad \textrm{ for } i = 1,2,\ldots, n-1. $$
	
2. **Maximum entropy models** A lot of physical systems are modeled
   with what is known as the maximum entropy approach. This is very
   common in statistical mechanics, but also while modeling weather,
   in geology, in ocean sciences, and many other domains, where one
   models a complex phenomenon, and therefore adopts a probabilistic
   description of the phenomenon. Let $$X$$ be a random variable
   taking values in $$\{1,2,3, \ldots\}$$ (ie any natural number), and
   suppose we know that $$\E X = \mu$$. We want the probability model
   for $$X$$, and just knowing the expectation doesn't give us the
   probability model. Furthermore, doing experiments to find out the
   probability of each number is not usually feasible.

   Instead, we prefer a probability distribution for $$X$$ that
   maximizes a quantity called "entropy". If the pmf $$p$$ for $$X$$
   assigns the number $$i$$ a probability $$p_i$$, $$i\ge 1$$, (namely
   $$\sum_{i\ge 1} p_i =1 $$), then the entropy of $$X$$ is

    $$ - \sum_{i\ge 1} p_i \ln p_i. $$

   The entropy quantifies the information we obtain by observing $$X$$.
   Imagine there is some pmf $$p$$ that maximizes the entropy of
   $$X$$.  Any other pmf provides less information when we observe
   $$X$$, which can be interpreted as follows: we get less information
   because of an implicit assumption we already made about $$X$$. So
   the "no further assumptions" model is the maximum entropy model.

   Now, given $$X$$ is a random variable taking values in
   $$\{1,2,3,\ldots\}$$, with $$\E X = \mu$$, find the maximum entropy
   probability model for $$X$$.  As you notice, the maximum entropy
   model is a geometric distribution.

3. Let $$N_1$$ be a Binomial $$n, p$$ random variable (the number of
   1s in $$n$$ independent Bernoulli $$p$$ trials). Let $$N_0 = n-N_1$$
   be the number of 0s in those trials, which is a Binomial $$n, 1-p$$
   random variable. Now since $$N_1+N_0=n$$, they are not independent.
   
   Now, let us take an alternate perspective. Let us imagine $$N$$ to
   be a Poisson random $$\lambda$$ variable. Conditioned on $$N$$, let
   $$N_1$$ be Binomial $$N$$, $$p$$ random variable, and let $$N_0= N-N_1$$. 
   
   1. Show that $$N_1$$ is a Poisson $$\lambda p$$ random variable.
   2. Show that $$N_0$$ is a Poisson $$\lambda (1-p)$$ random variable.
   3. Show that $$N_0$$ and $$N_1$$ are independent. 
   
   This is Problem 37 in Chapter 2 of the text (worked example) from a
   different perspective. This trick to "independentize" $$N_0$$ and
   $$N_1$$ is a useful and common technique in analyzing and
   simulating randomized algorithms.



    
