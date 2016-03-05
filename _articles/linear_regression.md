---
title: Introduction
section: Linear Regression
---

Regression problems aim to find relationships between input variables and their
corresponding outputs using labelled past experience to learn models that can
predict future outcomes.  <span>Input variables are variously called
*predictor*, *feature*, *regressor*, *explanatory*, *exogenous* or *independent
variables*.  Similarly, output variables may also be referred to as *response*,
*regressand*, *criterion*, *measured*, *exogenous* or *dependent
variables*.</span>{:.mn} They are examples of *supervised learning* tasks, all
of which share the same goal of inferring predictive functions from annotated
training data.

In general, the outputs, which we will denote $$y$$, may be any element chosen
from a given *output space*, $$\mathcal{Y}$$. In *univariate* regression --- the
kind we'll be focusing on in these notes --- the response variable is a single
real scalar value, so $$ \mathcal{Y} = \mathbb{R} $$. There may, however, be
multiple input variables, $$x_i$$, and it is convenient to refer to all of the
input components of a given instance as a single vector, $$x$$,

<div> $$ x = \left(\begin{array}{c} x_1 \\ \vdots \\ x_N \end{array}\right) $$
</div>{:.mb}

chosen from the *input space*, $$ \mathcal{X} = \mathbb{R}^N $$.

As in all supervised learning tasks, we are initally provided a *training set*,
$$\mathcal{D} = (x^{(1)}, y^{(1)}), \ldots, (x^{(m)}, y^{(m)})$$, of *m*
training examples, each of which consists of an input vector $$x^{(i)} \in
\mathcal{X}$$ and its measured output $$y^{(i)} \in \mathcal{Y}$$. <span>The
notation $$x^{(i)}$$ indicates the *i*th training examples, and should not be
confused with exponentiation.</span>{:.mn} The task is to find a target function
$$ f: \mathcal{X} \mapsto \mathcal{Y} $$ that most closely matches what we
observe in $$\mathcal{D}$$. It can be shown (and should also make intuitive
sense), that the $$f$$ that meets this criterion on our training set is also
most likely to do well on new, previously unseen inputs (provided they are drawn
from the same distribution as the training data).

In order to determine $$f$$, we will narrow down our search to a particular
hypothesis set, $$ \mathcal{H} = \{ h : \mathcal{X} \mapsto \mathcal{Y} \} $$,
where each element $$h$$ is a possible candidate for our target function. A good
first choice of the hypothesis set is the set of all linear combinations of
$$x_i$$,

<div> $$ h(x) = b_0 + b_1 x_1 + \ldots + b_N x_N \tag{1} $$ </div>{:.mb}

where $$b_i$$ are the weights to attach to each feature. In this linear model,
the larger a particular weight, $$b_i$$, the greater the impact of the
corresponding component of the input vector, $$x_i$$, on the predicted outcome.

Finally, we can simplify our notation a little bit by prepending our $$x$$
vectors with a bias component that is always equal to one,

<div> $$ x = \left(\begin{array}{c} 1 \\ x_1 \\ \vdots \\ x_N \end{array}\right)
$$ </div>{:.mb}

If we then define a weight vector $$ \beta^\top = (b_0, b_1, \ldots, b_N)
$$<span> Note that $$^\top$$ indicates the transpose, so $$ \beta =
\left(\begin{array}{c} b_0 \\ b_1 \\ \vdots \\ b_N \end{array}\right)
$$</span>{:.mn}, we can rewrite equation (1) as

<div> $$ h(x; \beta) = \beta^\top x $$ </div>{:.mb}

Our task now is to find the weight vector, $$\beta^*$$, for which
$$h(x;\beta^*)$$ most closesly approximates our training set, $$\mathcal{D}$$.
We will explore common ways of determining these optimal weights in the next set
of notes.
