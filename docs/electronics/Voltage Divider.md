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

**Do not** solder anything together yet. 

Make sure everything fits and that it is wired correctly. 

<img src="/media/vdu/dry.JPG?raw=true" alt="A dry fit of my VDU" width=50%>
&nbsp;

### 2) Bend the legs

Bend the legs of your components to stop them from falling out. 

> [!TIP]
> Resistors can go in either direction. However, I suggest you put them all in the same direction. It looks much nicer.

Ensure your components are flush with the board. 

> [!TIP]
> If you are having trouble with the components falling out or are not confortable soldering with this many components loose on the board, consider bending and soldering each component individually. 

<img src="/media/vdu/legs.JPG?raw=true" alt="Bent legs on my board" width=50%>
&nbsp;

### 3) Soldering the components

If you have flux, apply it to the joints now.

<img src="/media/vdu/flux.JPG?raw=true" alt="Applying Chipquik Flux to the board" width=50%>
&nbsp;

Then, solder on each leg.

> [!IMPORTANT]
> Ensure your tip is clean and shiny. You can do this by using a sponge, then going over the tip with fresh solder.

<img src="/media/vdu/leg solder.JPG?raw=true" alt="Soldering on a leg" width=50%>
&nbsp;

Repeat this for all of your legs and cut off any excess. 
&nbsp;

### 4) Making the bridge

Find where $R_1$ meets $R_2$ and $C$. For me, its where my iron is pointing.

<img src="/media/vdu/bridge 1.JPG?raw=true" alt="Pointing to the first section the bridge" width=50%>
&nbsp;

Heat up both joints and apply a blob of solder between them. You may add extra flux if needed.

<img src="/media/vdu/solder bridge 1.JPG?raw=true" alt="Soldering to the first section the bridge" width=50%>
&nbsp;

Here is what a successful bridge should look like. This bridge connects $R_1$ to the rest of the circuit.
<img src="/media/vdu/bridge 1 done.JPG?raw=true" alt="Finished solder bridge" width=50%>
&nbsp;

### 5) Bridge subcomponents

Instead of a $69k\Omega$ resistor, I used a $22k\Omega$ and a $47k\Omega$ resistor in series. I have to connect them together in series on the board by bridging this spot.

<img src="/media/vdu/bridge 2.JPG?raw=true" alt="Pointing to the second section the bridge" width=50%>
&nbsp;

Here is the completed bridge.

<img src="/media/vdu/bridge 2 done.JPG?raw=true" alt="Finished solder bridge" width=50%>
&nbsp;

> [!NOTE]
> The joints you will have to bridge or solder may differ based on your exact components and configuration. Check the diagram.
&nbsp;

### 6) Clean the board

Pour some Isopropyl Alcohol on the board. Just a few drops should do. I'd recommend placing the board on a napkin or towel.

<img src="/media/vdu/ipa.JPG?raw=true" alt="Pouring some Isopropyl on the board" width=50%>
&nbsp;

Using a soft brush, brush the joints to get rid of any excess flux. A toothbrush works well for this.

> [!WARNING]
> Use a new toothbrush. Do not use this toothbrush to brush your teeth afterwards.

<img src="/media/vdu/brush bottom.JPG?raw=true" alt="Cleaning the joints" width=50%>
&nbsp;

### 7) Testing

I'd recommend testing the board now. I've attached my benchtop power supply to the positive and negative terminals of the board, and have connected my multimeter to the power supply ground with an alligator clip.

I will now use the red probe to measure the voltage between the resistors. (The green wire on the diagram)

<img src="/media/vdu/meter.JPG?raw=true" alt="Testing the VDU" width=50%>
&nbsp;

> The divider seems to be working just fine. $2.74V$ is lover than the $3.01V$ I was expecting, but the theoretical value does not account for real world factors. $2.74V$ will be perfectly fine. 

If yours does not work:
- Check for solder bridges that were not purposefully formed.
- Look for missed or poorly soldered joints.
- Clean off any residual flux.
- Check for metal debris stuck to the board.
- Compare your board to the diagram and ensure that they match.
- Ensure your resistor and capacitor values match what you calculated.

&nbsp;
### 8) Adding wires

Add the connecting wires to the board. You should have three: One for power, one for ground, and one for the divided voltage.

<img src="/media/vdu/wires.JPG?raw=true" alt="Adding wires" width=50%>
&nbsp;

Solder the wires to the board.

<img src="/media/vdu/solder wire.JPG?raw=true" alt="Soldering the wires to the board" width=50%>
&nbsp;

### 9) Finishing up

Clean off any excess flux off the board. Clean both the top and the bottom.

<img src="/media/vdu/brush top.JPG?raw=true" alt="Cleaning off flux" width=50%>
&nbsp;

Cut the board down to size. Make it as small as possible, as the board itself has weight. 

> [!TIP]
> If you have a utility knife, score where you want to cut and snap it. This is cleaner and safer. 

<img src="/media/vdu/cut.JPG?raw=true" alt="Cutting the board to size" width=50%>
&nbsp;

Admire your handiwork.

<img src="/media/vdu/done.JPG?raw=true" alt="A picture of the finished VDU" width=50%>
&nbsp;

Congratulations! You survived. Give yourself a well deserved break. 

## Conclusion
A VDU is actually a standard component used often in electronics. This guide works for any VDU or Voltage Divider. 

Next, modify your IA6B to accept the the telemetry data and install OpenI6X on your I6X.

