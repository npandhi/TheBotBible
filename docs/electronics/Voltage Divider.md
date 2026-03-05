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

> [!CAUTION]
> This guide involves soldering.
>
> A soldering iron can be extremely dangerous if misused. A soldering iron can get up to 450°C and cause **third-degree burns** in under a second.
>
> I myself have been burned by an iron. It's not fun. But because I followed standard safety procedures, I was okay. 
>
> Always wear safety goggles, use a soldering mat, and use an iron holder.
>
> NEVER leave an iron unattended, hold components being soldered with your hands, leave flammable or explosive items nearby, or touch the iron's tip while it is hot.
>
> If you are burned, run the affected area under cool water for as long as you can. If the burn is large or affects deep skin tissue, seek medical attention.
>
> Keep a fire extinguisher nearby. See Commandment 07.
>
> **Failure to abide to these precautions may result in serious burns or fire.**

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

**The Goal: Get the output down to 3V with a fully charged battery.**

### Circuit Diagram

<img src="/media/vdu.png?raw=true" alt="Circuit Diagram" width=50%>

### The formulae

$\Delta V_{out} = \frac{\mathcal{E}R_2}{R_1+R_2}$

Time Constant = $\tau = RC$. The Time Constant is measured in seconds.

> [!NOTE]
> $\mathcal{E}$, emf, or electromotive force is the voltage of your battery.
>
> Why don't I use $\Delta V_{bat}$? $\Delta V_{bat}$ refers to a battery under load. Using $\Delta V_{bat}$ could lead to a voltage that is too high.





The divider formula ends up becoming this:

$3 = \frac{\mathcal{E}R_2}{R_1+R_2}$

And you can solve the equation by choosing one of the resistor values and solving for the other.

> [!TIP]
> Choose a high resistor value to limit the current going to the receiver. I'm talking kiloohms.

## Building the VDU

Here's the values I will be using, These may or may not work for you.

$\mathcal{E} = 12.6V$

$R_1 = 220k\Omega$

$R_2 = 69k\Omega$

> Nice.

$C = 100nF$

> Plugging in my emf and resistor values into the formula gives me 3.01V. Close enough. 

> [!TIP]
> $R_1$, $R_2$, and $C$ all refer to equvalent resistance and capacitance. Feel free to use the properties of resistors and capacitors to create resistor or capacitor values that may be hard to find.
>
> For example, I don't have $69k\Omega$ resistors, so I put a $22k\Omega$ and a $47k\Omega$ in series. This is basically identical to using a $69k\Omega$ resistor.
>
> $100nF$ was chosen for the capacitor as I am using high-quality batteries and only use brushless motors. If you are using lower quality batteries or brushed motors, consider using a capacitor with a higher capacitance.
&nbsp;

### 1) Do a dry run
Place all of your parts into the protoboard according to the diagram. 

**Do not** solder anything together. 
