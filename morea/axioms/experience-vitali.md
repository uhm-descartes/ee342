---
title: "Sets of real numbers with no length"
published: true
morea_id: experience-vitali
morea_type: experience
morea_summary: "Does NOT mean zero length"
morea_start_date: "2023-08-28"
morea_labels:
---

# Non-measurable sets

One of the points I have mentioned is that when $$\Omega$$ is uncountable,
we exclude subsets of $$\Omega$$ before assigning probabilities. It is not
that they have zero probability, but they cannot participate at all!

Consider the uniform pdf over $$[0,1]$$ we covered in this
module. Under this pdf, the probability of an interval is its
length. We generalize the observation and say that the length of any
subset of $$[0,1]$$ is the probability assigned to this set under the
uniform pdf. We will construct a subset of $$[0,1]$$ that CANNOT have
a length/probability (not even length 0). Assigning _any_ value to its
length/probability simply breaks the notion of length/probability
altogether.

First, you need to know that the set of rational numbers is
countable. We define the following relation $$a\sim b$$ to mean
$$|a-b|$$ is rational. Such a relation satisfies

* For all $$a\in[0,1]$$, $$a\sim a$$
* If $$a\sim b$$, then $$b\sim a$$
* If $$a\sim b$$ and $$b\sim c$$, then $$a \sim c$$

Generally, relations that satisfy the above are called _equivalence_
relations.  One interesting property of equivalence relations in
general, and $$\sim$$ in particular, is that it can partition (break
into disjoint sets) $$[0,1]$$ based on the relation. To make this
clear, for any $$a \in [0,1]$$, let the family of $$a$$ be defined as

$$H_a = \{ x: x\in [0,1] \textrm{ and } a \sim x \}.$$

If you think about it, if $$a \sim b$$, then $$H_a = H_b$$ (prove
using the three properties). If $$a\not\sim b$$, then $$H_a \cap H_b =
\{\}$$ (the third property gives this insight). So all related numbers
live in their own family. Any two distinct families are
disjoint. Every number is in some family. So $$[0,1]$$ is broken down
into disjoint families based on the relation $$\sim$$. Now that you
know a little about countability, the number of families here is
uncountably infinite. 

These families have another structure we exploit: given any one member
$$z$$ of a family, you can get all the others by adding every rational
number between 0 and 1 to it, with the caveat that if for some
rational number $$0r$$, $$z+r>1$$, then you interpret the
result as $$z+r-1$$.  As a shorthand for this operation, we define for
$$z, r \in [0,1]$$, 

$$ z + r \mod 1 \stackrel{\textrm{def}}{=} \begin{cases} z+r & \textrm{
if } z+r \le 1\\ z+r-1 & \textrm{ if } z+r > 1.  \end{cases}$$ 

With this observation, notice that the size of each family is simply
the size of the set of rational numbers (which, as we have seen, is
countable, and hence has a bijection with natural numbers $$\mathbb
N$$). So every family can be thought of as an offset version of the
set of rational numbers.

When we have an uncountably infinite number of non-empty sets, it is
not clear how to define their Cartesian product (tuples don't work,
since the index is not countable). Whether we can have have something
like a Cartesian product is a matter of much debate, but in the ZFC
version of set theory axioms (remember [Logicomix](https://uhm-descartes.github.io/ee342/morea/sets-logic-func/experience-slf.html) from the previous [module](https://uhm-descartes.github.io/ee342/modules/module-slf/)?) we use (without knowing the name), we
adopt an axiom that such a Cartesian product is possible. This
is called the "Axiom of Choice", that assures us that in _any_
collection of non-empty sets, we can pick one element from each set.

Let us go ahead and choose one representative of each family we formed
using the relation $$\sim$$, and call it $$H$$. For $$r\in[0,1]$$ let
$$H\oplus r$$ be the set

$$ H\oplus r =\{ z+r \mod 1 : z \in H \}. $$

Now note that for rational $$r\in (0,1]$$, $$H\oplus r$$ also contains
one member of each family, but different from the family member in
$$H$$ (by an amount equal to a right shift by $$r$$, subtracting 1 if
needed). But since very family can be thought of as an offset version
of the set of rational numbers,

$$[0,1] = \bigcup_{\substack{r \in [0,1]\\r \textrm{ rational}}} H \oplus r.$$

Now, the set of rational numbers has a bijection with the set of
natural nubmers, so the above equation is a way to write $$[0,1]$$ as
a countable, disjoint union. Probability axiom 2 therefore applies.

In the uniform probability law, $$P(H) =
P(H\oplus r)$$ for any $$r$$ because the two sets are just shifts of
each other. Using Probability Axiom 2, we have

$$1= P([0,1]) = \sum_{\substack{r \in [0,1]\\r \textrm{ rational}}} P(H \oplus r) = \sum_{\substack{r\in[0,1]\\r \textrm{ rational}}} P(H). \qquad\qquad\qquad\qquad\qquad(1)$$

We are allowed to write sum over rational numbers since there is a one
to one correspondance between rationals and natural numbers (so the
sum over rationals is really like $$\sum_{i\ge 1}$$, except the indices
are called by different names).

Now we have a problem with Equation (1). The left side of the equation
is 1. The right side is 0 if $$P(H)=0$$, and $$\infty$$ if $$P(H)$$ is
any number $$>0$$. It can never equal the left side no matter what we
do. 

$$H$$ therefore simply cannot be measured, it breaks the axioms of
length/probability if we assign it anything at all! Now you know what I mean
when I said we cannot assign probabilities or lengths to sets like $$H$$---they
are so weird that if you do so, you break the axioms of probabilities/lengths.
The crucial role played by the Axiom of Choice cannot be taken away, in fact,
it is known that the Axiom of Choice is equivalent to the existence of such
weird sets. 

