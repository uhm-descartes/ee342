---
title: "Quicksort"
published: true
morea_id: experience-axioms-prob-quicksort
morea_type: experience
morea_summary: "Problems in class"
morea_start_date: "2023-09-01"
morea_labels:
---

_QuickSort_ is a recursive, divide-and-conquer algorithm to sort a
  sequence. We will assume here that no two numbers in the sequence
  are equal. Many of you may have seen this algorithm before. Each
  call to QuickSort works as follows: given $$n$$ numbers to sort (in
  ascending order, say),

1. pick a _pivot_ at random from one of the $$n$$ elements.

2. all numbers $$<$$ the pivot are placed in the left bin, and
       all numbers $$>$$ than the pivot are placed in the right bin
       (so we do $$n$$ comparisons to partition the numbers into left
       and right bins). The two bins may end up being unequal in size.

Then Quicksort is called on each bin separately till we end up with
bins of size 1.  We also know the relative order of each bin (numbers
in left bin are all less than the pivot, which in turn is less than
the numbers in right bin at any step). When each bin has a single
element, writing out all the elements in the order of bins gives the
sorted sequence. 

Quicksort is an example of a randomized algorithm. Note that different
sequences and different choices of pivots lead to different number of
comparisons. Set up a probability space to model one step of Quicksort
for a random permutation of a sequence of 4 distinct numbers. (You can
assume without loss of generality that the input is a permutation of 1
through 4, do you see why?)

