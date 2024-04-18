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

- **ASIC Design Flow using OpenLANE**
<br>
An application-specific integrated circuit is an integrated circuit (IC) that's custom-designed for a particular task or application. Unlike FPGA boards that can be programmed to meet a variety of use case requirements after manufacturing, ASIC designs are tailored early in the design process to address specific needs.
<br>
OpenLane is an automated RTL to GDSII flow that is composed of several tools such as OpenROAD, Yosys, Magic, Netgen, Fault, CVC, SPEF-Extractor, CU-GR, Klayout and a number of scripts used for design exploration and optimization. This collection of tools performs all steps required in a full ASIC implementation from RTL to GDSII.
<br><br>

![image_2024-04-18_193042068](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/3c34612a-720c-4b59-98d9-7f591a605650)
<br>

## Design Preparation Step
<br>

- To access OpenLANE, we enter `cd Desktop/work/toold/openlane_working_dir/openlane/docker`
- We use `-interactive` to design the system as per the flow for better understanding
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/fc79a6dc-4dfc-47ea-96cc-c1f819993702)

<br>

- Design setup stage involves setting up the data structure, file designs and other requirements of a design and is done using the command `prep -design picorv32a`
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/bd7b8c84-5201-4358-aa39-15aac9a5102d)

<br>

 - `run_synthesis` is used to run the Yosys synthesis tool as well as the abc
 - The result for the above command will be:
<br><br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/e851f642-d6a7-4e12-948f-d23fe75f9bff)
<br>
```
Flop Ratio = Total number of flip flops / Total number of Cells
```

- In the output of the above synthesis, the flop ratio is 10.84%<br><br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/73e15429-efaf-42bd-8aa7-0f66050641da)

<br>

- The output of the ABC Synthesis is:
<br><br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/015bdd61-ce9d-499a-b189-8c83bb91b883)
<br>

## Floorplan using OpenLANE

<br>

- `run_floorplan` command is used to design the floorplan in Openlane. The output will be as follows:
<br><br>


![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/b35278ad-cbd0-4c45-b541-977625e0a618)
<br>






