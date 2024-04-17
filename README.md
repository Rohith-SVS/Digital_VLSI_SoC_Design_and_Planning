# Digital_VLSI_SoC_Design_and_Planning
## Introduction
An integrated circuit, also known as a microchip, chip or IC, is a small electronic device made up of multiple interconnected electronic components such as transistors, resistors, and capacitors. These components are etched onto a small piece of semiconductor material, usually silicon.
<br> <p align="center">
  ![image_2024-04-17_201134006](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/d5715b1e-b7e8-4316-8e54-7e260cbd26c8)
</p>
<br>
 
- **Wire Bond**
<br>Wire bonding is the method of making interconnections between an integrated circuit (IC) or other semiconductor device and its packaging during semiconductor device fabrication. <br><br>

![Screenshot 2024-04-17 202738](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/386006a8-557b-465e-ba4d-c0efeaa33cae)
- **Die**
<br>A die, in the context of integrated circuits, is a small block of semiconducting material on which a given functional circuit is fabricated. <br>
- **Core**<br>
A semiconductor intellectual property core (SIP core), IP core or IP block is a reusable unit of logic, cell, or integrated circuit layout design that is the intellectual property of one party.<br>
- **Pads**<br>
Contact pads or bond pads are small, conductive surface areas of a printed circuit board (PCB) or die of an integrated circuit. They are often made of gold, copper, or aluminum and measure mere micrometres wide. Pads are positioned on the edges of die, to facilitate connections without shorting.<br>

Any program which is written in `C language` is first compiled into `Assembly level Language`. This `Assembly level language` is then translated into `Binary language` for the chip to perform the required functionality. This translation from Assembly to Binary language is carried out by the `RTL logic`. The RTL is responsible for implementing the specifications of the RISC V processor.
<br><br>
![image_2024-04-17_210632880](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/d57bddce-ae9d-44a5-a011-90ba1cd2c8c4)
- **RTL Design**
<br>In digital circuit design, register-transfer level (RTL) is a design abstraction which models a synchronous digital circuit in terms of the flow of digital signals (data) between hardware registers, and the logical operations performed on those signals.<br>
- **EDA Tools**
<br>Electronic design automation, also referred to as electronic computer-aided design, is a category of software tools for designing electronic systems such as integrated circuits and printed circuit boards. The tools work together in a design flow that chip designers use to design and analyze entire semiconductor chips.<br>
- **PDK Data**
<br>A process design kit is a set of files used within the semiconductor industry to model a fabrication process for the design tools used to design an integrated circuit. The PDK is created by the foundry defining a certain technology variation for their processes.<br><br>

>[!NOTE]
>Some of the available `Open source tools` are shown in the image which can be used by the masses for designing an `IC`

![image_2024-04-17_213405578](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/2891405a-56b8-4391-8394-50fae784048b)
<br>
```
RTL to GDSII Flow
├──Synthesis
├──Floor and Power Planning
├──Placement-Gloabal and Detailed
├──Clock Tree Synthesis
├──Signal Routing
└──Sign Off-Physical Verification and Timing Verification
```
<br>

