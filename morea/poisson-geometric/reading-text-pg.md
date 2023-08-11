---
title: "Guide for the Text"
published: true
morea_id: reading-text-pg
morea_summary: "Chapters 2.2 and 2.4"
morea_type: reading
morea_labels:
---

This module covers the Geometric and Poisson distributions you find in Chapters 2.2 and 2.4. 

The geometric distribution was introduced as the number of trials
before the first success when you have independent Bernoulli
trials. The geometric distribution plays another important role in
modeling: it is the "maximum entropy" distribution among all
distributions over natural numbers with a given mean. While this
course is too premature to introduce the "maximum entropy" concept
formally, the intuitive meaning is that it is the distribution that
makes the least assumptions.

The Poisson was introduced as a limiting case of Binomial random
variables when the number of trials goes to infinity, but the success
paramater diminishes to zero in just the right way. Needless to say,
the Poisson model is also extremely important in modeling, It shows up
in another way when analyzing and simulating randomized algorithms, by
means of what is known as the Poissonization approach. 

When you take $$n$$ independent Bernoulli trials and record the number
of ones (say $$N_1$$) and zeros (say $$N_0$$), the random variables
$$N_1$$ and $$N_0$$ are not independent (clearly, since
$$N_1=n-N_0$$). But suppose you took a different perspective on this,
and treated $$n$$ not as a fixed number by a random variable
itself. So you would first choose a value for $$N$$ according to the
probability model, and then do $$N$$ independent Bernoulli trials and
record the number of 1s and 0s in $$N_1$$ and $$N_0$$ respectively. So
conditioned on $$N$$, $$N_1$$ and $$N_0$$ are not independent for the
same reason as above. But if $$N$$ is chosen to be Poisson, then $$N_0$$
and $$N_1$$ turn out to be _independent_ Poisson random variables as
well!  We will look at this in one of the Problems in class.


