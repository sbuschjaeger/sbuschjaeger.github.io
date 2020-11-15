---
layout: page
permalink: /software/
title: software
description: I do some programming. That stuff is mostly in Python and C/C++. 
nav: true
---

These are some software packages which are independent from specific papers and which I try to maintain as best as possible. For a complete list of software projects checkout my github [repistories](https://github.com/sbuschjaeger?tab=repositories).

### pysembles

PyTorch + Ensembles = Pysembles. This is a collection of ensembling algorithms implemented in PyTorch for our paper ["Generalized Negative Correlation Learning for Deep Ensembling"](https://arxiv.org/abs/2011.02952). These are mostly straightforward implementations with some optimizations. Currently I maintain the following ensembling algorithms:

    - (Generalized) Negative Correlation Learning
    - Bagging
    - (Stochastic) Gradient Boosting
    - Snapshot Ensembles
    - Stochastic Multiple Choice Learning
    - End2End Ensembles
    - Stacking

Check out the repo. for more information [https://github.com/sbuschjaeger/Pysembles](https://github.com/sbuschjaeger/Pysembles)

### submodular Streaming Maximization

Submodular Maximization meets streaming in a header-only C++ library with Python bindings. We wrote this code for our paper ["Very Fast Streaming Submodular Function Maximization"](https://arxiv.org/abs/2010.10059) which introduces a new nonnegative submodular function maximization algorithm for streaming data. For our experiments, we also implemented already existing state-of-the-art streaming algorithms for which we could not find an implementation. Currently the following algorithms are implemented:

    - Greedy
    - SieveStreaming
    - SieveStreaming++
    - ThreeSieves
    - Random
    - Salsa

Huge shoutout goes to [Philipp Honysz](https://github.com/philippjh) how came up with the initial implementation during his master thesis.
Check out the repo. for more information [https://github.com/sbuschjaeger/SubmodularStreamingMaximization](https://github.com/sbuschjaeger/SubmodularStreamingMaximization)


### fastinference

Machine learning + jinja2 = FastInference. FastInference is a machine learning model compiler specifically targeted to small, embedded systems. Moreover, we aim to provide an easily extensible framework for researches and practitioners alike. The main idea behind FastInference is to statically compile models into source code files which are then compiled using a regular compiler. This two-step process has the advantage that there is no runtime environment required on the target system, and we can make use of system-specific instructions on the embedded system. To make this approach flexible and accessible we heavily rely on template instantiation managed by jinja2. Simply put, we provide a set of pre-programmed template for different ML models for a target language / backend and then FastInference will make sure that correct data types, instructions etc. are used during template instantiation. In order to add new ML models and/or backend you simply need to provide the core computations for model application as jinja2 template. 

If you are interested in deploying machine learning models for production then this project is probably not mature enough for you. For deep learning there are a ton of frameworks available such as [glow](https://github.com/pytorch/glow), [tensorflow-lite](https://www.tensorflow.org/), [ONNX Runtime](https://github.com/microsoft/onnxruntime), [NGraph](https://github.com/NervanaSystems/ngraph), [MACE](https://github.com/XiaoMi/mace), [NCNN](https://github.com/Tencent/ncnn), [NVIDIA TensorRT](https://developer.nvidia.com/tensorrt), [OpenVINO Toolkit](https://github.com/openvinotoolkit/openvino) and probably more. 
For classical machine learning algorithm we have fewer, but still very capable model compiler such as [Hummingbird](https://github.com/microsoft/hummingbird) or 
[Treelite](https://github.com/dmlc/treelite).

If you are interested in quickly trying out more obscure implementations then this tool might be intrestring for you. FastInference supports the generation of Binarized Neural Networks and has been used in our ECML Paper "On-Site Gamma-Hadron Separation with Deep Learning on FPGAs". It also has been used for generating cache-friendly DT ensembles in our paper "Realization of Random Forest for Real-Time  Evaluation through Tree Framing". 

Check out the repo. for more information [https://github.com/sbuschjaeger/fastinference](https://github.com/sbuschjaeger/fastinference)