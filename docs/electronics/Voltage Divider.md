# Building a Voltage Divider Unit (VDU)
This guide will walk you through bulding a VDU.

> [!WARNING]
> Nearly all Bots have no use for a VDU. The only reason to make one is for voltage telemetry with a modified IA6B.
>
> This guide is meant for experienced builders.
>
> - Advanced PCB soldering is required for the modification
> 
> - Building the VDU requires knowledge of RC circuits. 
>
> - An I6X with OpenI6X is required to get correct telemetry.
>
> **I cannot feasibly teach all of those skills in this guide.**

> [!TIP]
> [This video](https://www.youtube.com/watch?v=degbF-1VqIE) is a fantastic resource that goes over modifying the IA6B for voltage telemetry.
>
> A guide on the I6X with OpenI6X is on my To-Do list. I'll get that together soon enough. 

## Parts and Tools
The same tools that were used to make the wiring harness will be used. 

You will also need a protoboard, resistors, and capacitors. 

## Designing the VDU

A VDU, or Voltage Divider Unit, steps down the voltage coming from your battery to make it safe to use for telemetry. This unit is made up of two resistors and one capacitor. 

> [!CAUTION]
> There are no universal VDU values. What works for me may not work for you.

**The Goal: Get the output down below 3V with a fully charged battery.**

### Circuit Diagram

<img src="/media/vdu.png?raw=true" alt="Circuit Diagram" width=50%>

### The formulae

$\Delta V_{out} =  \frac{\mathcal{E}R_1}{R_1+R_2}$

> [!TIP]
> $\mathcal{E}$, or emf, is the voltage of your battery.
>
> Why not $\Delta V_{bat}$? $\Delta V_{bat}$ refers to a battery under load. Using $\Delta V_{bat}$ could lead to a voltage that is too high.

For the capacitor, Your Time Constant should be greater than the average fluctuation period. 

> [!TIP]
> Time Constant = $\tau = RC$. The Time Constant is measured in seconds.




