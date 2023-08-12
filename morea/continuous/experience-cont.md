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
   random variable. 
   
    * Show that for any $$r, s \ge 0$$,

	$${\mathbb P}( X > r+s | X> r) = {\mathbb P}(X> s).$$
	
	Life of electronic components without moving parts are often
    modeled as exponential random variables. This means that if a
    component is already $$r$$ years old, the probability it will last
    for $$s$$ more years is equal to the probability a new identical
    component will last for $$s$$ years. Meaning there is no point
    buying a new one, you should wait till failure to replace it and
	use a different way to manage failures when they happen.
	
	* Write the analog of the memoryless property for discrete random
	variables taking values in $$\{1,2,\ldots\}$$, and show that the
	geometric random variable also has the memoryless property.
	
	 **Radioactive Decay** It can be proved (those who are interested
	 can try your hand at it, or see me for a proof) that the
	 exponential random variable is the _only_ continuous random
	 variable defined on $$[0,\infty)$$ that can have the memoryless
	 property. This has a very important consequence in physics, one
	 that you have already studied.
	 
	 Radioactivity is a probabilistic, quantum mechanical phenomenon,
	 wherein certain atoms, like C-14, rearrange themselves
	 spontaneously to a lower energy configuration. One may posit such
	 a memoryless property for radioactive decay: a C-14 atom at time
	 0, regardless of past, will rearrange itself to N-14 at a time
	 $$t$$ in the future with some probability. The assumption here is
	 not on the probability, only that the probability is independent
	 of the past from time 0. This is enough to ensure that the time
	 to decay is modeled by an exponential random variable, and all
	 one has to do then is to find the exponential parameter by
	 observing the half life of C-14! Of course, this has been verified in 
	 practice to fantastic precision, and the harbinger of the atomic
	 age. 
 
	 

	
2. Let $$R_1, \ldots R_k$$ be $$k$$ independent exponentially
   distributed random variables with parameters $$\lambda_1,\ldots,
   \lambda_k$$. Show that

	$$R = \min_{1\le i \le k} R_i$$
	
	is also an exponentially distributed random variable. What is its
    parameter?
	
3. **Poisson and Exponentials** Let $$X_1, X_2, \ldots$$ be iid
   exponential random variables with parameter $$\lambda$$. Think of a
   packet queue at an Internet hub, and suppose $$X_i$$ is the time
   gap (in seconds) between the $$i-1$$th and $$i$$'th packet. Show
   that the number of packets that arrive in $$t$$ seconds is Poisson
   distributed with parameter $$\lambda t$$. Therefore, when you model
   interarrival times as exponential, the number of arrivals in any
   time interval is Poisson.
   

