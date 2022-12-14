---
layout: default
title: November
nav_order: 3
---

# November

## October 31 to November 04

Goals of the week:

Goals
-Find reasonable ratios for eDAR
-Go back to MTE: what exactly needs to be done and how for the model?
-Finish Monte Carlo units
-Test the machine scientist on salinity temperature table
-Change PAR data
-Next round of edits of code
-Meeting with Toni

Reading
-Phages to sharks
-Journal club

Others
Email Savannah
reboot modeling club
Think about virision

## October 31

Now, I want to test the Machine Scientist on the Benson and Krause's paper.
How should I do this?
My goal is to find O2 concentration as a function of temperature and salinity. I have two variables. How many parameters? I don't know. I am going to look at my test on the Lotka-Volterra equations.
What I am seeing, is that I will need to reshape the dataset of the paper:
Column 1 - Temperature
Column 2 - Salinity
Column 3 - O2 concentration
y= Dataset[O2 concentration]
x= Dataset[temperature] and dataset[salinity]
I will do this with a single value of Salinity first. If I do that, my variable will be the temperature. Then I should try different numbers of parameters. And I should compare the results with the equation in the paper.
I prepared a csv for my first experiment.

## November 1

I want to continue with the machine scientist test. My first tests don't work. I don't know if I made a simple mistake or if the machine scientist simply does not have enough data to find equations. An
obvious solution would be to add a column to the salinity.
The machine scientist keeps returning an error and I don't understand why that happens.
I have three hypotheses of why this is not working:
Hypothesis 1:
There is a mistake in the code that I have not seen
Test:
Take the same code with a different dataset.
Compare this code to the most similar code that works.

Hypothesis 2:
There are too many few data points.
Test:
Check the paper to see the minimum number of data points.
Add a third value of salinity.

Meeting:
Rewrite already written introduction. Go to an introduction-results-method structure.
Use figures to help you write the paper.
Write methods also using the figures.

Paper for journal club
This paper studies the role of O2 flow in corals.
The cilia of corals helps them manage O2.
They use a combination of nanoparticles and imaging to look at O2 at the diffusive boundary layer of corals (a region sorruonding the coral).
They observe that the cilia of corals reallocate surplus of O2 to areas that have less chlorophyll. This minimizes oxidative stress. This is good for coral bleaching.

## November 2
I am going to start working with the machine scientist again.
Check minimum number of points. They say a minimum of 100 points. But it seems 400 is a better number.
Let's check again by adding another value for the salinity.
I still get the same error. Before trying to have more samples, I should test Hypothesis 1 (error in the code)

I don't see any difference in the code, so I am going to test on a dataset that I found. It seems there is a minor mistake on the code. Yes, I confirm the mistake.

Now the machine scientist is giving back a constant. I am assuming that a constant better explains the data. Is this a problem of scaling?
It might be. What about converting mg/l to micromol/dm3?

I am going to move to edit the draft of the transient dynamics paper. I should start talking about the results: go figure by figure? But first, look at other papers with that structure.
I drafted something, although I don't like it very much.

## November 4

Draft of the paper

Paragraph 1: describe Figure 1 a. Figure 1.a is a graphical representation of the model with the four terms. Following this idea, I think it is better to describe the model rather than the ecology. However, I should put the bacteria and the phage at the center of everything. I will avoid mentions to E coli and T4 because I want to keep my method more general than that.
I don't like the first iteration, too technical. I still don't like this and I always end in the same place.
Then I have to specify the type of bacteria and phage I consider.

How should I describe Figure 1 b?


## November 8
Draft of the paper. My goal is to:
1. Be more agnostic describing Figure 1b. Done.
2. Include the equations in my results and let help them explain the results.

I have a hard time explaining time aggregated per capita contributions. How do I explain the need for a reference timescale?
Now I have to make the point that these rates tell me that:
1. Sometimes they don't contribute to the dynamics.
2. They help me explain what is going on. How am I going to do this? Is it too much? I need to think about this in more detail.

Paper for Journal Club
They analyse the interplay of deoxygenation and global warming in coral reefs. They analyze coral reef benthic communities, they do microbial community sequencing and show a deoxygenation event altered the ecosystem.
There was a 50% coral loss and massive bleaching.
They observe that the benthic communities and microbial communities recovered on different timescales. This shows that deoxygenation is an important thing.

## November 9
No journal club today.
I am going to work on my GoldSim problems today. Last week I produced a model based on energy consumption.
This produced a very interesting curve, but the bacteria were not consuming O2 or sugar. I have to make them do that. How? I am going to take values from the metabolic model.
<<<<<<< HEAD

## November 10
I am going to start looking at the paper. My goals for today are linking Figure 1 to Figure 2

## November 14
Paper for journal club. My understanding is that the goal of the paper is to build an experimental system that simulates the future conditions of the Red Sea under different scenarios.
Six different temperatures and four ph scenarios. 80 experimental aquaria. Manipulation of light, nutrients. I am not sure about the results from the abstract.
It appears that they arrive to different conclusions as the hypothesis proposed by Forest (what I get is that temperature+CO2 have the most negative effect in coral mortality).

Consider a function called e-DAR that measures the ratio of e- donors and e- acceptors in any given ecosystem. Let the function be such that e-DAR=[e-donors]/[e-acceptors]+e, where e is a small number that prevents singularities, and [e-donor] and [e-acceptor] represent the concentration of electron donor and electron acceptors. In practice, these concentrations correspond to the concentration of labile DOC and O2. Then, the goldilocks line is the subset of values of e-donors and e-acceptors such that eDAR~1.

Limitations:
 1. how to count the concentration of (particularly) [e-donors], and [e-acceptors].

## November 16

Forest wants now to add Dissolved Organic Matter to the model. Every time a bacteria or phage dies, it fills the pool of DOC. The pool of DOC can be used for respiration and fermentation. It is not very different from glucose. In fact, in the last iteration, Forest wanted to connect the pool of glucose and DOC (I don't know if that is a good idea because they are not the same thing).
He was also interested in pH (he relates it to the concentration of CO2). He was arguing that pH is related to the energy of activation (and hence metabolism). But I do not understand how.

Now I am going to go for the introduction of Matt's paper. First I am going to read it. I think the message of the paper should be that we have a tool for predicting transient dynamics. So, how does the introduction help me conveying that message? That's how I should read, modify or combine the introductions.
The introduction has four paragraphs. The first paragraph is a perfect description of the problem: I will incorporate it to the text.
I am not sure about the second paragraph. In my version of the paper we argue something different.
I don't think the second and third paragraph fit in our narrative of what is going on and how we approach transient dynamics.

I finished a firt iteration of the introduction now.
=======


## November 10
I am going to start looking at the paper. For an hour. My goals for today are linking Figure 1 to Figure 2
I will make the substitution now. Likely, this will destroy the balance of O2+sugar to H20+C02.
The results do not make sense to me. The growth should mimic the energy consumption and this is not happening.
I think that GoldSim is reaching the largest numbers permissible.

## November 15
I am confused about what to do with the documentation. I do not want to start over, but I feel it is not informative the way it is written.


>>>>>>> 3a1ac258ef2fab03f2ada32ef7ffbc1fc5ca591a
