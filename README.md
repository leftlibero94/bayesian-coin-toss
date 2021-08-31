# bayesian-coin-toss
Analytical and Monte-Carlo computation of the Bayesian probabilities of the outcomes of a randomly biased coin tossing game.

### An Analysis of Thomas Bayes' ball-rolling thought-experiment

The following thought experiment is adapted from Section II of Thomas Bayes' seminal 1763 paper, "An Essay towards solving a Problem in the Doctrine of Chances". I have used the modern treatment of the problem given by Prof. Sean R. Eddy in "What is Bayesian Statistics?", Nature Biotechnology volume 22, pages1177–1178(2004).

Alice and Bob are playing a game in which the first person to get 6 points wins. The way each point is decided is a little strange. The Casino has a pool table that Alice and Bob can’t see. Before the game begins, the Casino rolls an initial ball onto the table, which comes to rest at a completely random position, which the Casino marks. Then, each point is decided by the Casino rolling another ball onto the table randomly. If it comes to rest to the left of the initial mark, Alice wins the point; to the right of the mark, Bob wins the point. The Casino reveals nothing to Alice and Bob except who won each point.

Clearly, the probability that Alice wins a point is the fraction of the table to the left of the mark—call this probability p; and Bob’s probability of winning a point is 1 – p. Because the Casino rolled the initial ball to a random position, before any points were decided every value of p was equally probable. The mark is only set once per game, so p is the same for every point (in a particular game).

Say, after  8  rolls of any particular game, we end up with a situation  𝐴:𝐵=5:3 . Given this information, and only this information (we do not know  𝑝 ), what is the likelihood that Bob wins this game? Bayesian analysis tells us the probability is roughly  1/11 , whereas Alice winning has a probability  10/11  - the ratio of  𝐴:𝐵  probabilities is therefore  10 . We shall first verify this by actually running a large number of trials, discarding those that do not end up at  5:3  after  8  rolls, and of those that do, let us analyse how often Alice or Bob actually win. Then we shall implement a dynamic Bayesian paradigm where the odds update after every ball roll, and then figure out a general formula for a game stuck at Alice:Bob=x:y after x+y total rolls. We then write a program that implements this formula and plots out the dynamically changing odds against every turn. 

This formula and code can be easily modified for any two person zero-sum game of chance with imperfect information of bias, and possibly also to multi-player games. 
