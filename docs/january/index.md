---
layout: default
title: January
nav_order: 6
---

# January

## January 2 to 6

Goals of the week

-Finish GoldSim model
-Finish presentation
-Do bulk part of presentation for Jan 12

Reading
Origin of species
Smart brevity


## January 2
The next thing I want to do is to change concentrations of $$O_2$$ and/or glucose at day 0 (day +2)
There are several types of elements in GoldSim that appear to be helpful.
This is confusing to me: all I need is to change the concentration of $$O_2$$ or glucose at day 2.
Then, I guess I need some element that can do these two instructions. I found how to add 
concentration, but not the timed part.
The event delay is not helpful to me. I might need time series.
I got it now.
I have something that can be functional now. I would need to:
1. Rename this discrete addition.
2. Link it to $$O_2$$ or glucose.
3. Test it again.
4. Repeat until I have all the corresponding experiments implemented.

The sugar part is done. I am going to implement O2. However, I still don't know if these
are single interventions or continuous ones (i.e., add a constant supply of O2 during some time)
It appears now that it is not a single intervention but a rate; it is like having a hose turn on.
The metabolic part of the model looks very strange and redundant to me now. Is it correct?

There is no way we can cross the Goldilocks line with these concentrations. Here is the solution:
Forest was saying that I should start at the Goldilocks line (give it or take a factor 6 or 12). For
practical purposes, all I need to do is to fix one concentration and calculate the other one. Which
concentration is more reliable? O2 or sucrose?

I need to change single additions by constant flow of O2 and constant concentration of sucrose.
I need to recalculate eDAR for sucrose and set the concentrations at the Goldilocks line.
I need to have a glucose dependent Hill Function (you can grow without O2, but you cannot grow
without sugar). I need to know what a crazy sugar concentration is like to design the Hill function.

Now that I have a reliable O2 concentration I can calculate the sucrose concentration for the
Goldilocks line. I will have to decide what eDAR looks like.
I've been thinking that the sugar hill function should peak relatively fast and at relatively low sugar concentrations.
I do not need a modified Hill function for that, really...So I need to define the sugar concentration at which the 
Hill function is 0.5. I think first I should calculate the initial sugar (sucrose) so that I start off at the 
Goldilocks line.

Things I have to do:
1. Look for the concentration of fructose that produces a Goldilocks line at the beginning.
2. At that concentration of sugar, growth is not limited. Set K_DOC to half of that initial concentration.
3. Change events for constant supply of O2 and constant concentration of sucrose.
4. Link hill functions to growth rates.

## January 3
I have to start preparing the presentation for the meeting. And I have no idea how to do it. But
let's stick to the smart brevity thing.
Apparently, I should start with one sentence (the title) that perfectly summarizes my model or the results of my model.
I should be honest to myself: the model does not probably predict the data, but there are probably some results worth
discussing.
I should follow up with a sentence: that sentence should be very direct and short.
Then I explain why the results matter and finally I give the readers the option to go deeper.
How do I structure this into slides?

First slide: Title with muscular teaser.
Second slide: Sharp sentences (maybe add main result)
Third slide: Why it matters (maybe another figure)
Fourth and fifth slides: go deeper about what does the model do.

I go back to the model.
I should find the concentration of fructose that produces a Goldilocks line at the beginning. I did the following reasoning yesterday:
1. My machine only takes glucose and only does respiration with glucose. It does not make sense to implement a type of respiration for every type of sugar.
Therefore, I should assume that every molecule of DOC is, ultimately, glucose.
2. The DOC Andres and Lucas used was sucrose: sucrose is a molecule of glucose and a molecule of fructose bound to each other.
3. Let us assume that sucrose is just two molecules of glucose.
4. Then, when Lucas/Andres tell me a certain concentration of sucrose, I should treat that concentration as a concentration of pairs of glucose.
5. eDAR should be have a factor or 6 because I am explicitly assuming that only glucose and respiration are taking place in my system.
Assignment 1 is done.

Lucas says that the O2 experiment also works like a thermostat as well. That makes my life easier, actually.

For tomorrow:
1. Implement the Hill function for glucose
2. Link the product to growth rate
3. Do a thermostat for O2
4. Extract results and interpret them


Assignment number 2 is to define the Hill function for sugar. How should I define this? How am I supposed to be the most agnostic? I don't know, but I am going to assume that
growth is limited at only very small concentrations of sugar. I should do some experiments on the other laptop. So I am going to jump to Assignment 3 now. For the sucrose,
I just have to have a thermostat active from day 2.
Doing this is more complicated and different than what I expected. 
For starters, I need two status elements: one to switch on the thermostat and another one to control the thermostat.
My condition is inverse to that of the example. If sugar drops below the target value, I should add sugar until it goes over the target value.
I got it. Now I need to activate it over time.
I solved this but I don't know how to interpret the results now. Is this working properly?

## January 4
I think this model is ready and all I am going to do now is make up and documentation.
On the other hand, I will extract results and interpret them. I know this model is not working right, but I refuse to keep adjusting it before doing the presentation.
Before doing anything, I believe that my message should be this:
The model is accurate on the bacteria, but not on the phages. I am going to confirm this now.
Normoxic experiment - True, but less accurate on the bacteria. Same pattern on the phages.
Hyperoxic experiment - True and bacteria are very accurate. Addition: in my model, viruses drop. In the experiment viruses increase. Either more predation, higher burst size, or less lysogeny
No DOC experiment -
Low DOC experiment - Same
High DOC experiment - Same


## January 6
Boltzmann did not postulate the existence of atoms. I guess he proved they had to exist.
The question of statistical physics was that there was no way to explain the physics of a gas using newtonian mechanics. This would have
been a microscopic analysis of a gas. Instead, statistical physics offers a macroscopic explanation of its mechanics.