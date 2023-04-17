---
type: web article
creationtag: 2023-01-12 12:30
title: "What is the Difference Between Gradient Descent and Gradient Ascent?"
URL: "https://www.baeldung.com/cs/gradient-descent-vs-ascent"
people: []
infotags: []
project:
citekey:
---

> [!Excerpt] What is the Difference Between Gradient Descent and Gradient Ascent? | Baeldung on Computer Science
> Learn about gradient descent and gradient ascent and when to use them.

---
  

If you have a few years of experience in Computer Science or research, and you’re interested in sharing that experience with the community, have a look at our [**Contribution Guidelines**](https://www.baeldung.com/cs/contribution-guidelines).

## 1\. Overview[](https://www.baeldung.com/cs/gradient-descent-vs-ascent#overview)

In this tutorial, we’ll study the difference between gradient descent and gradient ascent.

At the end of this article, we’ll be familiar with the difference between the two and know how to convert from one to the other.

## 2\. The Gradient in General[](https://www.baeldung.com/cs/gradient-descent-vs-ascent#the-gradient-in-general)

The gradient of a continuous function ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-f5844370b6482674a233a3063f762555_l3.svg]] is defined as **the vector that contains the partial derivatives** ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-543354c1e2262ce8edaf2c25ca9a9bd5_l3.svg]] computed at that point ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-5faad0904f612a3fa5b27faafb8dc903_l3.svg]]. The gradient is finite and defined if and only if all partial derivatives are also defined and finite. With formal notation, we indicate the gradient as:

![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-133a31967b684d56f788e2ceaf4d4a89_l3.svg]]

When using the gradient for optimization, we can either conduct gradient *descent* or gradient *ascent*. Let’s now see the difference between the two.

[Gradient descent](https://www.baeldung.com/java-gradient-descent) is an iterative process through which we optimize the parameters of a [machine learning model](https://www.baeldung.com/cs/machine-learning-how-to-start). It’s particularly used in [neural networks](https://www.baeldung.com/cs/neural-net-advantages-disadvantages), but also in [logistic regression](https://www.baeldung.com/cs/linear-vs-logistic-regression#logistic-regression) and [support vector machines](https://www.baeldung.com/cs/ml-support-vector-machines).

It’s the most typical method for iterative minimization of a [cost function](https://www.baeldung.com/cs/learning-curve-ml#2-single-curves). **Its major limitation, though, consists of its guaranteed convergence to a local, not necessarily global, minimum**:

![[https://www.baeldung.com/wp-content/uploads/sites/4/2020/08/loc_glob_minima-1.png]]

A hyperparameter ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-5f44d9bbc8046069be4aa2989bff19aa_l3.svg]], also called the [learning rate](https://www.baeldung.com/spark-mlib-machine-learning#2-model-hyper-parameter-tuning), allows the fine-tuning of the process of descent. In particular, with an appropriate choice of ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-5f44d9bbc8046069be4aa2989bff19aa_l3.svg]], we can escape the convergence to a local minimum, and descend towards a global minimum instead.

The gradient is calculated with respect to a vector of parameters for the model, typically the weights ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-d4b432605ef5750fdc8e364f5bc8beea_l3.svg]]. In neural networks, the process of applying gradient descent to the weight matrix takes the name of the [backpropagation of the error](https://www.baeldung.com/cs/ml-nonlinear-activation-functions#magicparlabel-11835).

Backpropagation uses the sign of the gradient to determine whether the weights should increase or decrease. The sign of the gradient allows us to decide the direction of the closest minimum to the cost function. For a given parameter ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-5f44d9bbc8046069be4aa2989bff19aa_l3.svg]], we iteratively optimize the vector ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-d4b432605ef5750fdc8e364f5bc8beea_l3.svg]] by computing:

![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-8c3bb86ed151bddf3301c79e02d64c21_l3.svg]]

And this is the graphical representation:

![[https://www.baeldung.com/wp-content/uploads/sites/4/2020/08/1-1.png]]

We can read the formula above like this. At step ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-ec4217f4fa5fcd92a9edceba0e708cf7_l3.svg]], the weights of the neural network are all modified by the product of the hyperparameter ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-5f44d9bbc8046069be4aa2989bff19aa_l3.svg]] times the gradient of the cost function, computed with those weights. **If the gradient is positive, then we decrease the weights;** and conversely, if the gradient is negative, then we increase them.

## 4\. Gradient Ascent[](https://www.baeldung.com/cs/gradient-descent-vs-ascent#gradient-ascent)

Gradient ascent works in the same manner as gradient descent, with one difference. **The task it fulfills isn’t minimization, but rather maximization of some function**. The reason for the difference is that, at times, we may want to reach the maximum, not the minimum of some function; this is the case, for instance, if we’re maximizing the distance between [separation hyperplanes and observations](https://www.baeldung.com/cs/ml-support-vector-machines#2-separation-hyperplane-and-support-vectors).

For this reason, the formula that describes gradient ascent is similar to the one for gradient descent. Only, with a flipped sign:

![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-077cd6c25237e82a2ab9bd63d635da66_l3.svg]]

If gradient descent indicates an iterative movement towards the closest minimum, gradient ascent, conversely, indicates a movement towards the nearest maximum. In this sense, for any function ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-f5844370b6482674a233a3063f762555_l3.svg]] on which we apply gradient descent, there is a symmetric function ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-9dc7ff4ff5dd9b02ddf76810c3b10911_l3.svg]] on which we can apply gradient ascent.

This means also that **a problem tackled through gradient descent also has solutions that we can find through gradient ascent, if only we reflect it upon the axis of the independent variable**. This image shows the same function of the previous graph, but reflected along the ![[https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-7e5fbfa0bbbd9f3051cd156a0f1b5e31_l3.svg]] axis:

![[https://www.baeldung.com/wp-content/uploads/sites/4/2020/08/3.png]]

In our article on the [cost function for logistic regression](https://www.baeldung.com/cs/cost-function-logistic-regression-logarithmic-expr#cost-function-of-the-logistic-regression), we studied the usage of the log-likelihood and its relation to convexity. If we use a positive log-likelihood, then the objective function is concave and we must use gradient ascent. Conversely, if we use negative log-likelihood, as is common practice, we should instead use gradient descent.

**This is because gradient descent works on convex objective functions, while gradient ascent requires concave functions**.

## 5\. Gradient Descent or Gradient Ascent?[](https://www.baeldung.com/cs/gradient-descent-vs-ascent#gradient-descent-or-gradient-ascent)

We can now sum-up the considerations made above:

-   The gradient is the vector containing all partial derivatives of a function in a point
-   We can apply gradient descent on a convex function, and gradient ascent on a concave function
-   Gradient descent finds the nearest minimum of a function, gradient ascent the nearest maximum
-   We can use either form of optimization for the same problem if we can flip the objective function

With this said, **gradient descent is more common in practice than gradient ascent**.

## 6\. Conclusions[](https://www.baeldung.com/cs/gradient-descent-vs-ascent#conclusions)

In this tutorial, we studied the concept of gradient, and learned the distinction between gradient descent and gradient ascent.

If you have a few years of experience in Computer Science or research, and you’re interested in sharing that experience with the community, have a look at our [**Contribution Guidelines**](https://www.baeldung.com/cs/contribution-guidelines).
