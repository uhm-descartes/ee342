---
title: "Problems in Class"
published: true
morea_id: experience-cont-prob
morea_type: experience
morea_summary: "Continuous RV: exponentials"
morea_start_date: "2023-10-31"
morea_labels:
---

# Problems in Class

1. **Memoryless Property** Let $$X$$ be an exponentially distributed
   random variable. Show that for any $$r, s \ge 0$$,

	$${\mathbb P}( X > r+s | X> r) = {\mathbb P}(X> s).$$
	
	Life of electronic components without moving parts are often
    modeled as exponential random variables. This means that if a
    component is already $$r$$ years old, the probability it will last
    for $$s$$ more years is equal to the probability a new identical
    component will last for $$s$$ years. Meaning there is no point
    buying a new one, you should wait till failure to replace it and
	use a different way to manage failures when they happen.
	
2. Let $$R_1, \ldots R_k$$ be $$k$$ independent exponentially
   distributed random variables with parameters $$\lambda_1\upto
   \lambda_k$$. Show that

	$$R = \min_{1\le i \le k} R_i$$
	
	is also an exponentially distributed random variable. What is its
    parameter?
	
3. **Poisson and Exponentials** Let $$X_1, X_2, \ldots$$ be iid
   exponential random variables with parameter $$\lambda$$. Think of a
   packet queue at an Internet hub, and suppose $$X_i$$ is the time
   gap (in seconds) between the $$i-1$$th and $$i$$'th packet. Show
   that the number of packets that arrive in $t$ seconds is Poisson
   distributed with parameter $$\lambda t$$. Therefore, when you model
   interarrival times as exponential, the number of arrivals in any
   time interval is Poisson.
   

