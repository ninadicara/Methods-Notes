
Type I Error: Reject the null hypothesis when it is true
Type II Error: Accept the null hypothesis when it is false

## Standard Error of the mean

The standard error is the range in which the true population mean will fall, and sits around the sample mean. 
It can be considered a measure of the _precision of the sample mean_. 

>[!important] Standard Error = Standard Deviation / SQRT(Sample Size)

The SE is the Standard Deviation of a sampling distribution. As such, Standard Error goes down as Sample Size increases because there is less variability. This is a safe estimate with samples of size 30 or more. 

You could use [[Bootstrapping]] to estimate the standard error because you would be sampling many means from 'different' simulated samples. 

## Confidence Intervals

A 95% confidence is the sample mean plus or minus 1.96 times the Standard Error. 

>[!important] Confidence Interval = ± 1.96 x Standard Error

## When to use CI versus SE

Standard Error by its definition invites a comparison with the normal distribution. So, don't use it if you're talking about a distribution that is highly skewed. 



---

[Altman, D. G., & Bland, J. M. (2005). Standard deviations and standard errors. _Bmj_, _331_(7521), 903.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1255808)
Statistics without Tears 
