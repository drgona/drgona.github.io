---
layout: page
title: SciML for robotics
description: Developing Scientific Machine Learning (SciML) methods for robotics applications.
img: assets/img/iver_DPC1.png
importance: 3
category: applications
related_publications: CORTEZ2023228, DRGONA202280
---


## Abstract 

In this project we developed a range of scientific machine learning (SciML) 
methods for data-driven surrogate modeling and control of robotics platforms with embedded HW devices.
Specifically, we employ [differentiable programming](https://en.wikipedia.org/wiki/Differentiable_programming)
that allow us to systematically combine physics-based models with black-box function approximators
to obtain physics-informed dynamical system models of complex robotics platforms. 
The differentiability of such models allows us to use them in 
[differentiable predictive control](https://www.sciencedirect.com/science/article/pii/S0959152422000981) (DPC)
method developed by our team. In DPC, we leverage the system dynamics surrogates 
as generative models to train neural control policies in closed-loop simulations.
This offline model-based policy optimization approach is inspired by traditional 
[model predictive control](https://en.wikipedia.org/wiki/Model_predictive_control) (MPC)
and allows for systematic handling of state and input constraints for guaranteed performance and safety.
For the implementation of these methods, we leverage our Pytorch-based SciML library Neuromancer developed by our team at PNNL.
For more details, see the [associated project](https://drgona.github.io/projects/1_project/).

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=pnnl&repo=neuromancer)](https://github.com/pnnl/neuromancer)



## Differentiable predictive control deployment on embedded HW devices 

**Method:**  We are concerned with the problem of deploying complex nonlinear control
policies on HW devices with limited computational and memory resources.
To address this issue, we present DPC as a deep learning-based alternative to the 
[explicit MPC](https://link.springer.com/referenceworkentry/10.1007/978-1-4471-5102-9_10-1). 
In DPC, we trained a neural state-space model from time-series measurements of the real system
and used it to train the neural control policy via stochastic gradient descent by differentiating the MPC loss function 
through the closed-loop system dynamics model. 
 The DPC method learns model-based control policies with state and input constraints, 
while supporting time-varying references and constraints. 


**Embedded HW deployment:** In this project, we collaborated with a team at the 
[Slovak University of Technology, in Bratislava](https://www.uiam.sk/), who deployed the trained SciML models
and DPC policies on embedded HW platform.
Specifically, we demonstrated sim2real transfer and deploy the trained policy 
on a [Raspberry-Pi platform](https://en.wikipedia.org/wiki/Raspberry_Pi). 
We experimentally demonstrate that it is possible to train constrained control policies 
purely based on the measurements of the unknown nonlinear system. 
We compare the control performance of the DPC method against explicit MPC and report efficiency gains 
in online computational demands, memory requirements, policy complexity, and construction time. 
For more details, see our [paper](https://www.sciencedirect.com/science/article/pii/S0959152422000981).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DPC_raspberry.png" title="DPC HW" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    DPC method: From real system measurements to surrogate neural state space model (SSM) of the system dynamics to
    offline model-based control policy to deployment on embedded HW device.
</div>


**Team:**  
- **Ján Drgoňa** 
- [Karol Kiš](https://www.linkedin.com/in/karol-kis-kk1/) (STU, Bratislava)
- [Aaron Tuor](https://www.linkedin.com/in/aarontuor/)
- [Draguna Vrabie](https://www.pnnl.gov/people/draguna-vrabie-phd) 
- [Martin Klauco](https://www.linkedin.com/in/mklauco/?originalSubdomain=sk) (STU, Bratislava)



## Differentiable programming for modeling autonomous underwater vehicles

**Method:** Conventional physics-based modeling is a time-consuming bottleneck in control design 
for complex nonlinear systems like [autonomous underwater vehicles](https://oceanexplorer.noaa.gov/facts/auv.html) (AUVs).
 In contrast, purely data-driven models require a large number of observations and lack operational guarantees 
for safety-critical systems. SciML models leveraging prior knowledge of the system dynamics have potential 
to provide reliable models in a typical data-limited scenario for high value complex systems, 
thereby avoiding months of expensive expert modeling time. 
In this work, present control-oriented parametric SciML models with varying levels of domain-awareness 
that exploit known system structure and prior physics knowledge to create constrained deep neural dynamical system models. 
We employ [universal differential equations](https://arxiv.org/abs/2001.04385) (UDEs) 
to construct data-driven control-oriented blackbox and graybox representations of the AUV dynamics. 
For more details, see our [paper](https://www.sciencedirect.com/science/article/pii/S2405896323002276).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Iver_DPC.png" title="iver dpc" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Conceptual methodology of the differentiable programming-based method for end-to-end 
modeling and control of autonomous underwater vehicles.
</div>

**Real-world data:** In this project, we collaborated with 
[University of Washington's Applied Physics Laboratory](https://www.apl.washington.edu/home.php) (UW APL)
team who collected experimental data using their 
[IVER AUV platform](https://www.l3harris.com/all-capabilities/iver-suite-autonomous-undersea-vehicles).
The collected datasets have been used to train and validate the SciML surrogate models 
developed by our team.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/iver_AUV1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/iver_AUV2.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/iver_AUV3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
     Field data collection by the UW APL team using the IVER AUV platform.
</div>


**Team:**  
- [Soumya Vasisht](https://www.linkedin.com/in/m-shapiro/)
- [Wenceslao Shaw Cortez](https://shawcortez.wordpress.com/)
- [Aaron Tuor](https://www.linkedin.com/in/aarontuor/)
- [James Koch](https://www.linkedin.com/in/james-koch-5285a87a/)
- [Draguna Vrabie](https://www.pnnl.gov/people/draguna-vrabie-phd) 
- Peter Brodsky (UW APL)
- Greg Okopal (UW APL)
- Joseph Sammartino (UW APL)
- **Ján Drgoňa** 



## Differentiable predictive control of a quadcopter 

In this project we develop DPC method with safety guarantees to train neural policies to control a 17 dimensional quadcopter system.
The quadrotor has 3 simulations, one differentiable model in PyTorch to allow for DPC policy optimization, 
one in [CasADi](https://web.casadi.org/) to allow for MPC, 
and one in [Mujoco](https://mujoco.org/) to allow for a validation environment.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DPC_mujoco_1.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DPC_mujoco_2.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DPC_mujoco_3.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
     Closed-loop simulation profiles of the DPC policy evaluated under different tasks using Mujoco environment.
</div>


*This is an active project by John Viljoen. Stay tuned for the updates.*


**Team:**  
- [John Viljoen](https://www.linkedin.com/in/john-viljoen-763427150/) (UC Berkeley - Summer internship)
- [Wenceslao Shaw Cortez](https://shawcortez.wordpress.com/)
- [Draguna Vrabie](https://www.pnnl.gov/people/draguna-vrabie-phd) 
- **Ján Drgoňa** 



## Acknowledgements
This research was supported by the Mathematics for Artificial Reasoning in Science (MARS) initiative via 
the Laboratory Directed Research and Development (LDRD) investments at Pacific Northwest National Laboratory (PNNL).
PNNL is a multi-program national laboratory operated for the U.S. Department of Energy (DOE) by 
Battelle Memorial Institute under Contract No. DE-AC05-76RL0-1830.