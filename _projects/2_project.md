---
layout: page
title: SciML for buildings
description: Developing differentiable predictive control (DPC) as a market-ready technology for energy-efficient building control.
img: assets/img/DPC_BTO_project.PNG
importance: 1
category: applications
related_publications: DRGONA202114, drgona2022learning, DRGONA2021110992, DRGONA202280, DrgonaDSCC2020, DRGONA2020190,
 NAGY2023110435, DONG2022109195, 10155901, 10156081, das2022machine, das2022machine, Blum2021, bs2021_30806
---


## Abstract 
At PNNL, I have led the development and demonstration of 
[differentiable predictive control (DPC)](https://www.sciencedirect.com/science/article/pii/S0959152422000981), a state-of-the-art advanced control method,
that enables rapid design and scalable deployment of predictive controls for
building energy systems. DPC provides benefits of 
[model predictive control](https://en.wikipedia.org/wiki/Model_predictive_control) 
(MPC) at costs and complexity
of traditional controls allowing for improved control and predictions which result in reduced energy use,
demand flexibility and improved air quality. 
Under this project, my PNNL team collaborates with industry partners to integrate
DPC with existing market-available control products to develop affordable, high-performance, and scalable
predictive control solutions that can be deployed in new and existing buildings to reduce energy, peak demand,
greenhouse gas emissions, and improve occupant comfort. The project will demonstrate the DPC
technology’s flexibility in design and deployment to industry use cases and underlying building energy
systems without substantial, bespoke rework. This applied research is directed by industry objectives to bring to the
market this new capability, and enable its broad deployment. The resulting buildings control technologies and
deployment enabling software will significantly advance BTO’s goals to reduce emissions in US buildings.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DPC_BTO_project.PNG" title="DPC BTO" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Overview of Differentiable Predictive Control (DPC) methodology for real-world building control.
</div>



### Modeling building thermal dynamics

Energy-efficient buildings are one of the top priorities to sustainably address the global energy demands and reduction 
of the CO2 emissions. It has been demonstrated that advanced building control, 
like [model predictive control](https://en.wikipedia.org/wiki/Model_predictive_control) (MPC) 
or [deep reinforcement learning](https://en.wikipedia.org/wiki/Deep_reinforcement_learning) (DRL), 
can notably reduce the energy use and mitigate greenhouse gas emissions. 
However, in order for these advanced control methods to work in practice, they heavily rely on accurate 
prediction models of building thermal dynamics.

To address this, our team has developed a family of control-oriented 
physics-constrained deep learning models of building thermal dynamics. 
Specifically, our method incorporates structural prior knowledge from traditional physics-based building modeling 
into the architecture of the deep neural network model. Further, we also use penalty methods to enforce 
inequality constraints, thereby bounding predictions within physically realistic and safe operating ranges. 
We show that using only 10 days’ measurements for training, our method is capable of generalizing over 
20 consecutive days. We demonstrate that the proposed modeling methodology is achieving state-of-the-art 
performance by significantly improving the accuracy and generalization compared to classical system identification 
methods and prior advanced methods reported in the literature. compared to prior state-of-the-art 
methods reported in the literature.
For more information read [our paper](https://www.sciencedirect.com/science/article/pii/S0378778821002760).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/NSSM_building.jpg" title="nssm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Generic structure of physics-inspired neural dynamics model architecture. Weights of individual neural blocks 
 are parametrized by linear maps with constrained eigenvalues to enforce the energy dissipativity property of the modeled system.
</div>



### Differentiable predictive control of building energy systems

Despite intensive research efforts, the practical applications 
of advanced control methods such as MPC and DRL are still in the early stages. 
One of these challenges is the complexity of designing and deploying the optimal control policies 
in the current predominantly rule-based building automation systems.

To address this limitation, our team has developed novel methodology 
called [differentiable predictive control (DPC)](https://www.sciencedirect.com/science/article/pii/S0959152422000981) 
for learning constrained control 
policies for dynamical systems subject to operational and safety constraints.
DPC presents a novel data-driven policy optimization algorithm that combines the benefits of 
both worlds, data-driven adaptive nature of DRL, and model-based performance and safety guarantees of MPC.
We have demonstrated the proposed DPC method in a high fidelity simulation environment 
using learned model of multi-zone building thermal dynamics.
For more information read [our paper](https://www.sciencedirect.com/science/article/pii/S2405896321012933).


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DPC_building.png" title="dpc building" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   Conceptual overview of Differentiable Predictive Control (DPC) methodology for buidling control. 
Step 1: physics-constrained system identification of the building thermal dynamics.  
Step 2: Learning neural control policies in closed-loop simulations with differentiable system dynamics model and MPC constraints.
</div>



### High fidelity simulation platform of building energy system

Development of new building HVAC control algorithms has grown due to needs for energy efficiency and operational flexibility. 
However, case studies demonstrating new algorithms are largely individualized, making algorithm performance difficult 
to compare directly. In addition, the effort and expertise required to implement case studies in real or simulated buildings 
limits rapid prototyping potential. 
To address this issue, our team has been co-developing a high fidelity building simulation framework for performance benchmarking
of modern control methods. This multi-institution project called  Building Optimization Testing Framework (BOPTEST)
was recognized with the [best paper award](https://www.tandfonline.com/doi/full/10.1080/19401493.2021.1986574)
issued by the Journal of Building Performance Simulation.
For more information visit the [project website](https://ibpsa.github.io/project1-boptest/).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/BOPTEST.PNG" title="boptest" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Conceptual overview of the BOPTEST framework designed to facilitate the performance evaluation and benchmarking 
of advanced building control strategies.
</div>



## Open-source Software 

The technology developed under this project is being open-sourced 
as part of the Neuromancer Scientific Machine Learning (SciML) library developed by our team at PNNL.

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=pnnl&repo=neuromancer)](https://github.com/pnnl/neuromancer)


## PNNL Team
- [Draguna Vrabie](https://www.pnnl.gov/people/draguna-vrabie-phd) (PI)
- **Ján Drgoňa** (Co-PI)
- [Aaron Tuor](https://www.linkedin.com/in/aarontuor/) (Co-PI)
- [James Koch](https://www.linkedin.com/in/james-koch-5285a87a/)
- [Madelyn Shapiro](https://www.linkedin.com/in/m-shapiro/)
- [Wenceslao Shaw Cortez](https://shawcortez.wordpress.com/)
- [Soumya Vasisht](https://www.linkedin.com/in/m-shapiro/)
- [Rahul Birmiwal](https://www.linkedin.com/in/rahul-birmiwal009/)
- [Himanshu Sharma](https://www.linkedin.com/in/hsharma2328/)
- [Brian Hutchinson](https://www.linkedin.com/in/brian-hutchinson-7a8b0857/) (WWU Professor)
- [Seth Briney](https://www.linkedin.com/in/sethlbriney/) (WWU student)
- [Diego Llanes](https://www.linkedin.com/in/diego-llanes-ai/) (WWU student)
- [Harry Qiang](https://www.linkedin.com/in/harry-qiang-23417151/) (WWU student)


## Industrial Partners
- [Community Energy Labs](https://communityenergylabs.com/)
- [Verdigris](https://verdigris.co/)
- [Elexity](https://www.elexity.io/)
- [Delta Controls](https://deltacontrols.com/)
- [PassiveLogic](https://passivelogic.com/)


## Acknowledgements
This project is supported through the U.S. Department of Energy (DOE),
Energy Efficiency and Renewable Energy, Building Technologies Office (BTO) under the 
“Advancing Market-Ready Building Energy Management by Cost-Effective Differentiable Predictive Control” 
and the “Dynamic decarbonization through autonomous physics-centric deep learning and optimization of building operations” projects. 
 PNNL is a multi-program national laboratory operated for the U.S. Department of Energy (DOE) 
by Battelle Memorial Institute under Contract No. DE-AC05-76RL0-1830.

Part of this work emerged from the IBPSA Project 1, an international project conducted under the umbrella 
of the International Building Performance Simulation Association (IBPSA). 
Project 1 develops and demonstrates a BIM/GIS and Modelica Framework for building and 
community energy system design and operation. This research was partially supported by 
the Assistant Secretary for Energy Efficiency and Renewable Energy, Office of Building Technologies of the U.S. 
Department of Energy, under Contracts nos. DE-AC05-76RL01830, and DE-AC02-05CH11231.

