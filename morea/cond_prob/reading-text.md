---
title: "Guide for the Text"
published: true
morea_id: reading-text-cp
morea_summary: "Chapters 1.3 and 1.5"
morea_type: reading
morea_labels:
---

When you read the examples in the text, it will help to explicitly
write out events.  For example, in Example 1.6, can you write out the
events $$A$$ and $$B$$ explicitly?  Similarly in Examples 1.7. We will
do example 1.8 in class. In Example 1.9, can you write out the sample
space explicitly? In addition, here are some points to pay particular
attention to.

In Chapter 1.5 (Independence), you can skip Example 1.21 for now. It
is the only example that uses the law of total probability (in Chapter 1.4,
which will logically follow this module in our flow). You can also
skip the last subsection of Chapter 1.5 (Independent Trials and 
Binomial Probabilities) for the moment. You will get a chance to 
review both after the next module.

### Partial information and Conditional Probabilities
One thing to note is that we are making an association, implicitly,
between probabilities and _information_. This is not a heuristic
comment or a vague notion. It can be formalized quantitatively and
precisely. When we come to random variables, one of the experiences
will tell you about the quantification of "descriptions" into bits
vis-a-vis their probabilities.

For now, we will associate "describing an event $$A$$" with "assigning
event $$A$$ with probability $$P(A)$$". If you have partial
information from $$Z$$ (that $${\mathbb 1}_Z$$ is either True or
False), describing the event $$A$$ given $$Z$$ (or $$Z^c$$)
means we use conditional distributions, $$P(A|Z)$$ (or $$P(A|Z^c)$$).

As you may expect, if $$Z$$ provides information on $$A$$, intuitively
we should need fewer bits to describe $$A$$ if we already know $$Z$$
has happened.  This will turn out to be true. But it does not mean
that $$P(A|Z)$$ must necessarily increase (or necessarily
decrease). If $$P(A|Z)$$ is any number different from $$P(A)$$, we
will need fewer bits to describe $$A$$ given information on $$Z$$ than
to describe $$A$$ from scratch. Peek into the Information Theory
experience in the module on Random Variables if you want to understand
this.

The *multiplication rule* highlighted in the text is very important, and
it should make intuitive sense.  It says that you can describe a
sequence of properties by describing them one at a time.  Think of
$$A_1,\ldots, A_n$$ as the various properties an element of the sample
space has---to describe them, you first describe $$A_1$$. When you
next describe $$A_2$$, you don't have to start from scratch, you
already have partial information it has property $$A_1$$. So you
describe $$A_2$$ given $$A_1$$. And so on.

### $$P(A|Z)$$ and $$P(A|Z^c)$$

Since $$P(\Omega|Z) = 1$$, we have $$P(A|Z)+P(A^c|Z)=1.$$ But what about
$$P(A|Z)$$ and $$P(A|Z^c)$$? The partial information 
is different in the two notations---the first indicates that $$Z$$ has
happened, but the second indicates $$Z$$ has __not__ happened. In general
they don't add up to anything specific. 

However, the law of total probability (next module) does connect these
different descriptions.
