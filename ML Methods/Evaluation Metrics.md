
[StatQuest has a good video to help you remember the different names and definitions.](https://www.youtube.com/watch?v=PWvfrTgaPBI&list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF&index=5)


| Name | Definition | Use Cases |
|-------|--------|--------|
|Accuracy | Overall percentage of correct classifications (pos and neg) | You have balanced classes and all classes are important.| 
|Precision | Percentage of predicted positives that are correct |. |
|Recall / Sensitivity | Percentage of true positives correctly predicted. | | 
|Specificity | Percentage of true negatives correctly predicted. | | 
|F1 Score |The harmonic mean of precision and recall.  |Best when you care more about the positive class. | 
|ROC AUC | | Balanced dataset, where you care equally about positive and negative classes. | 
|PR AUC |Area Under the Precision-Recall Curve as threshold changes. Think of it as the average of precision scores calculated for each recall threshold. | When classes are imbalanced and you are trying to identify positive cases (e.g. medicine, fraud detection) this is a much better choice. | 

ROC or PR curves are created by classification methods that use a _score_ or _probability_ that each instance is a member of a class. For example, [[Naive Bayes]], or [[CNNs]]. 

We can use these probabilistic classifiers with a threshold to turn them into discrete classifiers. The classification curves (ROC/PR) represent what happens when we try different thresholds. 

We can also turn discrete classifiers into scoring classifiers by looking at their instance statistics (Fawcett, 3.3 p12). You could also train an [[Ensemble Learning]] model and use the set of votes as a score. 

---

[Fawcett, T (2004) ROC Graphs: Notes and Practical Considerations for Researchers](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.10.9777&rep=rep1&type=pdf)
