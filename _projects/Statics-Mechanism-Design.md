---
layout: project
title: Statics Class Machanism Design
description: Designing A Lifting Mechanism
technologies: 
image: /assets/images/Statics-Design.jpg
---

2D Mechanism Design for Maximum Lift

In this project, I was tasked with designing a 2D lifting mechanism within a 150 cm by 50 cm design space using three pin supports, a rigid bar of chosen length, and a linear actuator selected from an online catalog. The objective was to develop a rigid-frame mechanism capable of lifting the maximum possible load to the highest possible height while respecting geometric and force limitations.

This problem required a blend of mechanical design, kinematic analysis, and structural reasoning. Key skills included:

Mechanism design and geometry optimization to determine bar placement and support configuration.

Statics and force analysis to ensure the system could handle maximum actuator loads efficiently.

CAD modeling and simulation to visualize motion and validate mechanical feasibility.

Engineering judgment in balancing lift height, force amplification, and structural stability.

Through this project, I strengthened my ability to translate abstract design constraints into a physically realizable and efficient lifting mechanism.

To complete this problem, I used the following design choices:

  - Design Space 50x150cm
  - Bar Length 120cm
  - Actuator max force 294kN
  - Actuator pinned 80cm from pivot and makes 60º angle with bar
  - Load is applied at the free end of the bar

Problem Solution Considering the Bar to be Rigid:

d_act = distance from pivot to actuator

d_load = distance from pivot to applied load

Moment about pivot = 0 = F_actuator(d_act)(sin(theta)) - W(d_load)

W_max = (F_actuator(d_act)(sin(theta)))/(d_load)

(Photo won't load for some reason - I drew the forces and dimensions)
![Portfolio](/KevinPezzulich/assets/images/SAP.jpg)

Answer: W_max = 170kN @ theta = 60º

Problem Solution Considering the Bar No Longer Rigid:

Goal: Select a beam design that is best for this situation.

Maximum Deflection of 2% of bar length: 2.4cm

For the flexible-beam analysis, I model the 120 cm bar as a cantilever beam fixed at the ground pin at (150 cm, 0). The maximum lifting scenario from Step 1 applies a vertical load at the free end of the beam equal to the maximum lifted weight, 𝑊max=170 kN. This produces the greatest deflection and bending moment. The actuator force acts closer to the support, so its contribution to deflection is smaller and can be neglected for the critical deflection case. The beam is assumed to be prismatic, linearly elastic, and made of structural steel unless otherwise stated.

M_max = W_max(d_load)+(F_act)(sin(60))(d_act) = 407 kN m

Using F_yield_steel = 355MPa and a FOS of 1.5, 355/1.5 = 237MPa

S_required = M_max/Stress_allowed = 407kNm/237MPa = 0.00172m^3 = 1.72(10)^6 mm^3

Deflection_max = 0.024 = (W)(d_load)^3/(3EI) + (F_act)(sin(60))(d_act)^2(3(d_load)-d_act)/(6EI)

I_required = 2(10)^-5 m^4 = 2(10)^7 mm^4

So, I_x must be greater than or equal to 2(10)^7 mm^4

Looking at table: W460x158 best fits the situation, as it is under the height requirement and strong enough, and is the lightest/least expensive option to do so.
(This photo won't load either - I drew the bar's FBD)
![Portfolio](/KevinPezzulich/assets/images/SPA2.jpg)

