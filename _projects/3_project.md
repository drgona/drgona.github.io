---
layout: page
title: Decision and Control of Complex Systems 
description: Developing scientific machine learning methods for modeling and control of complex systems.
img: assets/img/publication_preview/NeurIPS_DMM.PNG
importance: 2
category: methods and tools
related_publications: 9993146, 9992386, DRGONA2022121, NEURIPS2021_c9dd73f5, AutoNF_2023, ns2023extreme, wang2023semisupervised, 9809789
---



## Abstract 
The objective of this project is to develop the mathematical foundations and framework for
controlling and optimizing complex systems by developing novel 
[scientific machine learning](https://sites.brown.edu/bergen-lab/research/what-is-sciml/) (SciML) methods. 
In US Department of Energy (DOE) mission areas, the analyses, simulations, and
optimizations of these complex systems have been the objectives of numerous past research efforts.
In this project, we recognize the fundamental challenge of complex system modeling and control,
which is that high-fidelity models can be prohibitively expensive to construct. 
This limitation is not necessarily due to the lack of fundamental understanding of the underlying natural
phenomena but due to practical constraints such as the difficulties in instrumenting the complex
systems to collect relevant data, the need to resolve inherent uncertainties in the models (e.g., due
to unmodeled physics), and the loss of observability due to excessive exogenous noises. The general
applicability of the current solutions is hampered by the ad hoc nature of the approaches and the
lack of a coherent theoretical framework.
The new SciML methods developed under this project are adressing key challenges of complex systems: 
model construction, uncertainty quantification, decision and control,
and continual learning. 

The research in this project is conducted by researchers from Oak Ridge National Laboratory; 
Pacific Northwest National Laboratory; the University of California, Santa Barbara; and
Arizona State University. 


## Safe Data-driven Control

Under this project our team has developed a range of provably safe data-driven control methods
based on differentiable programming paradigm. 
The developed methods can be used in conjunction with any learning-based controller, 
such as deep reinforcement learning control policy.
In our case we have focused on the extensions of promissing offline model-based 
policy optimization approach called 
[differentiable predictive control](https://www.sciencedirect.com/science/article/pii/S0959152422000981) (DPC).

DPC is a modern SciML method that bring the benefits of both worlds.
It combines model-based interpretability, constraints handling, and performance guarantees of 
[model predictive control](https://en.wikipedia.org/wiki/Model_predictive_control) (MPC)
with [deep reinforcement learning](https://en.wikipedia.org/wiki/Deep_reinforcement_learning) 
(RL) policy optimization.
This synnergy allows DPC to learn control policy parameters directly by
backpropagating MPC objective function and constraints through the differentiable
 model of a dynamical system. Instances of a differentiable model can include 
a family of physics-based and data-driven 
differential equations models, such as  [neural ODEs](https://arxiv.org/abs/1806.07366), 
[universal differential equations (UDEs)](https://arxiv.org/abs/2001.04385), 
or [neural state space models (SSMs)](https://ieeexplore.ieee.org/abstract/document/9482930).



[**Neural Lyapunov Differentiable Predictive Control**](https://ieeexplore.ieee.org/abstract/document/9992386) 
combines the principles of Lyapunov functions, model predictive control, 
reinforcement learning, and differentiable programming to offer a 
systematic way for offline model-based policy 
optimization with guaranteed stability.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Lyap_DPC_method.png" title="DPC Lyap" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Conceptual methodology of the neural Lyapunov differentiable predictive control. 
Simulation of the differentiable constrained closed-loop system dynamics with neural Lyapunov function 
in the forward pass is followed by backward pass computing direct policy gradients for policy optimization.
</div>


[**Differentiable Predictive Control with Safety Guarantees: A Control Barrier Function Approach**](https://ieeexplore.ieee.org/abstract/document/9993146) 
combines the principles of control barrier functions, model predictive control, 
reinforcement learning, and differentiable programming to offer a 
systematic way for offline model-based policy 
optimization with guaranteed constraints satisfaction via projections onto the feasible set.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Barrier_DPC_method.png" title="DPC barrier" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Conceptual methodology of the neural Lyapunov differentiable predictive control. 
Simulation of the differentiable constrained closed-loop system dynamics with neural Lyapunov function 
in the forward pass is followed by backward pass computing direct policy gradients for policy optimization.
</div>



## Stability analysis of deep neural models


In recent years, deep neural networks (DNN) have become
ever more integrated into safety-critical and high-performance
systems, including robotics, autonomous driving, and process control, where formal verification methods are desired
to ensure safe operation.
Stability is one of the properties of dynamical systems with paramount importance for
safety-verified control systems applications.
To address these issues we provided sufficient conditions for 
i) [dissipativity](https://ieeexplore.ieee.org/abstract/document/9809789) 
and ii) [stochastic stability](https://proceedings.neurips.cc/paper/2021/hash/c9dd73f5cb96486f5e1e0680e841a550-Abstract.html) 
of discrete-time dynamical systems  parametrized  by DNNs. 
To do so we leverage the representation of neural networks as pointwise affine maps, 
thus exposing their local linear operators and making them accessible to classical system analytic and design methods. 
This allows us to “crack open the black box” of the neural dynamical system’s behavior. 
We make connections between the spectral properties of neural network's weights and 
different types of used activation function on the stability and overall dynamic behavior of these type of models.
Based on the theory, we propose a few practical methods for designing constrained neural dynamical models with guaranteed stability. 

**Dissipative neural dynamical systems:** 
For more information read the [paper](https://ieeexplore.ieee.org/abstract/document/9809789) 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DNN_stability.PNG" title="DNN" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Phase portraits of deep neural dynamical system models with different stability properties and their associated 
eigenvalue spectra.    Colors represent different initial conditions.
</div>

**Stable deep markov models:** 
For more information read the [paper](https://proceedings.neurips.cc/paper/2021/hash/c9dd73f5cb96486f5e1e0680e841a550-Abstract.html).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DMM_stability.PNG" title="DMM" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Phase portraits of stochastic neural dynamical system models with different stochastic stability properties.
    Thin lines are samples of the stochastic
dynamics with bold lines representing mean trajectories. Colors represent different initial conditions.
</div>



## Open-source Software 

The technology developed under this project is being open-sourced 
as part of the Neuromancer Scientific Machine Learning (SciML) library developed by our team at PNNL.

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=pnnl&repo=neuromancer)](https://github.com/pnnl/neuromancer)


## PNNL Team
- [Mahantesh Halappanavar](https://www.pnnl.gov/people/mahantesh-halappanavar) (PI)
- **Ján Drgoňa** (Task lead)
- [Wenceslao Shaw Cortez](https://shawcortez.wordpress.com/)
- [Sayak Mukherjee](https://energyenvironment.pnnl.gov/staff/staff_info.asp?staff_num=3815)
- [Sam Chatterjee](https://www.pnnl.gov/people/sam-chatterjee)
- [Vikas Chandan](https://www.linkedin.com/in/vikas-chandan-a0624221/)


## Acknowledgements
This project was supported through the U.S. Department of Energy (DOE), 
through the Office of Advanced Scientific Computing Research's 
“Data-Driven Decision Control for Complex Systems (DnC2S)” project.
PNNL is a multi-program national laboratory operated for the U.S. DOE
by Battelle Memorial Institute under Contract No. DE-AC05-76RL0-1830.
