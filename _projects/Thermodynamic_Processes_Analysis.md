---
layout: project
title: Analysis of System
description: Class project with calculations and diagrams
technologies: System Analysis
image: /assets/images/Dual-stage-turbocharging-system.png
---

QUALITATIVE DESCRIPTION:

This system is used in internal combustion engine applications to increase power output without increasing engine size. It operates by recovering energy from the engine’s exhaust gases and converting it into useful shaft work through a two-stage turbocharging system. The exhaust gases expand through a high-pressure and low-pressure turbine, and the work produced by these turbines drives corresponding compressors on the intake side.

Ambient intake air is first compressed by the low-pressure compressor and then further compressed by the high-pressure compressor, increasing its pressure and temperature. The compressed air then passes through an intercooler, where heat is rejected to the surroundings at approximately constant pressure. This cooling increases the air density, allowing a greater mass of oxygen to enter the combustion chamber for a given volumetric flow rate.

The increased oxygen availability enables additional fuel to be combusted, resulting in greater engine power output. Importantly, this enhancement is achieved by utilizing energy that would otherwise be wasted in the exhaust stream, improving overall engine performance and power density without a proportional increase in engine mass or displacement. This makes multi-stage turbocharging with intercooling an effective strategy for engine downsizing while maintaining high performance.

Overall, this is a particularly interesting and helpful application of thermodynamic processes, as it enables combustion engines to gain far more power with just a relatively minor weight addition. This system is an exeptional example of how the devices we learned about in Thermodynamics fit real-world scenarios.

Here is a system diagram - note, this does not include the Wout from the engine, largly because while this is the most important metric, it also wouldn't take into consideration the chemical potential energy added through the influx of fuel:

---
![Two-stage turbocharging system diagram](/assets/images/Thermo-Portfolio-Assgnmnt.jpg)
---

Here are some relevant equations which capture the relevant thermodynamic processes that are undergone by the mass within the control volume "CV" system:

Firstly, the LP compressor Mdot-in = Mdot-out, with its energy balance Wdot-in,LP = Mdot(h2,LP - h1). For an ideal gas, which we model air as, h = CpT, so Wdot-in,LP = MdotCp(T2,LP - T1). Isentropic efficiency = (T2s,LP - T1)/(T2,LP - T1).

Then, this is fed into the HP compressor, which has a very similar role, and thus acts similarly to the Low-Pressure compressor. Mdot-in = Mdot-out, with its energy balance Wdot-in,HP = Mdot(h3,HP - h2,LP). Again, h = CpT, so Wdot-in,HP = MdotCp(T3,HP - T2,LP).
While these compressors act essentially in separate systems, since their Work input comes as a result of the turbine they are directly connected to, the overall Work input to the gas can be represented as Wdot-total = Wdot-in,LP + Wdot-in,HP. Overall, as I discussed earleir, these compressor-sides of the turbochargers are what is responsible for adding pressure to the system and thus forcing more air into the combustion chamber.

Next, the intercooler acts to cool and condense this air, further allowing more of it to be packed into each combustion stroke. It also has mass balance Mdot-in = Mdot-out, as well as Qdot-out = MdotCp(T3,HP-T4). Notably, this component in a non-reversible process would have entropy generation Sdot-gen = Mdot(s4-s3,HP)-(Qdot-out/T-boundary), which represents the real world irreversibilty due to finite temperature differences.

Here, the air finally flows into the combustion cylinder, where, thanks to the combination of the turbos and the intercooler, it is far more dense than what is considered a "naturally aspirated" system, where the engine intakes air directly from the atmosphere without additional devices. Mdot-exhaust = Mdot-airin + Mdot-fuelin. Additionally Wdot-out = Qdotin (from the energy of the fuel through combustion) - Mdot-exhaust(h-out - h-in). This exhaust enthalpy will go on to power the turbines in the next step, whose Work powers the compressors in the initial steps of the system.

