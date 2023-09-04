---
title: "Countability and Uncountability*"
published: true
morea_id: experience-counting
morea_type: experience
morea_summary: "Cantor's Diagonalization Argument"
morea_start_date: "2023-08-30"
morea_labels:
---

# Countability definitions

A bijective function $$f: A\to B$$ satisfies the property that for all
$$b\in B$$, there is exactly one $$a\in A$$ such that $$f(a) = b$$. So there
is a one-one correspondance between the elements of $$A$$ and $$B$$.
Clearly if there is a bijective function $$f$$ from $$A$$ to $$B$$, the
function has an inverse $$f^{-1}:B\to A$$ that is also a bijection.

By definition, the cardinality of $$A$$ and $$B$$ are equal if there is
a bijection from $$A$$ to $$B$$. This is how we compare infinite sets.

**Definition** All finite sets are countable. An infinite set $$A$$ is
_countable_ iff there is a bijection $$c:A\to {\mathbb N}$$, where
$${\mathbb N}=\sets{1,2, \ldots$$ is the set of all natural numbers.

Your handout gives many examples of countable sets. Informally this means
that given an infinite sheet of paper and infinite time, you could write all
elements of $$A$$ one below another (because you can write natural numbers one
below another as a list). 

[Cantor](en.wikipedia.org/wiki/Georg_Cantor) came up with a stunningly
beautiful argument to prove that the set $$[0,1]$$ is not countable.
While both $$[0,1]$$ and $${\mathbb N}$$ have an infinite number of
elements, the size of $$[0,1]$$ is a bigger infinity than the size of
$${\mathbb N}$$. 

This means that even given infinite time, you couldn't write out all
elements of $$[0,1]$$ one below another in that infinite sheet of
paper (in any order). This is not because there isn't a notion of "the
next real number after .1". In fact, you could write all rational
numbers one below another (though there is no "next rational number
after .1" either).

There are any number of articles on this on the Internet, here is a
short [video](https://www.youtube.com/watch?v=0HF39OWyl54) explaining
it. This argument is very fundamental---it is used to prove a lot of
other things, for example that the Halting Problem is undecidable (in
very imprecise terms, this means there are problems that the Turing
model of computation cannot solve). Who knows, you may get to use it
in grad school for your research too, as one of my students did to
show that some models cannot be infered well no matter how much
data you see.


