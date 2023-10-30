---
layout: page
title: SciML for power systems
description: Developing Scientific Machine Learning (SciML) methods for power system applications.
img: assets/img/methodology_DED_DPC.png
importance: 2
category: applications
related_publications: 10253098, Shimiao2023, KochChaos2023, li2023homotopy, 9867379
---


## Abstract 

In this project we developed a range of scientific machine learning (SciML) 
methods for surrogate modeling of electric power system dynamics and decision problems.

**Learning to optimize:** We have investigated the use of [differentiable parametric optimization](https://github.com/pnnl/neuromancer/tree/master/examples/parametric_programming)
also called learning to optimize (L2O) approach to tackle several constrained optimization-based
decision problems in power systems, namely [load modeling of a transmission-distribution network](https://ieeexplore.ieee.org/document/10253098),
and [optimal power flow (OPF) problem](https://openreview.net/forum?id=GdimRqV_S7).


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/imitationVSdpp1.jpg" title="DPP" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Imitation learning VS end-to-end learning using Differentiable Parametric Programming.
</div>


**Learning to control:** 
The dynamics-aware [economic dispatch](https://en.wikipedia.org/wiki/Merit_order) (DED)
is an important problem in power systems that includes
generator dynamics and operational constraints to enable near real-time scheduling of generation 
units in a power network. 
However, the incorporation of differential 
equations that govern the system dynamics makes this optimization problem computationally prohibitive to solve. 
To adress this limitation, we [developed a novel method](https://ieeexplore.ieee.org/abstract/document/9867379) 
to employ the recently proposed 
[differentiable predictive control (DPC)](https://www.sciencedirect.com/science/article/pii/S0959152422000981)
for offline learning of explicit neural control policies using an 
identified Koopman operator (KO) model of the power system dynamics. By doing so, we demonstrate the high solution 
quality and five orders of magnitude computational-time savings of the DPC method over the original online 
optimization-based DED approach.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/methodology_DED_DPC.png" title="DPC DED" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Constructing a surrogate model of generator swing dynamics with a Koopman operator (KO) approach and leveraging 
differentiable predictive control 
to learn a solution map from forecast system loads to a schedule of generation inputs that meets the loads at least cost.
</div>


**Modeling networked dynamical systems:** 
Networked dynamical systems are common in power systems, however, they are notoriously hard to model
with purely data-driven approaches.
In [our work](https://pubs.aip.org/aip/cha/article-abstract/33/2/023103/2875955/Structural-inference-of-networked-dynamical?redirectedFrom=fulltext), 
we seek to infer (i) the intrinsic physics of a base unit of a population, 
(ii) the underlying graphical structure shared between units, and (iii) the coupling physics of a given networked 
dynamical system given observations of nodal states. These tasks are formulated around the notion of the 
[Universal Differential Equation](https://arxiv.org/abs/2001.04385), 
whereby unknown dynamical systems can be approximated with neural networks, 
mathematical terms known a priori (albeit with unknown parameterizations), or combinations of the two. 
We demonstrate the value of these inference tasks by investigating not only future state predictions but 
also the inference of system behavior on varied network topologies. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/UDE_networked.PNG" title="UDE net" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   Conceptual methodology of networked dynamical system modeled via universal differential equations.
 In (a), a small network of unknown oscillators interact according to an adjacency matrix shown in (b).
</div>


**Datasets:** Our team lead by researchers form Carnegie Mellon University (CMU) also 
investigated power [grid behavioral patterns in real-world datasets](https://dl.acm.org/doi/10.1145/3599733.3600257), 
including the time-varying topology, 
 load, and generation, as well as the spatial differences between 
 individual loads and generations. Based on these observations, we evaluated the generalization 
 risks in some existing ML works caused by ignoring these grid-specific patterns in model design and training.


## Open-source Software 

The methods developed under this project is being open-sourced 
as part of the Neuromancer Scientific Machine Learning (SciML) library developed by our team at PNNL.

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=pnnl&repo=neuromancer)](https://github.com/pnnl/neuromancer)


## Acknowledgements
This research was supported by the Data Model Convergence (DMC) initiative via 
the Laboratory Directed Research and Development (LDRD) investments at Pacific Northwest National Laboratory (PNNL).
PNNL is a multi-program national laboratory operated for the U.S. Department of Energy (DOE) by 
Battelle Memorial Institute under Contract No. DE-AC05-76RL0-1830.

## PNNL Team
- **Ján Drgoňa** (PI)
- [Shrirang Abhyankar](https://www.linkedin.com/in/shrirang-abhyankar-59018144/) (Co-PI)
- [Aaron Tuor](https://www.linkedin.com/in/aarontuor/)
- [James Koch](https://www.linkedin.com/in/james-koch-5285a87a/)
- [Draguna Vrabie](https://www.pnnl.gov/people/draguna-vrabie-phd) 
- Ethan King
- [Andrew August](https://www.linkedin.com/in/andrew-august/)
- [Shimiao Li](https://www.linkedin.com/in/shimiao-li-305512226/) (CMU - Summer internship)



