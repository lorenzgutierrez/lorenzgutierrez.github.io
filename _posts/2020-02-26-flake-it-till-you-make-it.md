---
layout: post
title: Sindy
subtitle: Classificator using LASSO for clusters neurons signals
cover-img: /assets/img/path.jpg
gh-repo: lorenzgutierrez/Sindy
gh-badge: [star, fork, follow]
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [Sindy, Data analysis, Lasso, Clustering]
---

My PhD director developed a beautiful algorithm named `Wave_clus` writen in matlab that basically clusterizes the signals comming from electrodes in brain's patients in order to diferentiate the activity of those neurons. The problem with this algorithm is that can't decide what "cluster" is effectively a neuron cluster or a noise cluster.

Since we alredy have a big database of clusters we started to label those that were neuron clusters and those that weren t. The idea of this project was to use the fact the neuronal acitvity is easily simulated and charactherized by a few parameters of simple models. The hypothesis was that the value of those parameters would allow us to diferenciate noise from neuron activity.

We used a novel aproach named `Sparse Algorithm of Non-linear Dynamics System` with a LASSO regressor in order to find the dinamics of our database. Altough this was a very interesting approach and I learnt a lot, I could'nt make it work.

## The data
In the next plot you can see neuron clusters (Cluster 1) and noisy clusters (Cluster 2,3) from one of the recordings fo neural activity (same electrode).
![Figure 1](/assets/Figuras/Clusters_example.png)

While the standard deviation, the max amplitude of the cluster and some other features give information about if a cluster is noise or not, this project used only the average signal of each cluster. Normalizing and using `Hierarchical clustering` I grouped those neuron cluster who shared similarities. The results below:
![Figure 2](/assets/Figuras/Hierarchical_clustering.png)

## Embeddings
One of the most important concepts for this project was that of *embeddings*. Since Sindy requires full knowledge of the *phase space*, an embedding is the way you can construct the former via partial observation of the phenomena (in this case, the partial observation was the mean signal cluster). Below is a figure of the aproximated phase space recreated from one of the clusters we got.

![Figure 3](/assets/Figuras/Embedding.png)

## Sindy
Sindy is a novel framework to discover governing equations underlying a dynamical system simply from data measurements, leveraging advances in sparsity techniques and machine learning. The resulting models are parsimonious, balancing model complexity with descriptive ability while avoiding overfitting. There are many critical data-driven problems, such as understanding cognition from neural recordings, inferring climate patterns, determining stability of financial markets, predicting and suppressing the spread of disease, and controlling turbulence for greener transportation and energy. With abundant data and elusive laws, data-driven discovery of dynamics will continue to play an important role in these efforts.

Literally, Sindy is a framework that fits models to data. The parameter values of that model is what we were looking for. In this case, our model was of the form

![Figure 4](/assets/Figuras/Sindy_equation.png)

as previous research showed that with this model many neuronal dynamics should be contained for different values of the parameters.

## Results
While the parameters of the model were determinated for each cluster, the solutions were highly unstable, leading to a bad predictor for new data. Besides that, I was surprised to see how easy and powerful Sindy is, as is clear that the results are close enough to the true solution in the parameter space. I used an interpolation of the signals to see if an stable solution to the dynamics could be obtained, but there were not significal improvements. 

![Figure 5](/assets/Figuras/Sindy_result.png)

## To do
I am quite sure that this SHOULD work, probably expending more time in this project will give better results. Probably another model could be used. Instead of using LASSO other method may improve the stability of the solution. I enjoyed a lot this project.






