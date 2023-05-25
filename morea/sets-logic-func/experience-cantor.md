---
title: "Cantor Set"
published: true
morea_id: experience-cantor
morea_type: experience
morea_summary: "Bizzare sets"
morea_start_date: "2023-07-15T23:00"
morea_labels:
---

# Cantor Set

The logo you see for this module is a representation of the Cantor
set. This is the way you construct the Cantor set: 

Start from the closed interval [0,1]. (A closed interval includes both end points)

1. Remove the open middle third (ie the interval $$(\frac13, \frac23)$$. What remains are two closed intervals, $$[0,\frac13]$$ and $$[\frac23, 1]$$. (An open interval excludes both the end points). We removed 1/3 of the interval,
	(so 2/3 remains). Carry over these 2 intervals to next step.
2. From steps 2 onwards:
   * Step i: There will be $$2^{i-1}$$ closed intervals carried over
     from the prior step, each with size $$\frac1{3^{i-1}}$$. Remove the
     middle open one third of each of the $$2^{i-1}$$ closed
     intervals. As a result, we are left with $$2^i$$ closed
     intervals, each with size $$\frac1{3^i}$$. The length removed equals
	 $$2^{i-1}/3^i$$. Carry these to the next
     step. The total length carried over is $$\frac{2^i}{3^i}$$.
  
The Cantor set $$\cal C$$ is what remains after you do this procedure for all
natural numbers $$i\ge 1$$. 

How do you know any element remains? Here is a way to get a handle on
what is happening. In the first step, let us represent every number in
the closed interval [0,1] with its ternary expansion. The ternary (or
binary or decimal) expansions are generally not unique---for example,
$$1/3 = .1_3 = .022222..._3$$ (all numbers of form $$m/3^n$$ have two
representations as above), and $$2/3 = .2_3 = .122222..._3$$). This is
true for decimals too, since $$.1_{10} = .099999..._{10}$$, and so
on. Choose .02222... for 1/3 and .2 for 2/3. Now note that every
number in the open middle one third reads $$.1xxx_3$$ (in _all_ its
representations).  So the open middle one third must use a 1 in the
first position of its ternary representation. Similarly, after the 
second step, every number removed must have a 1 in its second position
after the point. And so on. 

The numbers that remain are therefore all the numbers that can be
represented without using a 1 in some representation (so 1/3, 2/3 both
survive). These numbers form the Cantor set. In the $$i'$$th step, the
total length of intervals carried over to the next step is
$$\frac{2^i}{3^i}$$, so after the construction proceeds for all $$i$$,
the total length that remains must be 0. Calculating another way, the
total length removed in step $i$ is $$\frac{2^{i-1}}{3^i}=\frac12
\frac{2^i}{3^i}.$$ Summing over all $$i\ge 1$$, the total length
removed is 

$$ \frac12 \Bigl(\frac 23 + (\frac 23)^2 + \cdots \Bigr) =
\frac12 \frac{\frac 23}{1-\frac 23} =1,$$

which means the Cantor set $$\cal C$$ has length 0.

But here is where things get really bizzare. We can easily prove that
the Cantor set has the same size as [0,1]. It is easy in fact---we say
$$\cal C$$ has at least the size of $$[0,1]$$ if there is a surjective
(onto) function $$m:{\cal C}\to [0,1]$$. Namely, every element $$y \in
[0,1]$$ is the map of some element $$x\in{\cal C}$$ ($$y = m(x)$$),
though multiple elements in $$\cal C$$ could map to the same $$y\in
[0,1]$$. There is an obvious map: since the ternary expansion of 
any $$x\in{\cal C}$$ can be written only in terms of 0s and 2s, let
us replace every occurance of 2 with a 1. For example if 

$$ x = .02220202 $$

then we obtain the sequence 

$$ s = .01110101 $$

$$m(x)$$ is the number in $$[0,1]$$ whose _binary_ expansion is $$s$$,
which we will call as $$y$$. Now every number in $$[0,1]$$ has a
binary expansion of course, so some element of $$x$$ must map to it
(potentially more than one if it has multiple
representations). Therefore the size of $$\cal C$$ is at least as
large as the size of $$[0,1]$$. But $$\cal C \subset [0,1]$$, so the
size of $$[0,1]$$ is at least as large as the size of $$\cal C$$. So
the two sizes must be the same and is called the cardinality of an
uncountable set (which is a bigger infinity than the size of an
infinite set such as the set of all natural numbers).








