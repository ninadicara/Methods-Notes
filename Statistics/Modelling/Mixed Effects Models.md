

AKA hierarchical models, mixed effects models, multilevel models. 

## Intuition

[A Beginner's Introduction to Mixed Effects Models | Meghan Hall](https://meghan.rbind.io/blog/2022-06-28-a-beginner-s-guide-to-mixed-effects-models/)

Excellent resource for getting the right syntax in `lme4` 
https://bookdown.org/pingapang9/linear_models_bookdown/premidpost.html#linear-mixed-models-and-interaction-effects Chapter 12 and 13.

[Visualisation of how random intercepts and slopes work.](http://mfviz.com/hierarchical-models/) 

![](https://bookdown.org/steve_midway/DAR/images/07_models.png)


## Detailed explanations


This is an excellent guide for specifying models correctly and understanding random effects https://m-clark.github.io/mixed-models-with-R/

[Instructions from University of Bristol Multilevel Modelling Center](https://www.cmm.bris.ac.uk/lemma/index.php)

[[Mixed-Effects Models Standard Operating Procedure.pdf]]
## Implementation in R (`lmer`)


Step-by-step instructions in R with how to test assumptions https://ademos.people.uic.edu/Chapter18.html

The below is from a straightforward guide to implementation in R. 
[https://ademos.people.uic.edu/Chapter17.html]


When there is a 1 before the line, you are accounting for random intercepts (varying baseline levels) in your variable. A O indicates the variable has a fixed intercept and not a random one. These are a few hypothetical random effects structures:

- `(1| subject)` = Random intercepts and slopes for subjects (different baselines, different average effect per subject).
- `(1 + pizza |subject)` = The effect of pizza will vary _between_ subjects. Random intercepts for pizza consumption, random slopes for subjects influenced by pizza consumption.
- `(1 + pizza | subject) + (0 + time| subject)` = Subjects have random intercepts and slopes as influenced by pizza consumption. Time slopes can vary as function of the subject, but variance between pizza consumption and time as independent
- `(1 + pizza + time | subject)` = Same as above, but variance between pizza consumption and time are SHARED (pizza consumption has relationship with time that varies by subject).
- ``(1 + pizza * time | subject)` = Each subject can have their intercept, random slopes influenced by pizza and time, and their interaction between pizza and time. IMPORTANTLY, all random slopes and intercepts can be _correlated_.