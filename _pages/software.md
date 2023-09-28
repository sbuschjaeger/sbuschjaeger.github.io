---
layout: page
permalink: /software/
title: software
description: I do some programming. That stuff is mostly in Python and C/C++. 
nav: False
---

These are some software packages which are independent from specific papers and which I try to maintain as best as possible. For a complete list of software projects checkout my github [repositories](https://github.com/sbuschjaeger?tab=repositories).

### Shrub Ensembles

Shrub Ensembles are ensembles of small decision trees (hence _shrubs_) computed by a combination of regular batch DT algorithms and a global refinement minimizing a joint loss function. Shrub Ensembles are incredibly versatile. They can be trained via single- and multi-core SGD on a powerful server, via Federated Learning utilizing a network of devices, or directly on a small device after deployment. This software package started as a simple C++ implementation of classic DT algorithms such as CART and then became somewhat optimized over time. For small sample sizes (N < 16000), it usually outperforms [scikit-learn](https://scikit-learn.org/) in terms of speed. 

Check out the repository for more information [https://github.com/sbuschjaeger/ShrubEnsembles](https://github.com/sbuschjaeger/ShrubEnsembles)

### Pysembles

PyTorch + Ensembles = Pysembles. This is a collection of ensembling algorithms implemented in PyTorch for our paper ["Generalized Negative Correlation Learning for Deep Ensembling"](https://arxiv.org/abs/2011.02952). These are mostly straightforward implementations with some optimizations. Currently, I maintain the following ensembling algorithms:

- (Generalized) Negative Correlation Learning
- Bagging
- (Stochastic) Gradient Boosting
- Snapshot Ensembles
- Stochastic Multiple Choice Learning
- End2End Ensembles
- Stacking

Check out the repository for more information [https://github.com/sbuschjaeger/Pysembles](https://github.com/sbuschjaeger/Pysembles)

### Submodular Streaming Maximization

Submodular Maximization meets streaming in a header-only C++ library with Python bindings. We wrote this code for our paper ["Very Fast Streaming Submodular Function Maximization"](https://arxiv.org/abs/2010.10059) which introduces a new nonnegative submodular function maximization algorithm for streaming data. For our experiments, we also implemented already existing state-of-the-art streaming algorithms for which we could not find an implementation. Currently, the following algorithms are implemented:

- Greedy
- SieveStreaming
- SieveStreaming++
- ThreeSieves
- Random
- Salsa
- IndependentSetImprovement

A huge shout out goes to [Philipp Honysz](https://github.com/philippjh) who came up with the initial implementation during his master thesis.
Check out the repository for more information [https://github.com/sbuschjaeger/SubmodularStreamingMaximization](https://github.com/sbuschjaeger/SubmodularStreamingMaximization)

### PyPruning

Ensemble Pruning in Python. PyPruning provides implementations for the most common ensemble pruning algorithms. Pruning algorithms aim to select the best subset of an trained ensemble to minimize memory consumption and maximize accuracy. Currently, six types of pruning algorithms are implemented:

- `RandomPruningClassifier`: Selects a random subset of classifiers. This is mainly used as a baseline.
- `RankPruningClassifier`: Rank each classifier according to a given metric and then select the best K classifier.
- `ClusterPruningClassifier`: Cluster the classifiers according to a clustering method and then select a representative from each cluster to from the sub-ensemble.
- `GreedyPruningClassifier`: Proceeds in rounds and selects the best classifier in each round given the already selected sub-ensemble. 
- `MIQPPruningClassifier`: Constructs a mixed-integer quadratic problem and optimizes this to compute the best sub ensemble. 
- `ProxPruningClassifier`: Minimize a (regularized) loss function via (stochastic) proximal gradient descent over the ensembles weights. 

Check out the repository for more information [https://github.com/sbuschjaeger/pypruning](https://github.com/sbuschjaeger/pypruning)

### Fastinference

Fastinference is a machine learning model optimizer and model compiler that generates the optimal implementation for your model and hardware architecture. It encapsulates many classical ML algorithms such as Decision Trees or Random Forests as well as modern Deep Learning architectures. It is easily extensible and also offers more obscure models such as [Binarized Neural Networks](https://sbuschjaeger.github.io/fastinference/html/neuralnet.html). In Fastinference 

- **The user comes first:** We believe that the user know best what implementation and what type of optimizations should be performed. Hence, we generate *readable* code so that the user can adapt and change the implementation if necessary. 
- **Optimizations and implementations are separated.** Fastinference distinguishes between model optimizations and model implementation. You can combine different optimizations freely with different implementations and vice-versa. For example, [PyPruning](https://github.com/sbuschjaeger/pypruning) is fully supported. 
- **Rapid prototyping is key** You can easily add your own implementation while benefiting from all optimizations performed on the model and vice-versa. 

Fastinference is currently targeted to small, embedded systems as well as FPGAs, but we are always open to expand it use. For more details please see the [documentation](https://sbuschjaeger.github.io/fastinference/html/index.html).