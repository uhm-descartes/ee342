---
title: "Problems in class"
published: true
morea_id: assessment-bayes
morea_summary: "Bayes' Theorem"
morea_outcomes_assessed:
 # - outcome-CHANGE-ME
morea_type: assessment
morea_start_date: "2023-09-11"
morea_labels:
---
These problems are a Bayesian reformulation of problems from last 

1. **Coin Tosses** Recall the coin toss problem (Problem 1 from the previous module). In the previous module, we considered two coins:
    * Fair coin: The coin tosses are fair and every sequence of coin
       tosses has equal probability. What is the probability the
	   first coin is heads given the second and third coins have the
	   same face (ie. the event that they are both heads or both tails)?
	   
	* Biased coin: The coin tosses are rigged. The person tossing
       the coin ensures that you only see an even number of Heads, but
       makes sure that all sequences with an even number of Heads have
       equal probabilities (whether 0 or 2 Heads among 3 coin
       tosses). What is the probability the
	   first coin is heads given the second and third coins have the
	   same face (ie. the event that they are both heads or both tails)?  

   Now let us estimate the following probabilities. In the problems below,
   assume that the Fair coin is chosen with probability $$p$$ and the Biased
   coin is chosen with probability $$1-p$$. 
      * What is the probability distribution on the three coin tosses (ie, 
	  you need to compute probabilities of all outcomes, HHH, HHT, etc.)
	  * In the prior problem, you noted that any two coin tosses are independent. Is that still true?
	  * Are all three coin tosses independent?
	  * Given that you saw 2 heads, what is the probability you are seeing coin
	  tosses from the Fair coin? 
	  * Given that you saw 2 heads, what is the probability the next coin toss
	  is also heads?

2. **Communication over noisy channels** Recall the Binary Symmetric Channel from the previous module. As
    before, there is a transmitter and a receiver, and the transmitter
    transmits one bit through a channel. The transmitter chooses 0 or
    1, but unlike the previous module, now the probability of a 1 is
    $$p$$, this is the _prior_ probability. Now the link is not
    perfect. Given any input, the channel flips the input bit with
    probability $$\epsilon$$.
		
	  * What is the probability the received bit is 1?

	  * Given the received bit is 1, what is the probability that the transmitted bit is 1? This is the _posterior_ probability.