For the High_Pressure "HP" Turbine, Mdot-in = Mdot-out. Wdot-out,HP = Mdot(h5-h6) = MdotCp(T5-T6). The isentropic efficiency of this turbine = (T5 - T6)/(5 - T6s). This turbine work output is the same work input to the HP compressor, as while I drew them far apart in my system diagram for simplicity of analysis, this tubine is actually comprised in one small turbocharger, and thus is close and shares the same shaft as the HP compressor.

For the Low_Pressure "LP" Turbine, it has a similar relationship with the LP compressor, and shares the same energy and mass equations. Mdot-in = Mdot-out. Wdot-out,LP = Mdot(h6-h7) = MdotCp(T6-T7).

Ultimately, a key detail of this system is that Wdot-out, LP + Wdot-out, HP = Wdot-in, LP + Wdot-in, HP, thanks to the shared shafts between the compressors and the turbines.

Some key details of this system that define the performance metrics are the Pressure Ratio = P-intake / P-ambient. This is the key metric which represents the overall main goal of the dual-turbocharger setup: Higher intake Pressure to produce more engine power!

To assess the irreversibility and thermodynamic performance of the two-stage turbocharging system, the second law of thermodynamics is applied to each major control volume. For a steady-state control volume, the entropy balance is given by

0 = ∑𝑄/𝑇𝑏 + ∑𝑚-𝑖𝑛*𝑠-𝑖𝑛 - ∑𝑚-𝑜𝑢𝑡*𝑠-𝑜𝑢𝑡 + 𝑆𝑔𝑒𝑛

Here, 𝑄 represents heat transfer across the control-volume boundary at boundary temperature 𝑇𝑏, s is the specific entropy of the working fluid, and 𝑆𝑔𝑒𝑛​ is the rate of entropy generation due to irreversibilities.

For the compressors (low-pressure and high-pressure), the processes are modeled as adiabatic with work input from the turbine shafts. Under this assumption, heat transfer is negligible, and entropy generation arises primarily from internal irreversibilities such as fluid friction and non-isentropic compression. As a result, the entropy balance reduces to

Sgen,comp​ = Mdot(sout​−sin​) > 0​

indicating that entropy increases across each compression stage.

For the turbines, exhaust gases expand and perform work to drive the compressors. Although these processes are also commonly approximated as adiabatic, entropy generation still occurs due to irreversibilities associated with viscous dissipation and non-ideal flow. Thus, the turbine entropy balance similarly satisfies

indicating that entropy increases across each compression stage.

For the turbines, exhaust gases expand and perform work to drive the compressors. Although these processes are also commonly approximated as adiabatic, entropy generation still occurs due to irreversibilities associated with viscous dissipation and non-ideal flow. Thus, the turbine entropy balance similarly satisfies

Sgen,turb ​= Mdot(sout​−sin​) > 0

Finally, for the intercooler, heat is rejected from the compressed intake air to the surroundings. In this control volume, both mass flow and heat transfer terms contribute to the entropy balance. The presence of heat transfer across a finite temperature difference between the compressed air and the ambient environment ensures positive entropy generation, consistent with the second law.

Overall, the total entropy generation of the system is positive, confirming that the turbocharging process is irreversible. However, by recovering energy from the exhaust stream and reducing intake-air temperature through intercooling, the system improves engine performance while remaining fully consistent with the second law of thermodynamics.

HOW MIGHT THIS SYSTEM BE MODIFIED TO AFFECT PERFORMANCE?

One notable way this system could be modified is to improve the intercooler so that it removes more heat energy Qout from the system. This could be accomplished in numerous ways. Most simply, with colder ambient temperatures, the temperature of cold air flowing through the intercooler would be colder, thus removing more heat from the high-pressure air within the system. Additionally, it could be made more effective by increasing the surface area of outside air it is exposed to, as this would also allow it to remove more heat from the system. This would have a significant influence on the density of air, as it would become more dense, a key factor which would allow for more air and thus more oxygen to enter the combustion chamber, leading to more power.​

