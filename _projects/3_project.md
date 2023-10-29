---
layout: page
title: Neuromancer SciML library 
description: Developing novel scientific machine learning (SciML) methods and user-friendly software library in Pytorch.
img: assets/img/Neuromancer.png
importance: 1
category: work
related_publications: 10253098, Shimiao2023, Legaard2023, KochChaos2023, li2023homotopy, 
  9809789, 9867379, 9867586, skomski21a, SkomskiACC2021, drgona2022learning, tuor2020constrained
---



## Abstract 

Recent research has demonstrated great advantages to integrating physical knowledge into machine learning methods, 
and conversely data-driven modeling into traditional physics-based scientific computing. 
However, the underlying compute infrastructure in the form of both hardware and software has diverged 
considerably from the need for integrated approaches to scientific discovery. 
The current misalignment of these sets of tools has led to some very inefficient scientific workflows 
involving running computations on different systems, transposition of data between formats and expensive 
data copies (in both time and space). As well, the lack of tight integration, directly results in slower 
computations and methodological limitations (e.g. impractical to solve end-to-end optimization problems across 
scientific computing and machine learning codes). 

To adress these issues, this project developed novel
principled [scientific machine learning](https://sites.brown.edu/bergen-lab/research/what-is-sciml/) 
(SciML) methods and software tools. 
Specifically, under this project our team at PNNL 
has developed [NeuroMANCER SciML library in Pytorch](https://github.com/pnnl/neuromancer).

## Open-source Software 

**Neural Modules with Adaptive Nonlinear Constraints and Efficient Regularizations (NeuroMANCER)**
is an open-source differentiable programming (DP) library for solving parametric constrained optimization problems, 
physics-informed system identification, and parametric model-based optimal control.
NeuroMANCER is written in [PyTorch](https://pytorch.org/) and allows for systematic 
integration of machine learning with scientific computing for creating end-to-end 
differentiable models and algorithms embedded with prior knowledge and physics.

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=pnnl&repo=neuromancer)](https://github.com/pnnl/neuromancer)



## SciML Methods in Neuromancer


#### Learning to optimize (L2O) for constrained optimization

Learning Solutions to Constrained Optimization Problems
is a set of methods that use machine learning to learn the  
solutions (explicit solvers) to optimization problems. 
Constrained optimization problems where the solution x depends on the varying problem parameters ξ are
called [parametric programming problems](https://en.wikipedia.org/wiki/Parametric_programming).
Neuromancer allows you to formulate and solve a broad class of parametric optimization problems 
via the [Differentiable Programming (DP)](https://en.wikipedia.org/wiki/Differentiable_programming) paradigm.
Hence, we call the approach **Differentiable Programming Programming (DPP)**.
Specifically, Neuromancer allows you to use 
automatic differentiation (AD) in PyTorch to compute the sensitivities of 
such constrained optimization problems w.r.t. their parameters. 
This allows you to leverage gradient-based optimizers (e.g., stochastic gradient descent)
to obtain approximate solutions to constrained parametric programming problems via for semi-supervised offline learning. 
The main advantage of this offline DPP-based solution compared to classical optimization solvers (e.g., IPOPT) 
is faster online evaluation, often obtaining orders of magnitude speedups.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Rosenbrock_sensitivity.gif" title="rosenbrock" class="img-fluid rounded z-depth-1" %}
    </div>
</div>



For more information see the [open-source examples](https://github.com/pnnl/neuromancer/tree/master/examples/parametric_programming).


#### Learning SciML surrogates for dynamical systems

[**System identification**](https://en.wikipedia.org/wiki/System_identification) is using statistical methods 
to construct mathematical models of dynamical systems given the measured observations of the system behavior.
In the Neuromancer library, we are primarily interested in differentiable system 
ID methods that can incorporate prior physical knowledge into their architectures and loss functions. Examples include
structural assumption on the computational graph inspired by domain application, structure of the weight
matrices, or network architectures. Differentiaity allows us to 
leverage gradient-based optimization algorithms for learning the
unknown parameters of these structured digital twin models from observational data of the real system.

Neuromancer currently supports the following system identification methods:
+ [Neural ordinary differential equations (NODEs)](https://arxiv.org/abs/1806.07366)
+ [Neural state space models (NSSMs)](https://arxiv.org/abs/2011.13497)
+ [Universal differential equations (UDEs)](https://arxiv.org/abs/2001.04385)


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/NODE.png" title="node" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

For more information see the [open-source examples](https://github.com/pnnl/neuromancer/tree/master/examples/ODEs)

#### Learning to control with differentiable programming

[**Differentiable predictive control (DPC)** method](https://arxiv.org/abs/2004.11184) represents a 
flagship capability of the Neuromancer library.

DPC allows us to learn control policy parameters directly by
backpropagating model predictive control (MPC) objective function and constraints through the differentiable
 model of a dynamical system. Instances of a differentiable model include ordinary
differential equations (ODEs), including  [neural ODEs](https://arxiv.org/abs/1806.07366), 
[universal differential equations (UDEs)](https://arxiv.org/abs/2001.04385), 
or [neural state space models (SSMs)](https://ieeexplore.ieee.org/abstract/document/9482930).

The conceptual methodology shown in the figures below consists of two main steps.
In the first step, we perform system identification by learning the unknown parameters   of differentiable digital twins.
In the second step, we close the loop by combining the digital twin models with control policy, 
parametrized by neural networks, obtaining a differentiable closed-loop dynamics model.
This closed-loop model now allow us to use automatic differentiation (AD) 
to solve the parametric optimal control problem by computing the sensitivities 
of objective functions and constraints to changing problem parameters such as initial conditions, 
boundary conditions, and parametric control tasks such as time-varying reference tracking.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DPC_abstract.png" title="DPC" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


For more information see the [open-source examples](https://github.com/pnnl/neuromancer/tree/master/examples/control)



## PNNL Team
- **Ján Drgoňa** (PI)
- [Aaron Tuor](https://www.linkedin.com/in/aarontuor/) (Co-PI)
- [James Koch](https://www.linkedin.com/in/james-koch-5285a87a/)
- [Draguna Vrabie](https://www.pnnl.gov/people/draguna-vrabie-phd) 
- [Madelyn Shapiro](https://www.linkedin.com/in/m-shapiro/)
- Ethan King
- [Stefan Dernbach](https://www.linkedin.com/in/sdernbach/)
- Zhao Chen
- [Shrirang Abhyankar](https://www.linkedin.com/in/shrirang-abhyankar-59018144/)
- [Robert Cameron Rutherford](https://www.linkedin.com/in/robert-c-rutherford/)
- Mia Skomski
- [Difan (张迪凡) Zhang](https://www.linkedin.com/in/difan-zhang-32a167163/)
- [Rafsan Rabbi](https://www.linkedin.com/in/rafsanrabbi/) (Summer internship)
- [Ethan Herron](https://www.linkedin.com/in/ethan-herron-9218a1171/) (Summer internship)
- [Christian Møldrup Legaard](https://www.linkedin.com/in/christian-moeldrup-legaard/?originalSubdomain=dk) (Summer internship)
- [Shimiao Li](https://www.linkedin.com/in/shimiao-li-305512226/) (Summer internship)
- [Bo Tang](https://www.linkedin.com/in/lucas-bo-tang/) (Summer internship)
- [James Kotary](https://j-kota.github.io/) (Summer internship)





## Acknowledgements
This research was partially supported by the Mathematics for Artificial Reasoning in Science (MARS) 
and Data Model Convergence (DMC) initiatives via 
the Laboratory Directed Research and Development (LDRD) investments at Pacific Northwest National Laboratory (PNNL).
PNNL is a multi-program national laboratory operated for the U.S. Department of Energy (DOE) by 
Battelle Memorial Institute under Contract No. DE-AC05-76RL0-1830.