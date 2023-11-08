
## Between subjects ANOVA

Difference between two or more independent groups. 

>[!example] 
>Whether _boys_ or _girls_ have better grades (continuous) in school. Here gender is the independent variable.

More flexible than independent samples _t_ tests because they allow for multiple independent variables with two or more levels each. 

NOTE: This looks a _lot_ like the linear regression equation...

`Y = b0 + b1X + e`

Where gender is X and grade is Y. 
If b1 is significant then gender is related to the grades. 

## Within subjects ANOVA

Usually looks at multiple measurements of a variable for an individual - so observations aren't independent. 
Often examining changes in an outcome variable over time.

>[!example]
> Whether students have better grades in English or Maths. There is one (dichotomous) independent variable that differs between students, which is the discipline (English/Maths). Each student has two measurements, one for each subject.

Equation is: 

`Y1 - Y2 = b0 + e`

If b0 is statistically significant, then student's grades differ from each other. 

Better than paired sample t test because they allow for multiple independent variables with two or more levels each.

## 2 x 2 Mixed ANOVA

Combination of between-unit ANOVA and within-unit ANOVA. Requires:
- Min 2 categorical independent variables
- At least one should vary between units
- At least one should vary within units. 

The simplest model is then one dichotomous between-subjects variables, and one dicotomous within-subjects variable. 

> [!Example]
> Comparing grades in English and Maths for Boys and Girls. 
> Assume we predict that girls have better grades than boys, and this difference in genders is bigger for English v Maths. 
> This is a classic 2 x 2 design. 

This design allows for testing of whether any of the two main effects (gender or subject), or an interaction effect, are significant.

The equations are:

```
[1] (Y1 + Y2)/2 = b0 + b1X + e
[2] (Y1 - Y2) = b0 + b1X + e
```

In Eq1 b1 is the main effect of gender (between subjects)
In Eq2 b0 is the main effect of subject (within subjects)
In Eq2 b1 is the interaction effect of gender * subject

In Eq1 b0 is usually the grand mean, not really used.

>[!important]
>The intercept b0 in Eq2 is only useful if the between-subjects variable (X, gender) is **centered**. E.g. coded as -0.5 +0.5 instead of 1 and 2. 
Many statistical programmes will do this for you, but need to check. 


## Advanced Mixed Models

### 2 x 2 mixed ANOVA

Researchers sometimes use this design for 'pre-test' and 'post-test' as the within-subjects variable.
However, power can be increased by including the pretest as a covariate (i.e. by regressing the posttest on both the between-subjects variable and the pretest). 
This is dependent on some assumptions.
### 3 x 2 mixed ANOVA

Useful for the [Parenting project](obsidian://Project Notes/Parenting)
A type of advanced mixed model. 

Can contain within-subjects independent variables with more than two levels, such as if the above example with students and subjects contained English, Maths and Biology (3 levels). This gives a 2 x 3 factorial design. 

Should be used when: 
- continuous dependent variable
- two or more categorical independent variables
- at least one independent variable that vaires between-units
- at least one independent variable that varies within units.
Where units are usually subjects. 

### Mixed Model ANCOVA

A Mixed Model ANOVA with a Covariate. 
For instance, we might want to include parental income as a possible covariate. 

At this point though, consider linear models as an alternative.


## Assumptions

Aside from the regular assumptions for ANOVA/ANCOVA there are heavier assumptions for advanced mixed models - specifically something called sphericity, which applies with 3 or more levels. This is not necessary for linear mixed models, which may be a better option at this stage. 


----
Notes were made from:
[The Sage Encyclopedia of Education Research, Measurement and Evaluation: Mixed Model Analysis of Variance](https://psych.wisc.edu/Brauer/BrauerLab/wp-content/uploads/2014/04/Murrar-Brauer-2018-MM-ANOVA.pdf)

