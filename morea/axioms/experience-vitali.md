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

Consider the uniform pdf over $$[0,1]$$ we covered in this module. Under
this pdf, the probability of an interval is its length, and we generalize the
usage of length to mean the probability assigned to this set. We will construct
a subset of $$[0,1]$$ that CANNOT have a length (not even length 0). Assigning
any number to its length just breaks the notion of length/probability altogether!

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

$$H_a = \sets{ x: x\in [0,] \textrm{ and } a \sim x }.$$

If you think about it, if $$a \sim b$$, then $$H_a = H_b$$ (prove
using the three properties). If $$a\not\sim b$$, then $$H_a \cap H_b =
{}$$ (the third property gives this insight). So all related numbers
live in their own family. Any two distinct families are
disjoint. Every number is in some family. So $$[0,1]$$ is broken down
into disjoint families based on the relation $$\sim$$. Now that you
know a little about countability, the number of families here is
uncountably infinite. The size of each family is exactly the size of
rational numbers: any family can be thought of as the set of rational
numbers shifted by an offset unique to that family.

When we have an uncountably infinite number of sets, it is not clear
how to define their Cartesian product (tuples don't work, since the
index is not countable). But regardless, we use something called the
axiom of choice, that assures us that in _any_ collection of sets, we
can pick one element from each set. Let us go ahead and choose
one representative of each family, call it $$H$$. 

For any number $$z\in [0,1]$$, let $$z+r \mod 1$$ represent the number
obtained by shifting $$z$$ to the right by $$r$$ (and subtracting 1
if $$z+r > 1$$. Now let $$H\oplus r$$ be the set

$$ H\oplus r =\sets{ z+r \mod 1 : z \in H }. $$

Now note that $$H\oplus r$$ contains one member of each family, but
different from the family member in $$H$$ (by an amount equal to a
right shift by $$r$$, subtracting 1 if needed). But since very family
can be thought of as an offset version of the set of rational numbers,

$$[0,1] = \bigcup_{r \textrm{ rational}} H \oplus r.$$

Because we are looking at a uniform probability law, $$P(H) = P(H\oplus r)$$ for any $$r$$, and because $$H\oplus r$$ is disjoint for distinct $$r$$, we have

$$1= P([0,1]) = \sum_{r \textrm{ rational}} P(H \oplus r) = \sum_{r \textrm{ rational}} P(H) $$

Now we have a problem. The left side is 1. The right side is 0 if $$P(H)=0$$,
and $$\infty$$ if $$P(H)$$ is any number $$>0$$. It can never equal the left
side no matter what we do. $$H$$ therefore simply cannot be measured, it breaks
the axioms of length/probability if we assign it anything!


