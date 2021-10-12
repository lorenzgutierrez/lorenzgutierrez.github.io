---
layout: post
title: Sindy
subtitle: Classificator using LASSO for clusters neurons signals
cover-img: /assets/img/path.jpg
gh-repo: lorenzgutierrez/Sindy
gh-badge: [star, fork, follow]
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [books, test]
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
![Figure 3](/assets/Figuras/Embeddings.png)

## Sindy
Sindy is a novel framework to discover governing equations underlying a dynamical system simply from data measurements, leveraging advances in sparsity techniques and machine learning. The resulting models are parsimonious, balancing model complexity with descriptive ability while avoiding overfitting. There are many critical data-driven problems, such as understanding cognition from neural recordings, inferring climate patterns, determining stability of financial markets, predicting and suppressing the spread of disease, and controlling turbulence for greener transportation and energy. With abundant data and elusive laws, data-driven discovery of dynamics will continue to play an important role in these efforts.

Literally, Sindy is a framework that fits models to data. The parameter values of that model is what we were looking for. In this case, our model was of the form

![Figure 4](<a href="https://www.codecogs.com/eqnedit.php?latex=\begin{equation}&space;\begin{align*}&space;\dot{x}&space;&&space;=&space;y&space;\\&space;\dot{y}&space;&&space;=&space;a&space;&plus;&space;bx&space;&plus;&space;cy&space;&plus;&space;dxy&space;&plus;&space;e&space;y^2&space;&plus;&space;x^2y&space;\end{align}&space;\end{equation}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\begin{equation}&space;\begin{align*}&space;\dot{x}&space;&&space;=&space;y&space;\\&space;\dot{y}&space;&&space;=&space;a&space;&plus;&space;bx&space;&plus;&space;cy&space;&plus;&space;dxy&space;&plus;&space;e&space;y^2&space;&plus;&space;x^2y&space;\end{align}&space;\end{equation}" title="\begin{equation} \begin{align*} \dot{x} & = y \\ \dot{y} & = a + bx + cy + dxy + e y^2 + x^2y \end{align} \end{equation}" /></a>)


as previous research showed that with this model many neuronal dynamics should be contained for different values of the parameters

Under what circumstances should we step off a path? When is it essential that we finish what we start? If I bought a bag of peanuts and had an allergic reaction, no one would fault me if I threw it out. If I ended a relationship with a woman who hit me, no one would say that I had a commitment problem. But if I walk away from a seemingly secure route because my soul has other ideas, I am a flake?

The truth is that no one else can definitively know the path we are here to walk. It’s tempting to listen—many of us long for the omnipotent other—but unless they are genuine psychic intuitives, they can’t know. All others can know is their own truth, and if they’ve actually done the work to excavate it, they will have the good sense to know that they cannot genuinely know anyone else’s. Only soul knows the path it is here to walk. Since you are the only one living in your temple, only you can know its scriptures and interpretive structure.

At the heart of the struggle are two very different ideas of success—survival-driven and soul-driven. For survivalists, success is security, pragmatism, power over others. Success is the absence of material suffering, the nourishing of the soul be damned. It is an odd and ironic thing that most of the material power in our world often resides in the hands of younger souls. Still working in the egoic and material realms, they love the sensations of power and focus most of their energy on accumulation. Older souls tend not to be as materially driven. They have already played the worldly game in previous lives and they search for more subtle shades of meaning in this one—authentication rather than accumulation. They are often ignored by the culture at large, although they really are the truest warriors.

A soulful notion of success rests on the actualization of our innate image. Success is simply the completion of a soul step, however unsightly it may be. We have finished what we started when the lesson is learned. What a fear-based culture calls a wonderful opportunity may be fruitless and misguided for the soul. Staying in a passionless relationship may satisfy our need for comfort, but it may stifle the soul. Becoming a famous lawyer is only worthwhile if the soul demands it. It is an essential failure if you are called to be a monastic this time around. If you need to explore and abandon ten careers in order to stretch your soul toward its innate image, then so be it. Flake it till you make it.
