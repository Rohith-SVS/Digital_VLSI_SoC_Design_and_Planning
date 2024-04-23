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

- Floorplan results are created in the below locations.
```
vsduser@vsdsquadron:~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/18-04_15-16/results/floorplan$ ls
merged_unpadded.lef  picorv32a.floorplan.def  picorv32a.floorplan.def.png
```

- The results of the floorplan will be recorded as follows:<br><br>
![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/eb09c3c4-787d-4b66-a1a6-c1f9abd8cd6e)

<br>

- The floorplan can be viewed and edited using the Magic software which can be accessed using the following code-
```
magic -T /home/<user name>/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def
```

- After Executing the above command, a pop up window will appear as shown<br><br>
![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/b3fb98b0-39b7-48d4-b955-6738bf6befbe)

<br>

- We can use `s` to select the floorplan and `v` to align it to the center of the screen<br><br>
![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/1f9e9b7b-fed6-43f4-b552-eecc55872946)

<br>

- We can zoom sepicfic portions of the floorplan using `z` and the components of the floorplan can be selected using `s` . Upon writing `%what`, we will recieve the details of the selected component<br><br>
![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/98d6157c-344a-4337-bc74-f843c36371c8)

<br>

## Congestion aware placement using RePIAce

- `run_placement` command is used to perform global placement in OpenLANE. The main objective of global placement is to reduce the wire length. OpenLANE uses the concept of `Half Parameter Wire Length(HPWL)` to optimize the wiring in global placement.<br><br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/ce4c7331-bb22-4d5d-8cf2-75e34eb714fb)
<br>

- A snapshot of the placement is automatically careted after execution which is named as `picorv32a.placement.def.png`. This image can be accessed using the code `xdg-open picorv32a.placement.def.png` to obtain the following
<br><br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/8b053b5a-4c59-4e0d-903e-110e1c46f1ed)
<br>

- The placement results can be viewed in magic from `/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/22-04_12-46/results/placement` by using the command
```
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/a46db3f4-4e77-4cea-8b50-b6fa6cac5f6d)
<br>

- We can zoom in the magic software to view the placement of the standard cell rows
<br><br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/28226865-7c24-42b1-b50d-e0f64dc12edf)
<br>

## Spice Extraction and Simulation of Inverter Cell

- This content focuses mainly on the extraction and simulation of the Spice model for a given cell.
- The cell view under design is Inverter.
- We obtain the library files from GitHub link
```https://github.com/nickson-jose/vsdstdcelldesign.git```
Courtesy: nickson-jose
- The GitHub repo can be imported to the system using the command `git clone` followed by the URL link of the Repo
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/c572135b-25ac-4e14-bc36-22cecea4222f)
<br>

- `sky130A.tech` file is copied from `~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic` and pasted into `/home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/` using the command
```
  cp sky130A.tech /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/
```

- The inverter file is accessed using Magic Software using the following command:<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/875ded69-f3ef-4e18-9c75-98ecfb328fbd)
<br>

- The following Window will appear:<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/09d54659-d7d5-46d2-b5b6-90e8f99e57ba)<br>

- The Magic software uses different color coding scheme to represent different distinct regions or layers of an Integrated circuit. The `%what` function can be used to identify the different components in the design
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/e50d9fe6-c389-4d89-b9a7-4bf5c74afc10)
<br>

- `%extract all` command is used to extract the info of the spice model and the extracted information is stored in the name of `sky130_inv.ext` <br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/aaa601b2-0c11-4bc6-80ce-7b67dc381365)
<br>

- `%ext2spice cthresh 0 rthresh 0` is used to extract the parasitic capacitances induced in the design. The information can be stored in a file by using the command `%ext2spice`. It will be saved under the name `sky130_inv.spice`
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/816066b5-a3b4-4bbe-802d-60193feaccde)
<br>

- The spice file generated will be as follows:
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/bfaf2a0e-95a5-4067-bb47-0e4200b2fccb)
<br>

- The following changes are made to perform transient analysis for the given circuit:<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/8fc4894e-548c-405d-801f-d5dc40c92f7a)
<br>

