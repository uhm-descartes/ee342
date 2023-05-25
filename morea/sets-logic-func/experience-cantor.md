---
title: "Logicomix"
published: true
morea_id: experience-cantor
morea_type: experience
morea_summary: "A graphic novel"
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
     from the prior step, each with size $\frac1{3^{i-1}}$. Remove the
     middle open one third of each of the $$2^{i-1}$$ closed
     intervals. As a result, we are left with $$2^i$$ closed
     intervals, each with size $\frac1{3^i}$. The length removed equals
	 $$2^{i-1}/3^i$$. Carry these to the next
     step. The length of intervals removed
  
The Cantor set is what remains after you do this procedure for all
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
survive). These numbers form the Cantor set. There are a uncountably
infinite number of such numbers (so the Cantor set has the same size
as [0,1]). What is even more amazing is the "length" of the Cantor set.
The total length removed in step $i$ is $$\frac{2^{i-1}}{3^i}=\frac12 \frac{2^i}{3^i}.$$ Summing over all $$i\ge 1$$, the total length removed is

$$ \frac12 (\frac 23 + (\frac 23)^2 + \cdots ) = \frac12 \frac{\frac 23}{1-\frac 23} =1,$$

which means the Cantor set has length 0 (despite its size being as large as
the interval from [0,1])!!! Fun stuff. 








