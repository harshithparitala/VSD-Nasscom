# VSD-Nasscom

<details>
<summary><b>Day 1:</b>  Inception of open-source EDA, OpenLANE and Sky130 PDK </summary>   
<br>
  <details>
  <summary><b> Topic 1:</b>  Introduction to QFN-48,Package,Die,Core and IP's </summary>   
  <br>

![image](https://github.com/user-attachments/assets/58f6da45-1282-499a-89b8-46f8cf8eab01)

The highlighted one is the PROCESSOR/SOC connected along with other peripherals or interfacess .
The entire board can be describes as shown in figure 

![image](https://github.com/user-attachments/assets/ab6dfa84-ecd6-4ca8-8565-3fc9368b617b)

This consists of ADC, DAC, SRAM, UART,VCC/GND,I2C,SDRAM Chip and etc., there are there in typical ardunio board 

If , we open up on chip,it will loook like
![image](https://github.com/user-attachments/assets/e536e46e-0213-4c7d-9109-4d525ec55292)


Lets take an example of package ,QFN-48 .The QFN-48 Package has 48 pins and size of the package as 7mm 
![image](https://github.com/user-attachments/assets/4a11f75d-72b2-486f-b5d5-2a74e2a16b6b)

If we openup the chip we have various kinds of components such as Pads, Die,Core etc.,
![image](https://github.com/user-attachments/assets/17ebda03-7898-4345-a98a-0e0c32038ab8)

Pads: A component through which we can send the signals inside or outside of the chip

Die: defines the entire size of the chip

Core: the centre of the chip  where all the digital logics are placed
![image](https://github.com/user-attachments/assets/d549117d-0a4e-4e79-a238-90f2c21b5b74)

If we take an example of RISC-V,it look like
![image](https://github.com/user-attachments/assets/159f9c5a-ccee-4c9a-a7dd-edd48416946f)
typical chip consists of Pll,AD,DAC,SRAM  and these are called foundaryIPS

![image](https://github.com/user-attachments/assets/9e54cd99-66f8-4aae-9dbd-39221d95d3fe)

FoundaryIPS :Foundry IP refers to intellectual property (IP) blocks and libraries used in foundries, which are companies that manufacture integrated circuits

SOC,SPI Are called MACROS which are purely digital blocks.

In the second lecture we talk about RISC-V Instruction set ,
-------------------------------------------------------------------------------------------------------------------------------------------------------
For example , a c-program thats nedds to be run on computer or  a layout which is the interior of the chip,we need to compile into its assembly language is then converted into machine learning programm which is binary zeros and ones.

![image](https://github.com/user-attachments/assets/109e7823-ed6c-47d6-8f9d-2bfa1e961744)

The another interface which is present between RISC-V AND Layout is Hardware Description Language .We need to implement the RISC-V architecture specification using hdl .

![image](https://github.com/user-attachments/assets/bc2e283c-8d7b-4b7b-adb0-7773152b628c)

the flow starts from architecture and implemented using rtl and rtl to layout .

![image](https://github.com/user-attachments/assets/1d8db591-15a7-4578-9ff5-dc7a4d2af985)

In the third lecture disscused about flow from software applications to hardware 
----------------------------------------------------------------------------------------------------------------------------------------------------------
The software applications enter into a block called  system-software . system software converts the software application programm into binary language.
The major components of system software are operating system(os), Compiler and Assembler
![image](https://github.com/user-attachments/assets/48098144-3002-423e-886b-dae1259136ef)
The operating system is take the app and convert into assembly program and then finally into binary language program
Theoutput of the os is in the functions of C/C++/JAVA etc., these are taken by compiler and converts into Instructions .These instructions are taken by Assembler and converts into binary language.
![image](https://github.com/user-attachments/assets/5a258569-d622-4bb7-926c-9b53d76c3600)

For example
---------------------------------------------
Foa a add instruction ,the output of the assembler is the binary , we need an rtl which implements the spection for implementing the instruction set and rtl is synthesised into an netlist [digital logics],from netlist to hardware is called the physical design implementation of the netlist 
![image](https://github.com/user-attachments/assets/834c8967-a651-4436-8e69-4d1d9a55cc2d)


  </details>
   <details>
  <summary><b> Topic 2:</b> SOC Design and OpenLane </summary>   
  <br>

ASIC design
-------------
![image](https://github.com/user-attachments/assets/61403ae8-2cd5-4ebc-a0e6-abadfae676c1)

What is PDK?

PDK stands for Process Design Kit 
Collection of files used to modal a fabrication process for the EDA tools used to design an IC ;
Process Design Rules: DRC,LVS,PEX

OPEN SOURCE DIGITAL ASIC DESIGN
----------------------------------------
![image](https://github.com/user-attachments/assets/b3459d41-6d82-4ca0-ae92-1d0df95a592d)

EDA TOOLS 

![image](https://github.com/user-attachments/assets/780a31df-7d45-4c0b-9553-a1fc955032da)

ASIC DESIGN FLOW
--------------------------------------------------------------------
![image](https://github.com/user-attachments/assets/5608253d-dd07-43c0-a735-5c42315dcdfa)

Synthesis:
----------
Converts RTL to a circuit out of components from the standard cell library
![image](https://github.com/user-attachments/assets/0058cbd9-c19e-47db-93d4-62ee9318d9b8)

Floor and Power Planning: 
-------------------------
Partition the chip die between differnt system building blocks and place input output Pads 

for macroflooring there will be Dimensions ,PinLocations and Rows

![image](https://github.com/user-attachments/assets/ee0cbbf1-9dae-4466-81cb-5fb3e7022fdc)

Power Planning:
-------------
Power Networks are construcetd in terms of multiple vdd and grounds ,these are connected to all components verticall or horizantal, these are having less resistance due to these are metal surfaces
![image](https://github.com/user-attachments/assets/316123f5-a19c-4817-95f3-47f47b723a96)

Placement:
---------
![image](https://github.com/user-attachments/assets/bd510375-1d2b-4c54-96c2-07a18fa7af9a)

these are two kinds :
global:
optimum position for all cells

detailed: the positions that are obtained from global placemnt are minimally altered
![image](https://github.com/user-attachments/assets/3f379845-acba-457e-82f9-f4ac2a5c4d13)

Clock Tree Synthesis:
----------------------
![image](https://github.com/user-attachments/assets/5276c0c3-18b9-4c49-9283-e52e47b9b0e4)

Routing:
----------
![image](https://github.com/user-attachments/assets/c6b38024-af44-4c76-ae63-d4dad6b71d2f)
![image](https://github.com/user-attachments/assets/05e77ac9-a221-41d1-8a4d-14e206a572f4)

Sign-Off:
--------------
![image](https://github.com/user-attachments/assets/275975d4-411f-4196-968f-0beed460a169)

Introduction to OpenLane ASIC design Flow 
---------------------------------------------------------
![image](https://github.com/user-attachments/assets/400212be-debb-4384-98c0-cdafb4a9e878)

Fault:

![image](https://github.com/user-attachments/assets/994cd900-0423-44db-a01c-d9aceedf70e2)

OpenRoad: Used for Physical Implementation

![image](https://github.com/user-attachments/assets/9f6201e4-2f19-4960-bb5a-c2cbfd5c2bbe)

YOSYS: Used for Logic Equivalence Check [LEC]

![image](https://github.com/user-attachments/assets/f05e188d-f92a-48a7-8db1-9a51bdb33da4)

Magic:
Used for Physical Verification DRC & LVS
![image](https://github.com/user-attachments/assets/752eec12-b651-4eee-9111-86e6c1454122)



    
</details>  
   <details>
  <summary><b> Topic 3:</b> familarization to EDA Tool </summary>   
  <br>
Basic Linux Commands

## ls

**Command:** `ls [options] [directory]`
**Description:** Lists the contents of a directory. If no directory is specified, it lists the contents of the current directory.
**Options:**

* `-l`: Displays detailed information (permissions, owner, size, etc.)
* `-a`: Includes hidden files
* `-r`: Reverses the order of the listing

## pwd

**Command:** `pwd`
**Description:** Prints the full pathname of the current working directory.

## mkdir

**Command:** `mkdir [directory_name]`
**Description:** Creates a new directory with the specified `directory_name`.

## ls -ltr

**Command:** `ls -ltr`
**Description:** Lists the contents of the directory in long format (`-l`), sorted by modification time (`-t`), in reverse order (`-r`). Useful for viewing the most recently modified files at the end of the list.

## help

**Command:** `help [command]`
**Description:** Displays information about the built-in shell commands. If no command is specified, it shows a list of all available commands.

## man

**Command:** `man [command]`
**Description:** Displays the manual page for the specified command, providing detailed usage information.

## cp

**Command:** `cp [source] [destination]`
**Description:** Copies files or directories from the source to the destination.

## rm

**Command:** `rm [file]`
**Description:** Removes (deletes) the specified file or directory.

   <details>
  <summary><b> Topic 3.2 :</b> Run 'picorv32a' design synthesis using OpenLANE flow and generate necessary outputs </summary>   
  <br>
    
     Commands to Invoke the OpenLANE Flow and Perform Synthesis
     
## 1. Change to OpenLANE Directory

**Command:** `cd Desktop/work/tools/openlane_working_dir/openlane`
**Description:** Navigates to the directory where the OpenLANE flow is installed. This location contains all scripts, configuration files, and flow management utilities.

## 2. Launch OpenLANE Docker Container

**Command:** `docker`
**Description:** Starts the OpenLANE Docker container using a predefined alias. The alias sets up required volume mounts and environment variables, making it easier to access files on the host system from within the Docker container.

## 3. Start OpenLANE Interactive Mode

**Command:** `./flow.tcl -interactive`
**Description:** Launches the OpenLANE flow in interactive mode using its Tcl-based script. This mode allows users to execute each stage of the design flow manually and observe results.

## 4. Load OpenLANE Package

**Command:** `package require openlane 0.9`
**Description:** Loads the OpenLANE package (version 0.9) inside the Tcl shell. This step is necessary to access flow-specific commands.

## 5. Prepare the Design

**Command:** `prep -design picorv32a`
**Description:** Initializes and prepares the `picorv32a` design. This creates the required directory structure, copies configuration files, and sets up the environment for the selected design.

## 6. Run Synthesis

**Command:** `run_synthesis`
**Description:** Runs the synthesis step on the loaded design. The synthesis tool (typically Yosys) transforms the RTL (Verilog) into a gate-level representation that can be used for placement and routing.

## 7. Exit OpenLANE Flow

**Command:** `exit`
**Description:** Exits from the OpenLANE interactive Tcl environment.

## 8. Exit Docker Container

**Command:** `exit`
**Description:** Terminates the Docker container session and returns control to the host machine shell.


Screenshots of these running commands respectively given below 

![Image](https://github.com/user-attachments/assets/0e02917f-eb99-42b3-8c61-b680e318c423)
![Image](https://github.com/user-attachments/assets/6123c647-742e-4056-a955-95308591750a)

# Flop Ratio Calculation

## Definition

* **Flop Ratio**
  $\text{Flop Ratio} = \dfrac{\text{Number of D Flip‑Flops}}{\text{Total Number of Cells}}$
* **Percentage of D Flip‑Flops**
  $\%\text{ DFFs} = \text{Flop Ratio} \times 100$

## Example (from Synthesis Statistics)

| Metric                        | Value   |
| ----------------------------- | ------- |
| Number of D Flip‑Flops (DFFs) | `1613`  |
| Total Number of Cells         | `14876` |

**Step‑by‑Step Calculation:**

1. **Flop Ratio**
   $\frac{1613}{14876} \approx 0.108429685$
2. **Percentage of DFFs**
   $0.108429685 \times 100 \approx 10.84296854\,\%$

## Interpretation

Approximately **10.84 %** of the synthesized cells are D Flip‑Flops. A lower or higher ratio affects clock‑tree complexity, power consumption, and timing closure effort, so this metric helps gauge sequential logic density during design analysis.

![Image](https://github.com/user-attachments/assets/40959b9a-8df6-4c85-b58f-81234bd6e32f)



   </details> 
</details>
</details>





<details>
<summary><b>Day 2:</b> Good floorplan vs bad floorplan and introduction to library cells </summary>   
<br>
  <details>
<summary><b>Topic 1:</b> Chip Floor PLanning Considerations </summary>   
<br>

  <details>
<summary><b>1.1:</b> Utilization factor and Aspect ratio </summary>   
<br>

In the physical design flow the first step is defining the height and width of the core
![Screenshot 2024-10-06 103517](https://github.com/user-attachments/assets/55cbf2f4-132a-4c1c-9cc3-e1c8d83e9402)

Let's take an example of basic netlist consists of two flipflops and logic gates

![Screenshot 2024-10-06 103537](https://github.com/user-attachments/assets/e0e31ced-9a20-47e2-ae46-70af543fad70)

In this we are dependent on the dimensiions of logic gates and flipflops ,
lets assume standard cells are having an area of 1sq.unit and same are for flipflops as well

![Screenshot 2024-10-06 103552](https://github.com/user-attachments/assets/dd9a07af-9991-450d-a626-b13241f0caf1)

If we bring all the standard cells and flip flops together and caluclate the are area gives the minium area occupied by the netlist

![Screenshot 2024-10-06 103615](https://github.com/user-attachments/assets/bcda6bb0-055f-495d-8914-8afcb65d0a77)

If we place the netlist inside the core , we have seen that netlist completely occupies the core which means it has 100% utilization  of the core 

![Screenshot 2024-10-06 103640](https://github.com/user-attachments/assets/d520aa3a-f585-4649-a52b-2c6a5691a615)

Utilization factor is given by Area occupied by the netlist to Total Area of core

![Screenshot 2024-10-06 103640](https://github.com/user-attachments/assets/9f9cd759-85fb-4967-837a-a47003fa7b53)

Aspect Ratio is given by Height to the Width of the core .

Another example where the dimensions of the netlist is same and core is different 
![Screenshot 2024-10-06 103713](https://github.com/user-attachments/assets/38922f37-b0dd-40ce-bee5-beffd35e40aa)

In this case the utilization factor is 0.5
And Aspect ratio is also 0.5

![Screenshot 2024-10-06 103746](https://github.com/user-attachments/assets/5168dd59-b0d1-4952-a1bf-0d5750bf4cd5)

</details>

  <details>
<summary><b>1.2:</b> Concept of pre placed cells </summary>   
<br>
  cells that are placed in the core of a design before the placement and routing stages

Lets take an example of combinational logic circuit and output of the combinational logic is huge circuit

![Screenshot 2024-10-06 113528](https://github.com/user-attachments/assets/08b0ddf1-ca4e-4255-9d18-e2d7d01d0dd3)

so, we cut /divide the circuit into differnt parts .

![Screenshot 2024-10-06 113545](https://github.com/user-attachments/assets/c38d10ed-1fad-44d5-b279-212c7dc78d25)

lets assume circuit is divided into two parts and we separate into two different blocks and implemented separately 
These blocks are considered as Black box .

![Screenshot 2024-10-06 113556](https://github.com/user-attachments/assets/e1a64ef4-8f6e-4436-935e-2da2d43ef3cd)

If these blocks are replicated multiple times on the chip, We implement this block once and reused multiple times whenever it requires in the cihp.

![Screenshot 2024-10-06 113613](https://github.com/user-attachments/assets/c08ed8a3-62f3-4369-a9c6-e0fb8264822d)

Similarly there are other IP's are also avaliable. These are called pre-placed cells.

![Screenshot 2024-10-06 113633](https://github.com/user-attachments/assets/6be43725-f05b-42b5-a9b9-f831a13110ad)

    
</details>

  <details>
<summary><b>1.3:</b>Decoupling capacitors </summary>   
<br>
After placing the pre placed cells in the core , we need to surround them with the Decoupling capacitors .

![Screenshot 2024-10-06 120830](https://github.com/user-attachments/assets/ea3485d6-07ca-4da4-a1b7-000c4a5024ed)

 Lets consider this circuit is a part of any block of pre placed cells , whenever any gate switches from logic 0 to logic 1 there is some amount of current that demands , there is some capacitance setting over gate that capacitence needs to completely charge to represent logic 1 , this amount of charge is sent by power supply 
 Suppouse if the transition happening from logic 1 to logic 0, it is the responsibility of vss to take amount of charge .The capacitor will discharge 

![Screenshot 2024-10-06 120848](https://github.com/user-attachments/assets/7c7aabdb-32e8-40f5-86b8-25db971dba76)

 There will be some voltage drop across the wire and if the voltage vdd' is should be noise margin .
 Any voltage lies between Vil and Vih is undefined region , it's also called grey region.it can go either logic 0 or logic 1
 
![Screenshot 2024-10-06 120939](https://github.com/user-attachments/assets/2b4668c0-5f7f-4147-9e27-14ab81329360)

 We can ensure that voltage never lies in undefined region with the help of Decoupling capacitors , These capacitors decouples the circuit from main supply
 
![Screenshot 2024-10-06 120952](https://github.com/user-attachments/assets/918978d7-d1b1-4949-959f-76c8d7fb7a69)

 whenever switching happen decoupling capacitor will the current to circuit and these are placed very close to the circuit 

 ![Screenshot 2024-10-06 121012](https://github.com/user-attachments/assets/c8149a7c-8595-47ac-9f08-39a67413a1d7)

</details>


  <details>
<summary><b>1.4:</b>Power planning</summary>   
<br>
    Let us consider the circuit as Black box (macron). If this macron is repeated multiple times on the chip and there will be current demand for each and every macron

![Screenshot 2024-10-06 124925 - Copy](https://github.com/user-attachments/assets/cdffd4e9-fe6e-49c2-be8f-8a964c51ec24)

Let's there is a signal driven to load signal is transition from logic 0 to logic 1. we have to make sure that the signal path maintains same signal that load receives.

![Screenshot 2024-10-06 124934 - Copy](https://github.com/user-attachments/assets/3878b9b6-3720-45b1-9c70-4857848efab6)

let connect the power supply, these bllocks are tapped to vdd and ground respectively 

Since there is no De coupling capacitor near path the power supply need to take care of sinal. Powe supply is far to the path and there will be voltage drop happens 
![Screenshot 2024-10-06 124954 - Copy](https://github.com/user-attachments/assets/d8df73ad-051f-45aa-87a1-9e591140017a)

let's assume it is a 16-bit bus , If the bit is logic 1 it says the capacitor which is being charge to vdd similary logic 0 refers to capacitor discharged to ground
![Screenshot 2024-10-06 125020](https://github.com/user-attachments/assets/78c47552-ddb0-4c7d-9ca0-cb6ccfdc71da)

Let's  say it is connected to inverter , the  output will be all the capacitors are charged  to logic 1 and will discharge to logic 0 and it will cause a bump called as ground bounce 

![Screenshot 2024-10-06 125036](https://github.com/user-attachments/assets/9e573661-fd58-4beb-a06c-51b49e9ab351)

similarly logic 0 to logic 1  cause voltage droop

![Screenshot 2024-10-06 125051](https://github.com/user-attachments/assets/8f8d48c2-6d7c-4b1c-9fc6-20431602b571)

It is due to power is coming from single source, if there are multiple power supplies we can ensure that it will give current or drop current to the circuit 

![Screenshot 2024-10-06 125102](https://github.com/user-attachments/assets/615a5621-4f42-40c2-b01f-90fa24bf5c21)

![Screenshot 2024-10-06 125120](https://github.com/user-attachments/assets/fcea00dd-8e24-449f-b497-b5131f0f25bc)
</details>


  <details>
<summary><b>1.5:</b>Pin placement and logical cell blockage </summary>   
<br>
Lets take an example with two different flipflops with different colors and another section with different flipflop and clocks .

drive by clock 1
![image](https://github.com/user-attachments/assets/04f25190-aee1-420d-ae24-532bb20005f8)
driven by clk 2

![image](https://github.com/user-attachments/assets/cbbb8b61-dd31-4924-94a8-42d4544da4cf)

along with there are pre placed cells connect with din and output are connect to logic gates and another pre plced cell block b takes input from clks and give clock out

![image](https://github.com/user-attachments/assets/6ae6eb14-0cf7-42e8-b9a4-5e5b2f1802a8)


Asuume another section with same design which has two flipflops and two different clks  and another one with same but opposite clocks and block c pre placed cell is connected 

![image](https://github.com/user-attachments/assets/fd4aaf1f-674c-4b42-9068-4b5d117e98d1)

![image](https://github.com/user-attachments/assets/80cc86fb-fce2-47c6-a3ec-8f590370d2a1)


Complete design look like and  We connect clk 1 and clk2 

![image](https://github.com/user-attachments/assets/25830606-bb08-4a2f-9571-c669b1757432)

We fill the area between core and die with these ports and 
We place all the input ports on left hand side and output at right hand side  and ordering will be random

![image](https://github.com/user-attachments/assets/02c405b4-99b4-4ad4-91d6-0a28bfebdde1)

Pin placement creates hand checking frontend and backend ,
Clk ports are bigger in size  because it is continously driving all thw cells and sends the signals to all the flipflops 
The area between die and core blocks for cell placement and it is reserved for pins .

![image](https://github.com/user-attachments/assets/53c0c696-46ac-4b3a-918e-a40e31ba2c0f)

</details>
</details>

