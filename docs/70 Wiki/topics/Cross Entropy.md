---
aliases: [Cross-Entropy,]
type: topics
status: open
priority: p4
creationtag: 2023-02-08 12:53
infotags:
---

From[A Gentle Introduction to Cross-Entropy for Machine Learning - MachineLearningMastery.com](https://machinelearningmastery.com/cross-entropy-for-machine-learning/)

> Cross-entropy is commonly used in machine learning as a loss function.
> 
> Cross-entropy is a measure from the field of information theory, building upon [entropy](https://machinelearningmastery.com/what-is-information-entropy/) and generally calculating the difference between two probability distributions. It is closely related to but is different from [KL divergence](https://machinelearningmastery.com/divergence-between-probability-distributions/) that calculates the relative entropy between two probability distributions, whereas cross-entropy can be thought to calculate the total entropy between the distributions.
> 
> Cross-entropy is also related to and often confused with [logistic loss, called log loss](https://machinelearningmastery.com/logistic-regression-with-maximum-likelihood-estimation/). Although the two measures are derived from a different source, when used as loss functions for classification models, both measures calculate the same quantity and can be used interchangeably.

From: Pytorch Tutorial:
> If you're using negative log likelihood loss and log softmax activation, then Pytorch provides a single function `F.cross_entropy` that combines the two. So we can even remove the activation function from our model.



# Vault Query
```query 
line:("Cross Entropy") OR  line:("Cross-Entropy") 
```