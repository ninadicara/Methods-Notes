PCA reduces down the features of a dataset by creating a linear combination of variables (essentially a weighted average). 
It optimises the right way to weight and combine the variables to represent the most possible variance in each subsequent PC. 

The first principal component (PC) has a slope that best fits the data (based on minimising the perpendicular distance from data points to the slope). Then each next PC is orthogonal to the previous one, but in the direction of the next most variance.

## Idiots guide

The first principal component (PC) has a slope that best fits the data (based on minimising the perpendicular distance from data points to the slope). Then each next PC is orthogonal to the previous one, but in the direction of the next most variance.

These images by [Allison Horst](https://allisonhorst.com/everything-else) illustrate the idea of turning the first eigenvector (the whales mouth) to fit in the most shrimp. 

![PCA1 | 300](https://cdn.myportfolio.com/45214904-6a61-4e23-98d6-b140f8654a40/5937aa47-fc1b-48c5-862c-2936e3d2735d_rw_1920.png?h=75157a066efc94b5fc105670762d04d7)

![PCA2|300](https://cdn.myportfolio.com/45214904-6a61-4e23-98d6-b140f8654a40/c0b2a110-60ee-41c6-90e0-8f399141f128_rw_1920.png?h=d6394a7c0693830945f568a0605a2475)

## Technical stuff 

The percentage of variance explained by each principle component is the eigenvalue which is the average distance from each point to the slope. 
The eigen vector is a unit increase along the slope. 

## Choosing how many PCs to keep

Choosing the right number of principal components depends on your purpose. 

There will be n-1 PCs, where n is the total number of variables. 

You can calculate the cumulative amount of variance explained by using each additional PC, and it's up to you to decide how much variance is necessary for your purpose. 

However, if you're trying to plot it, you obviously only want 2 or 3. 

You can use a scree plot ('elbow plot') to visualise this too. 
On a scree plot the eigen values are on the y axis and each PC is on the x axis. 
You can look for the 'elbow' in the data, where the eigen values get much smaller and so are less important in representing the data.  