3. **Stochastic Block Model** This is an elaborate description of graphs,
     the Erdos-Renyi random graph model and the Stochastic Block model,
	 primarily for the reference of those who have not seen anything about
	 graphs at all. A graph is a collection of _vertices_ $$V$$,
     and a set $$E \subset V\times V$$ of _edges_. Every element of
     $$E$$ is an ordered pair $$(v_1, v_2)$$, where $$v_1$$ and
     $$v_2$$ are vertices. One can interpret this ordered pair as
     either a line going from $$v_1$$ to $$v_2$$ (denoted by an arrow,
     and called a directed edge) or a line connecting $$v_1$$ and
     $$v_2$$ (called an undirected edge). Our notation for the graph
     will be $$G=(V,E)$$, where $$V$$ is the vertex set, and $$E$$ the
     set of edges as described above. In this series of problems, we
     will only consider undirected edges. Graphs that have a random
     element to their construction are called _random graphs_, and are
     used extensively to model interactions between entities in a wide
     variety of areas, including social networks, economics,
     statistical mechanics, and biological mechanisms.
    
	 We will look at a particular kind of random graph generation
	 called the Erdos-Renyi model. In this model, the vertex set $$V$$
	 is fixed (and not random), and we also need a fixed number $$0\le
	 p\le 1$$. Suppose the vertex set has size $$n$$. For each of the
	 $${n\choose 2}$$ pairs of distinct vertices, the Erdos-Renyi
	 model tosses a coin (independent of all others) with probability
	 of heads $$p$$, and if heads, adds that corresponding edge to the
	 graph. Different coin toss outcomes therefore produce different
	 graphs, hence the actual graph that is generated is a random
	 quantity. All coin tosses, again, are assumed independent. A random
	 graph generated with this Erdos Renyi model on a vertex set of
	 size $$n$$ and parameter $$p$$ is denoted $$G(n,p)$$.

	 A Stochastic Block Model is a clustering model. Here we assume
	 that there are two clusters of related entities (for example,
	 senators of the same party, genomes of related species, etc.).
	 Each entity is represented by a node. The entities are related,
	 but not identical. We make an observation (say we sequence a part
	 of the genome of all bacteria in a patient's gut). Related
	 entities may behave similarly, but every pair of related entities
	 will not necessarily behave identically. So for example, portions
	 of the sequenced genome for different bacteria of the same
	 species may have some degree of similarity, but they will not be
	 identical. Unrelated entities may also show some similarity, but
	 to a lesser degree---namely, different species bacteria may show
	 some similarity in the portion of the genome sequenced (not too
	 surprising, humans share 90+% of the genome with chimps). Now
	 given the observation, can we infer which nodes belong to which
	 clusters? Which bacteria form different species in our observation?
	 
	 To model this, suppose there are $$2n$$ vertices, two clusters,
     with $$n$$ vertices in each cluster. Which nodes belong to which
     clusters is unknown to us, and must be infered from an
     experiment. Say we perform an experiment, and draw edges between
     nodes where the experiment indicates similarity (perhaps
     similarity greater than a threshold in our genome inference
     example). How do we infer cluster membership? 
	 
	 A common modeling approach is probabilistic, where we assume each
     cluster is a random realization of an Erdos-Renyi $$G(n,p)$$
     graph. Just like the Erdos-Renyi setup, we now place edges
     between two vertices in different clusters using independent coin
     flips, this time with bias $$q < p$$. Thus we expect vertices in
     the same cluster to be more tightly connected than with vertices
     in other clusters. The "random" edges placed is a probabilistic
     modeling technique to account for the fact that experiments do
     not always reveal similarity or dissimilarity with
     certainity. This model is the Stochastic Block Model. We will use
     this in later modules as well, but two preliminary questions for
     now:
	 
	 * Given two randomly chosen vertices $$v$$ and $$w$$ among the $$2n$$ vertices, what is	the probability that there is an edge between them?
	 
	 * Given that two vertices $$v$$ and $$w$$ have an edge between them, what is the probability they belong to the same cluster?
	 
3. **Classification** We considered a classification problem in the
    prior module.  where a threshold (a fixed but unknown number
    $$T$$) splits the line into two (infinite length) intervals, the
    left side of $$T$$ carrying label -1 and the right side carrying
    label +1. The threshold $$T$$ is unknown and the learning
    algorithm is supposed to figure this out.
	
	Training points are generated by a pdf $$f$$, which was left
	unspecified last module, but which we will now specify. To
	generate a training point from $$f$$, first toss a biased coin
	whose two sides are $$-1$$ and $$+1$$, and whose probability of landing
	on $$+1$$ is $$p$$. If the outcome of the coin toss is $$-1$$,
	we choose a number from $$T-1$$ to $$T$$, using a uniform pdf. If
	the coin toss is $$+1$$, we choose a number from $$T$$ to $$T+1$$,
	using a uniform pdf.
	
	Our learning algorithm sees a training point $$x$$ and its label.
	If the label of the training point $$x$$ is -1, the algorithm
	outputs as its estimate of the threshold to be $$x+1-p$$, If the
	label of the training point $$x$$ is +1, the algorithm outputs
	$$x-p$$. The idea is that since the learning algorithm does not
	know $$T$$, it uses its estimate of the threshold to classify
	points instead.
	
	  * What is the generalization error (the probability another
      point generated from $$f$$ is misclassified by the threshold
      estimated by the learning algorithm) if the label of the
      training point was $$-1$$? What if the label was $$+1$$?
	  
	  * What is the generalization error? The distinction between this
	  and the prior quesiton motivates the topics in the next module.