- To run the spice simulation use command:
```
ngspice sky130_inv.spice
```
- The output will be as follows<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/ce90612a-7265-4803-8c47-75bd96f49b0f)
<br>

- To plot the graph, we should enter the command `plot y vs time a`<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/8d0dc161-afb7-4242-8751-e29a97f28034)
<br>

- We can calculate Rise Time, Fall Time, Propogation Delay and Cell Fall Delay from the above graph:
- Rise Time : (2.2489-2.1819)e-09 = 66.92 psec
- Fall Time : (4.09512-4.05264)e-09 = 42.51 psec
- Propogation Delay : (2.2106-2.15012)e-09 = 40.48 psec
- Cell Fall Delay : (4.07735-4.04988)e-09 = 27.47 psec

## Magic tool options and DRC Rules

- To download and extract DRC Corrections, run the following commands
```
$ wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
$ tar xfz drc_tests.tgz
$ cd drc_tests
```
<br>

- The following contents will be listed in the folder:<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/365f419c-159a-4aa6-967f-d0bfd90dc242)
<br>

- To open magic, use the command `$ magic -d XR &`<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/8bb4650c-a717-417a-bd95-b68078bcca5d)
<br>

- `drc why` will show the reasons for errors in the system.<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/40da335c-db85-4d10-b7da-8286adaea1ba)

- We create a M3 layer using the middle mouse button followed by the instruction `cif see VIA2` to represent the contact cuts<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/76d07384-2ad3-493d-9e5b-ea33f1b26f2a)
<br>

- `feed clear` instruction can be used to remove the contact cuts<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/47b475ec-48d4-4b29-9e05-6ca33d02f306)

## Exercise to fix poly.9 error in Sky130 tech file

- `load poly` command is executed to load the file containing errors<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/a31b34c8-c382-496a-a31d-0c72316ea9b9)
<br>

- The errors in DRC are as follows:<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/815dac6c-4e01-4e97-b624-6cc7fbe018ae)
![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/26e6b9bf-f880-4633-8b3b-4b89bafd0b5e)
<br>

- New rules are added as shown above and we use the command
```
tech load sky130A.tech
check drc
```
- The errors will be rectified<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/5cf5edcc-7267-4107-ac4d-f02a0a16d127)
<br>

## Pre Layout Timing Analysis and Importance of good clock tree
- The .lef file can be accessed using the following command
```
pdk/sky130/libs.tech/openlane/sky130_fd_sc_hd/track.info
```
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/2d775516-aaf9-446e-a9d5-98b9f337e2de)

- In the layout, ports are situated on the li1 layer. To ensure that ports align with the intersection of tracks, we need to convert the grid into tracks.
- To accomplish this, we'll first open the tracks file and then access the tkcon window and execute the help grid command
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/f8f159bf-6a5e-49fb-b665-5e2b03d33e1b)
<br>
![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/ce01ae08-6a7e-4f8e-bffd-ddeb7a388457)
<br>

- The width of the standard cells should be in odd multiples of track pitch
- We have to execute the command, to extrac the `sky130_inv.lef` and `sky130_vsdinv.mag` file `lef write` .
 <br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/60a32982-d327-44da-8c88-7046977a51fe)
<br>
- The lef file generated will be as follows:
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/a04f911d-e01e-4c99-acb3-7356c1defe36)
<br>

- We copy `sky130_vsdin.lef` and paste it in `/home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src`
- we also copy `sky130_fd_sc_hd__*` into `/home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src`
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/929c18ec-23d3-4000-a513-159820335843)
<br>

- We have to make some configurations in `config.tcl`
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/fa667001-ad94-4f04-bdeb-790c59634023)
<br>

- Now we will go to the open lane directory and execute the docker command.
```
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
run_synthesis
```
- We will get te following output
<br>

![image](https://github.com/Rohith-SVS/Digital_VLSI_SoC_Design_and_Planning/assets/167219715/6a61dbfb-baf9-4d34-8056-a3b22550809d)
<br>

-




