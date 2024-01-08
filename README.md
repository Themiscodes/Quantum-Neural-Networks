# Quantum Neural Networks with Qutrits

This repository presents the code implementation for my thesis, "Quantum Neural Networks with Qutrits" [^1], and subsequent paper "The Gell-Mann feature map of qutrits and its applications in classification tasks" [^2] exploring the applicability of three-level quantum systems in quantum machine learning. Qutrits' expanded state space enhances data representation, effectively capturing intricate patterns and relationships. The work introduces the Gell-Mann feature map, encoding information within an 8-dimensional space, specifically designed for classification tasks. 

By delving into the design considerations and experimental setups in detail, this research aims to contribute to the broader understanding of the capabilities and limitations of qutrit-based systems in the context of quantum machine learning, contributing to the advancement of quantum computing and its applications in practical domains.

## Overview

![VQCa](https://github.com/Themiscodes/Quantum-Neural-Networks/assets/73662635/514c96db-e628-4e40-9204-03e0ec9afb9b)


Parameterized quantum circuits encode input data into quantum states using a feature map, followed by a variational layer with adjustable parameter weights. These parameters are iteratively adjusted using classical optimization methods to minimize a predefined objective function.

### Feature Map

The feature map used in this research employs Gell-Mann rotation operators for the encoding process. The potential of this feature map is explored with a Quantum Kernel method, which, unlike variational circuits, relies solely on data encoding.

In the kernel-based method, a quantum device is used to encode the features of two data points. The inner product and kernel estimation of the encoded data are then used as input for a classical support vector machine for classification. The implementation can be found in the [quantum_kernels](quantum_kernels/) directory.

### Quantum Neural Network

The Quantum Neural Network (QNN) architecture explored in this research comprises stacked layers of Parameterized Quantum Circuits (PQCs), which are analogous to classical perceptrons. This approach is inspired by the paper "Data re-uploading for a universal quantum classifier" [^3].

![QNNa](https://github.com/Themiscodes/Quantum-Neural-Networks/assets/73662635/e8bfb173-1b13-482a-81a5-70e7cb13014d)

The QNN class, implemented as a PyTorch module, allows for the specification of the number of layers and features during initialization. This design choice enables a modular framework that can be readily adjusted and modified during hyperparameter tuning to align with the underlying geometry of the problem. The implementaion can be found in the [quantum\_neural\_network](quantum_neural_network/) directory.

The effectiveness of increasing the number of qutrits varied across datasets. In some cases, utilizing multiple qutrits led to improved performance, whereas for other datasets, a single qutrit sufficed. These observations are also corroborated by the findings in the paper "Classification of data with a qudit, a geometric approach" [^4].

For more details, please refer to the [thesis](thesis/), which is designed to maintain clarity and accessibility for readers who may not possess prior familiarity with quantum computing. The research provides comprehensive descriptions of each architecture and implementation, while practical demonstrations and insights can be found in the corresponding notebooks.

## References

[^1]: [Quantum Neural Networks with Qutrits](https://pergamos.lib.uoa.gr/uoa/dl/frontend/el/browse/3338218) by Themistoklis Valtinos.

[^2]: [The Gell-Mann feature map of qutrits and its applications in classification tasks](https://arxiv.org/abs/2312.11150) by T. Valtinos, A. Mandilara and D. Syvridis.

[^3]: [Data re-uploading for a universal quantum classifier](https://arxiv.org/abs/1907.02085) by Adrián Pérez-Salinas, Alba Cervera-Lierta, Elies Gil-Fuster, José I. Latorre.

[^4]: [Classification of data with a qudit, a geometric approach](https://arxiv.org/abs/2307.14060) by A. Mandilara, B. Dellen, U. Jaekel, T. Valtinos and D. Syvridis.
