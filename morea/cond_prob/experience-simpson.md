---
title: "Simpson's Paradox"
published: true
morea_id: experience-simpson
morea_type: experience
morea_summary: "A famous lawsuit that never happened"
morea_start_date: "2023-09-04"
morea_labels:
---

## Simpson's Paradox

The official description of __Simpson's paradox__ is: "a phenomenon
where associations between variables in a population emerges,
disappears or reverses when the population is divided into
subpopulations."

It is best illustrated from a study of gender bias in grad school
admissions to UC Berkeley in 1970s. This is a famous story, and often
there is a claim of a lawsuit for gender discrimination. In reality,
there never was a lawsuit, but it is a striking example nonetheless.

#### UC Berkeley admissions data
Here is some data I dug up from Wikipedia:


| All applicants| Admitted | Male applicants| Admitted | Female applicants| Admitted |
|---|---|---|---|---|---|
| 12763 | 41% | 8442 | 44% | 4321 | 35% |


So here, it appears that women were admitted at a lower rate than male applicants. Yet, let us break down the data into individual departments. You can see the
full dataset [here](https://discovery.cs.illinois.edu/dataset/berkeley/), as well as a brief video describing the same. The following is a snapshot of three departments:

| Department | All apps | Admitted | Male apps | Admitted | Female apps | Admitted |
|---|---|---|---|---|----|----|
| A | 933 | 64% | 825 | 62%| 108 | 82%|
| B | 585 | 63% | 560 | 63%| 25 | 68%|
| C | 918 | 35% | 325 | 37%| 593| 34% |
| Total | 2436 | 53% | 1710 | 58% | 726 | 42 %|

When you see the total numbers, (58% acceptance for men, 42% for women), there
is a strong indication of gender discrimination against women. Yet, split into departments, there isn't such a damning story. In the full UC Berkeley database,
a similar story reveals itself. 

You can even recreate an example where every department treated women
applicants more favorably, but the overall totals indicate a higher
acceptance rate for men. Can you tweak the numbers in the table above to do so?

What is happening here is that the male applicants seem to be applying to departments with higher acceptance rates, while female applicants are applying to departments with lower acceptance rates. So even if each department seems to be treating the applicants equitably, it appears from aggregation that males are being
treated favorably. 

### Delta Variant Covid-19 cases in UK

In this [dataset](https://www.openintro.org/data/index.php?data=simpsons_paradox_covid), you have a comparison of death rates for 286,188 infected patients from UK. When you look at the overall death rates, vaccinated patients have
a higher death rate than unvaccinated death rates. But in each age category, vaccinated patients have a __lower__ death rate than unvaccinated patients. The reason for the paradox, of course, is that the vaccinated patients in this data set
come from a high risk, older age category, while the unvaccinated patients come from a lower risk, younger age category. 

### In philosophy

In fact, this phenomenon is not really uncommon. It just indicates
that a correlation may happen without a causal effect (or the
"obvious" causal effect). When you think about it, the bigger question
seems to be why we think this is a paradox or unintuitive. Here is a
more
[philosophical](https://plato.stanford.edu/entries/paradox-simpson/)
take on the Simpson's Paradox.
