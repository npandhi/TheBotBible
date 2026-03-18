# Building the Wiring Harness
This guide will walk you through wiring up a BattleBot's wiring harness.

> [!WARNING]
> The electronics I used to make this guide may be different than yours.
>
> The process should still be about the same.

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



## Parts and Tools
The following tools and parts are needed to complete a wiring harness. 

Tools can be purchased from [Amazon](amazon.com) or [Micro Center](microcenter.com), while parts can come from the combat robotics supplier of your choice. [Palm Beach Bots](palmbeachbots.com), [Repeat Robotics](repeat-robotics.com), and [FingerTech Robotics](fingertechrobotics.com) are all great suppliers. Parts have been fairly standarized, so feel free to mix and match parts between suppliers.

Bolded items are required, everything else is optional, but are still recommended.

### Tools
- **Soldering iron**
- **Solder**
- **Solder wick / Desoldering pump**
- **Solder sponge / Brass wool**
- **Soldering mat**
- Flux
- Tip tinner
- **Wire cutters**
- **Heat Shrink**
- Wire strippers
- Fume extractor
- **Safety goggles**

### Parts to be soldered
- **Drive ESC(s)**
- **Drive Motors**
- **Weapon ESC**
- **Power Distribution Board (PDB)**
- **Power Switch**
- **Battery JST**
- FS2A

> [!IMPORTANT]
> The following tools and parts will be used in this guide:
> - Pinecil V2 Soldering Iron
> - Lead-free flux core solder
> - Lead-free Superwick
> - Hakko 599B Brass wool
> - Chipquik
> - Flush cutters
> - A PC fan to extract fumes
> - Maginfying safety goggles
> - Repeat Robotics AM32 Brushless Dual Drive ESC + PDB
> - Repeat Robotics MK4 Brushless Drive Motors
> - ReadyToSky 45A Weapon ESC
> - Fingertech Mini Power Switch
> - Battery JST
> - _220k/69k Voltage Divider Unit_

> [!NOTE]
> The voltage divider is used by my modified IA6B for extra telemetry data.
> 
> **You do not need this and you shouldn't add one unless you know exactly what you are doing.**
> 
> **You cannot buy this part. You must make it yourself.**
>
> Check the voltage divider guide to make a divider unit.

## Circuit Diagram

<img src="/media/harness/diagram.png?raw=true" alt="A diagram showing the wiring of a brushed wiring harness." width=90%>

> [!NOTE]
> This diagram is for is for a split/double ESC brushed drive setup. 

## Assembly

### 1) Lay out your parts.
Lay out your parts in the way you will connect them, ensuring no part is left behind. 

&nbsp;
### 2) Prep the pads of the PDB.

> [!TIP]
> Before soldering, clean your soldering iron tip and apply some fresh solder.

Apply a layer of solder to the PDB. Using some extra flux here will make this a lot easier. 

&nbsp;
### 3a) Connect the Motors and the Drive ESCs to the PDB (Brushed)
*For brushed drive motors, such as the Repeat MK2 or the Silver Spark.*

Place heat shrink onto the ESC wires.

Loop the ends of the ESC wires into the terminal hooks and solder the hooks to the wire. The orientation of the wires isn't super important.

Slip the heat shrink over the terminal and apply heat to protect the connection.

Repeat this for the other motor, then solder the power leads of the ESC to the PDB. Orientation does matter. Red is positive, black is negative. You may have 2 ESCs.


&nbsp;
### 3b) Connect the Motors and the Drive ESCs to the PDB (Brushless)
*For brushless drive motors, such as the Repeat MK4.*

Solder the three motor leads to the ESC. The orientation doesn't matter. 

Repeat this for the other motor, then solder the power leads of the ESC to the PDB. Orientation does matter. Red is positive, black is negative. You may have 2 ESCs.

> [!NOTE]
> The Repeat Robotics AM32 Dual Drive Brushless ESC (The one used in the pictures) has a PDB system built in to the ESC. You do not need to use a second PDB.

&nbsp;
### 4) Connect the weapon ESC to the PDB

Solder the ESC leads to the the PDB. Orientation does matter. Red is positive, black is negative.

The position of the ESCs does not matter, as long as all reds are positive and all blacks are negative.

&nbsp;
### 5) Building the receiver
*If you are NOT using the FS2A, skip this step and move on to step 6.*


