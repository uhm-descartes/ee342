---
title: "Measurable functions"
published: true
morea_id: experience-measurable
morea_type: experience
morea_summary: "Not all functions are random variables"
morea_start_date: "2023-09-16"
morea_labels:
---

Let $$(\Omega, {\mathcal F}, \prob)$$ be a probability space, with
$${\mathcal F}$$ being the set of all events possible. Recall that the
technical term for $${\mathcal F}$$ is a sigma-algebra, and it is a
set of subsets of $$\Omega$$ that includes $$\Omega$$, and is closed
under complementation and countable unions (and therefore also
countable intersections).

We defined a random variable as a function from $$\Omega\to{\mathbb R}$$.
Of course, this definition hides some nuances. Just like not all
subsets of $$\Omega$$ are allowed to be events if we are to keep the
axioms of probability, not all functions from $$\Omega\to{\mathbb R}$$ can
be random variables. 

### Borel Sigma-Algebra

Recall that $${\mathbb R}$$, the set of all real numbers is
uncountable. Therefore, if were to define a probability space on
$${\mathbb R}$$, not every subset of $${\mathbb R}$$ can be an event. So we
first specify which subsets of $${\mathbb R}$$ we really want to be
events---and those are intervals of form $$[a,b]$$, $$(a,b]$$,
$$[a,b)$$ and $$(a,b)$$ for all values of $$a$$ and $$b$$ ($$-\infty$$
and $$\infty$$ allowed).

Then we construct a set of all events that includes every interval
as above (ie, a set of subsets of $${\mathbb R}$$ closed under complementation,
countable unions and therefore countable intersections, and which includes
$${\mathbb R}$$). This is a sigma-algebra. It includes all the intervals, plus
all countable unions and intersections of the intervals. That isn't enough,
because sets such as the Cantor set are complements of countable unions,
but are themselves not a countable union of simple intervals. So we have
to include many further sets for technical reasons. The smallest collection
of subsets of $${\mathbb R}$$ that contains all intervals, and in addition,
is a sigma-algebra, is called the _Borel_ sigma algebra. We denote this
Borel sigma-algebra by $${\mathcal B}$$.

### Random Variables: Measurable Functions

For any set $$A\subset {\mathbb R}$$, let 

$$X^{-1}(A) = \{ \omega\in\Omega: X(\omega) \in A \}$$

be the set of all elements of $$\Omega$$ that are mapped into
$$A$$. The notation $$X^{-1}$$ is not an inverse function, and in no
way implies that the mapping $$X$$ is injective or surjective, it is
simply a mnemonic to remind ourselves that these are the elements of
$$\Omega$$ that map into $$A$$. In any case, $$X^{-1}(A)$$ is a subset
of $$\Omega$$.

We define a function $$X:\Omega\to {\mathbb R}$$ to be measurable if for
all $$B\in {\mathcal B}$, $$X^{-1}(B) \in {\mathcal F}$$. 

Essentially this means that any event in the Borel Sigma-algebra naturally
gets a probability under the mapping $$X$$, using the probability 
space $$(\Omega, {\mathcal F}, \prob)$$. To do so, for any event $$B\in {\mathcal B}$$, we
simply identify $$X^{-1}(B)$$ and because of measurability, we are assured
that $$X^{-1}(B)\in{\mathcal F}$$. Now $$\prob$$ has assigned every element in $${\mathcal F}$$
a probability, and therefore $$X^{-1}(B)$$ in particular, and that is the
probability we assign for $$X \in B$$. 

If $$X$$ is not measurable, it means there may be a set $$B\in {\mathcal B}$ such
that $$X^{-1}(B)\notin {\mathcal F}$$, and therefore cannot be assigned a probability.
This means that the regular things we do with manipulation of real numbers,
countable unions and complements will break. 

A random variable $$X$$ is a _measurable_ function $$X:\Omega\to{\mathbb R}$$. 

You may have wondered why we make up a new notation (random variable)
instead of just saying real-valued functions on $$\Omega$$. Now you
know. Not all real-valued functions on $$\Omega$$ are admissible as
random variables.

You may have guessed also that there is nothing sacrosanct about real
numbers.  Indeed, we can replace $${\mathbb R}$$ and the Borel
sigma-algebra $${\mathcal B}$$ by another set $$Z$$ and a sigma-algebra on
$$Z$$. You would then have a $$Z-$$measurable random variable. The
real values are chosen in an introductory course since they are
simple, ubiquitous, and very very useful.

