If a certain effect of interest exists (e.g. a difference between two groups) power is the _chance that we actually find the effect_ in a given study.

Power is the probability of detecting an effect if there is a true effect present to detect. 
It helps to determine the smallest sample size that is suitable to detect an effect of a given test at the desired level of significance.

- Purpose is to protect against Type II [[Error]]s. 


To calculate power we need:
- **Alternative hypothesis** (i.e. effect size of interest) 
- **Alpha**-level (i.e p value threshold) - usually = 0.05 or 0.001 (Level for avoiding Type I [[Error]])
- Desired **power** level - usually around 80% (Level for avoiding Type II [[Error]])

>[!Example] Example: In a coin toss simulation, we want to detect if a coin is unfair. 
> - Alternative hypothesis: Lets set unfair as anything more than 55% heads - this is a deviation of 5% from our hypothesis (that the coin is 50/50).
> - Alpha: We only want to be wrong 1 in 1000 times so our alpha threshold is 0.001. 
> - Power: We only want to have a 10% chance of not detecting an effect if it was there. 100 minus 10 is 90 and so 90% is our desired power. 
> 
>In summary then, our job is to figure out **at which number of observations** (i.e. sample size) we can be 90% sure to detect the unfairness of 55% with only a 0.1% chance of getting our decision wrong.


This paper is a really good introduction to power and sample size calculations. 

## Observational data

There is some discussion about whether you should ever do ad-hoc power analysis - that is, power analysis after the data has been collected/experiement done. 

When I asked Edwin Dalmajer about this he said: 
	Given that you're dealing with secondary data, wouldn't it make more sense to do a sensitivity analysis? I.e. define the minimum effect size that one could possibly detect given the number of participants in ALSPAC.
	ALSPAC is already collected, so our maximum sample size is the number of relevant datasets in there. (You could even cheekily count the number of complete cases for your variables...) Let's call this maximum number of observations _N_.
	Next, let's define a minimum effect size of interest. For example, you could say that X points on the wellbeing measure that you are using as an outcome is a meaningful reduction, but anything below that wouldn't be. (This could be determined using e.g. the reliability of the measurement, and/or an understanding of what each of the questions on a questionnaire actually are, etc.) Let's call this minimum effect size of interest _d_.
	This brings us to the simulations: it's a bit of a minefield because we'd have to make a few assumptions about the data. (E.g. covariance between all measured variables... eek!) However, because we've already set N and d, the number of possible simulations is much more limited. In essence, we would simulate several conditions (from no to super high covariance) and count the proportion of simulations with N participants that show an effect size of d or over. This is our power, and thus this approach allows us to map what the relationship between assumptions and power is.
	You can then either show the full mapping of power to assumptions, or simply choose what the "most likely" assumptions are and show the associated power range.

---
[PANGEA: Power Analysis for General ANOVA Designs](https://jakewestfall.shinyapps.io/pangea/)

[Power Analysis by Simulation in R](https://julianquandt.com/post/power-analysis-by-data-simulation-in-r-part-i/)

[Jones, S., S. Carley, and M. Harrison. "An introduction to power and sample size estimation." _Emergency medicine journal: EMJ_ 20.5 (2003): 453.](https://emj.bmj.com/content/emermed/20/5/453.full.pdf)