# Digital_VLSI_SoC_Design_and_Planning
This repository is mainly to understand the basics of opensource EDA tools, OpenLANE and skywaterPDK. Here the focuus is on only the labs
# Table of Contents
- [Inception of open-source EDA OpenLANE and skywaterPDK](#inception-of-open-source-eda-openlane-and-skywaterpdk)
- [Good floorplan vs bad floorplan and introduction to library cells](#good-floorplan-vs-bad-floorplan-and-introduction-to-library-cells)
- [Design library cell using Magic Layout and ngspice Characterisation](#design-library-cell-using-magic-layout-and-ngspice-characterisation)
# Inception of open-source EDA OpenLANE and skywaterPDK 
Day 1 ::Learning Task:

Basic commands in Linux are needed
````
cd - change directory
 ls - list the files of directory
clear - clears the terminal
mkdir - make directory
pwd - present working directory
command --help - help for particular switches
````
The first objective of the workshop :
  1. Run the `picorv32a` design using Openlane flow
  2. Calculate flop ratio and its percentage of D Flip flop
Implementation of this task is presented in the form of screenshot
     
 ![Screenshot from 2024-04-12 11-43-07](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/6848add4-ada0-4e2d-924f-da1335f08068)
 
The outcome of Synthesis tool gives:
1. Total no of D Flip Flops = 1613
2.  Total no of cells = 14876
   The Flop ratio = Total no of D-Flip Flops / Total no of Cells
                  = 10.84%
    
More details on Openlane can be obtained [here](https://github.com/efabless/openlane).

# Good floorplan vs bad floorplan and introduction to library cells
Day 2: Learning Task : To know the floorplan and review in layout by sing Magic software
Floorplan is the arrangement of IPs in a chip
  * Utization factor factor = Area occupied by netlist / Total area of core.
  * Aspect ratio = Height / Width.

![Screenshot from 2024-04-23 15-00-23](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/1d45866c-78ea-4113-a566-07bed152ad29)

# Design library cell using Magic Layout and ngspice Characterisation

Day 3: Learning Task : To know the floorplan and review in layout by sing Magic software
![Screenshot from 2024-04-16 15-15-05](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/92e19f87-aa9f-4932-bdd5-ab52688fd3fa)
![Screenshot from 2024-04-16 16-29-42](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/b710d266-aee1-4957-a372-6bf4a9abcc1e)
![Screenshot from 2024-04-16 16-55-44](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/f42999e3-a898-41ed-8a88-eaa8844ea02e)
The changes done in  output capacitor and running the file again gives
![Screenshot from 2024-04-16 16-57-12](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/718737fc-53df-4a8c-b745-ce148e43a0bf)
Now plotting the graph by command ` plot y vs a `

![Screenshot from 2024-04-16 17-15-00](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/59cff69a-b449-476f-8703-c7925325c38b)
```
Rise time calculation is the time taken between 20% to 80% value on output waveform
x0 = 2.1819e-09 y0= 0.66
x0 = 2.245e-09  y0 = 2.64
so risetime = (2.245-2.1819)e-09 = 0.064ns
Fall time = 0.042ns
Propagation delay : It is the difference at 50% level from input and output level.
so Propagation delay = (2.21 - 2.15)e-09 = 0.06ns
````
Next is to create the lef file from the layout
![Screenshot from 2024-04-23 16-29-24](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/9c46a03d-9cab-4228-a177-483d1f302ccb)

   

  
    
    
     
    
   

# Acknowledgements
My heart felt thanks to Mr. Kunal Ghosh and Mr. Nickson Jose for meticulously framing the theory and practical from RTL to GDSII using opensource softwares. 
