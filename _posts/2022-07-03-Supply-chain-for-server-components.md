---
layout: post
title: Supply chain for server components using survival analysis, XGB embedding
subtitle: predictive model for the live data of servers
thumbnail-img: /assets/img/covid.jpeg
cover-img: /assets/img/Pharmaceutical_portada.jpeg
gh-badge: [star, fork, follow]
tags: [Data Science, Optimization, XGB, bokeh]
comments: false
---

The big amount of time it takes for components, racks and servers to go live from the moment they are created up was rounding to several years for a big technological company in USA, the number of components also vary and was difficult to estimate. It was needed for them to develop a model to predict with exactitude the number of components they will require and the probability for a component to go out. I was in the development team, during my stay in the project I colaborated in three main parts:
- Development of the predictability model using survival analysis
- Improvement of the model by performing an embedding of the categorical variables using XGBoost.
- Development of the visualization of the model using bokeh.

## Data
Although the data was confidential, the input data was gathered from client servers, having the go live estimate of different rack types across multiple regions for in many different dates. The features selected were mainly categorical, as those were the one with best quality. Some of the issues found were the bad quality in numerical data and the different go lives dates of the teams involved in the process of the company. Part of the preprocessing was to adress and solve these issues.

## Survival Model

Survival modeling, or time-to-event modeling, is used for modeling [censored](http://en.wikipedia.org/wiki/Censoring_(statistics)) data. For the cycle time data, we need to account the most common type of censoring, which is right censored.

A true event time is said to be right censored if the event did not occur at the time when the analysis is performed, so it is only known that the true event time is larger than the end of the observation period. In our case this means that the live time of the cluster is greater than the observation period

Assume that failure time $T$ is a nonnegative continuous random variable with a

density function $f (t)$ and a corresponding distribution function $F(t) = P(T ≤ t).$

The survival function of $T$ , the probability of an individual (cluster) surviving beyond time t

or not experiencing a failure up to time t, is defined by

$$
⁍
$$

Also, from the definition of $F(t)$ we obtain that 

$$
S(t) = 1 − P(\text{an individual fails before or at t}) = 1 − F(t).
$$

Notice that S(t) is a monotonically decreasing continuous function with

$$
S(0) = 1 ,\quad S(\infty) = lim_{t→∞} S(t) = 0.
$$

*The hazard function $\lambda(t)$ is defined as $\lambda(t) = f(t)/S(t)$.*

We can think of it as the instantaneus failure at time $t$, given the individual survived just prior to $t$.

Also, since $f(t) = -\frac{dS(t)}{dt}$ is easy to see that 

$$
\lambda(t) = -\frac{d}{dt}\log S(t)
$$

Then 

$$
-\log S(t) = \int_0^t\lambda(x)dx 
$$

And 

$$
S(t) = exp\left(-\int_0^t\lambda(x)dx\right) = exp\left(-\Lambda(t)\right) 
$$

The distribution of survival time is often positively skewed. The exponential and Weibull distributions are popular choices for modeling survival data. For this project a Weibull distribution was used.

## Embedding using XGB
The most obvious way to encode categorical data is through using one hot encoding, however this presents some problems, for instance doesn`t preserve distances in the new space. For this reason another approach to encoding the categorical data was performed: Embedding using an ensamble of trees. In this case  XGBoost with was used.

Transform your features into a higher dimensional, sparse space. Then train a linear model on these features.

First fit an ensemble of trees (totally random trees, a random forest, or gradient boosted trees) on the training set. Then each leaf of each tree in the ensemble is assigned a fixed arbitrary feature index in a new feature space. These leaf indices are then encoded in a one-hot fashion.

Each sample goes through the decisions of each tree of the ensemble and ends up in one leaf per tree. The sample is encoded by setting feature values for these leaves to 1 and the other feature values to 0.

The resulting transformer has then learned a supervised, sparse, high-dimensional categorical embedding of the data.
Probably the most difficult part of the project, tecnically speaking, as I had to learn new software, connecting the outputs and inputs to Riverlogic servers and creating a lot of SQL querys. We closely work with Riverlogic`s top developers, developing the model after continues feedback from the client. The results were considered succesful by the client, as important characteristics and behaviours observed by them in the reality (supply shortage, filled warehouses, production rates) were captured by our model.

I made a demo of this implementation with good results, the new embedding outperdormed OHE, although with a time cost that increased the run time of the survival model up to 10 minutes compared with 4 minutes in the case of OHE. This was not a huge problem as the model was not intended to be run frequently.

## Visualization and supply chain
Lastly, the visualization of the graph was done using the [bokeh](https://docs.bokeh.org/en/latest/) package in a similar fashion as seen below. The graph was interactive and dynamic, meaning that all the evolution of the model across different years can be seen in the graph.
![Figure 1](/assets/Figuras/bokeh_graph.gif)

