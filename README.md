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

<details>
<summary><b>1.Labs:</b> Run FLoorPlan using OpenLane and review files  </summary>   
<br>

-  Run 'picorv32a' design floorplan using OpenLANE flow and generate necessary outputs.
-  Calculate the die area in microns from the values in the generated floorplan DEF file.
-  Load the generated floorplan DEF in Magic tool and explore the floorplan layout.

1.Run 'picorv32a' design floorplan using OpenLANE flow and generate necessary outputs.
----



Here it explains the detailed process of running OpenLANE interactively for the `picorv32a` design.

---

#### 1. Change to the OpenLANE working directory

```bash
cd Desktop/work/tools/openlane_working_dir/openlane
```

This sets your working directory to where OpenLANE is installed locally on your machine.

---

#### 2. Set up Docker alias (optional)

```bash
# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
```

This command aliases the long Docker run command to `docker`, mounting the current OpenLANE folder and your PDK path into the container. You only need to run this once in a terminal session.

---

#### 3. Launch the OpenLANE Docker container

```bash
docker
```

After aliasing, just typing `docker` starts the OpenLANE container with proper mounts and environment settings.

---

#### 4. Start OpenLANE in interactive mode

```bash
./flow.tcl -interactive
```

This launches OpenLANE’s TCL-based interactive shell, allowing you to control each stage manually.

---

#### 5. Load the OpenLANE package

```tcl
package require openlane 0.9
```

Loads the OpenLANE commands and environment into the current shell session. This step is mandatory before running any flow operations.

---

#### 6. Prepare the design workspace

```tcl
prep -design picorv32a
```

This sets up the design directory, copies configuration files, and initializes the workspace for `picorv32a`. It's a prerequisite before synthesis.

---

#### 7. Run synthesis

```tcl
run_synthesis
```

This performs RTL-to-gate synthesis using Yosys. It converts the Verilog source code into a gate-level netlist and reports cell count, area, and timing.

---

#### 8. Run floorplanning

```tcl
run_floorplan
```

Generates the core and die area, sets up placement rows, IO pins, and creates an initial layout bounding box. This prepares the design for placement.

---

Screenshots of floorplan :

![Image](https://github.com/user-attachments/assets/04ca8c56-7cfb-4002-ad4e-140d7286a43f)

![Image](https://github.com/user-attachments/assets/ad8e96e2-4397-4f79-b61d-11ef4abce749)


2.Calculate the die area in microns from the values in the generated floorplan DEF file.
-

### Understanding Die Area Calculation from DEF File

 A DEF (Design Exchange Format) file contains geometric and placement information for a chip layout. One key property we extract from a DEF is the **die area**, which defines the physical dimensions of the integrated circuit (IC).

The DEF file includes a `DIEAREA` statement, specifying the lower-left and upper-right corners of the die in **database units (DBU)**.

---

####  What is a DBU?

* A **Database Unit (DBU)** is the internal unit of measurement used by layout tools.
* In **Sky130** technology, **1000 DBU = 1 micron**.

This means every coordinate value in the DEF is **1000x larger** than its actual physical size in microns.

---

#### DIEAREA line from DEF

```
DIEAREA ( 0 0 ) ( 660685 671405 ) ;
```

This defines:

* Lower-left corner at (0, 0)
* Upper-right corner at (660685, 671405)

---

###  Step-by-Step Area Calculation

#### 1. Convert Width and Height to Microns

* **Die width (DBU)** = 660685 - 0 = `660685`
* **Die height (DBU)** = 671405 - 0 = `671405`

Now convert DBU to microns:

```
Width in microns = 660685 / 1000 = 660.685 µm
Height in microns = 671405 / 1000 = 671.405 µm
```

#### 2. Calculate Area in Square Microns

```
Area = Width × Height
     = 660.685 × 671.405
     = 443,587.212425 µm²
```

---

###  Results

| Parameter   | Value          |
| ----------- | -------------- |
| Width (µm)  | 660.685        |
| Height (µm) | 671.405        |
| Area (µm²)  | 443,587.212425 |

---

This computed area is essential for estimating silicon cost, planning placement, and evaluating utilization during physical design. Always check the `UNITS` line in the DEF to confirm the DBU-to-micron scale (typically `1000` for Sky130).

screenshots :

![Image](https://github.com/user-attachments/assets/b55481f9-0e21-4a80-850a-ca895fd73bc5)

3.Load the generated floorplan DEF in Magic tool and explore the floorplan layout.
-

### Commands to Load Floorplan DEF in Magic (from a New Terminal)

Follow these steps to load the generated floorplan DEF of `picorv32a` into the Magic VLSI layout tool:

---

#### 1. Change to the Floorplan Directory

```bash
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/21-06_17-40/results/floorplan/
```

This path contains the generated `picorv32a.floorplan.def` file after running the floorplanning stage using OpenLANE.

---

#### 2. Launch Magic with Floorplan DEF and Merged LEF

```bash
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech \
      lef read ../../tmp/merged.lef \
      def read picorv32a.floorplan.def &
```

**Explanation:**

* `-T` specifies the Sky130 technology file for Magic.
* `lef read` loads the merged LEF file, which contains cell and IO macro definitions.
* `def read` loads the physical floorplan layout in DEF format.
* The `&` runs Magic in the background.

---

After running these commands, the Magic GUI will open with the layout. You can zoom, inspect cells, check placement rows, and view pin locations for your design.

Screenshots :-

Floorplan def in magic

![Image](https://github.com/user-attachments/assets/db510809-5caf-4c65-a72e-ad96d4679198)


Equidistant placement of ports:

![Image](https://github.com/user-attachments/assets/7434b744-b619-4a9c-870a-6b238c800aa9)

Horizontal ports :

![Image](https://github.com/user-attachments/assets/fa39d32b-8e6c-4c59-9716-952455044b5f)

Vertical cells :

![Image](https://github.com/user-attachments/assets/33922a79-af95-4454-9d9c-f3d1abd53aad)

Decap Cells and Tap Cells :

![Image](https://github.com/user-attachments/assets/1241afc5-fee2-4f25-85cc-4dd82d820fe4)

Diogonally equidistant Tap cells :

![Image](https://github.com/user-attachments/assets/0cd06758-b243-4273-93fa-795171a3061e)

Unplaced standard cells at the origin :

![Image](https://github.com/user-attachments/assets/2f0348f4-8ca2-4b0f-b8d6-b1bd77dac076)



</details>
</details>


<details>
<summary><b>Topic 2:</b>library binding and placement </summary>   
<br>
   <details>
<summary><b>Theory:</b>library binding and placement </summary>   
<br>
The first step in this is bind the netlist with the physical cells 
Lets say we have this netlist with all these gates,the shapes of these gates represents the functionality of the gates.

![image](https://github.com/user-attachments/assets/19e03a36-f395-465a-ba68-c5a5885e9227)

In reality we have only boxes these flipflops and logic gates are represent using boxes which has physical dimensions.The netlist will look like this if we use boxes.

![image](https://github.com/user-attachments/assets/c838f146-8ee4-4812-b965-ef907dc7f87a)

If all these netlist as well as pre placed cells are present in a shell is called a library ,
library is is where we find all the information about netlist and its timing .library also has various shapes of these particular gates 

Example

![image](https://github.com/user-attachments/assets/d3c89bf6-0106-4089-81bb-60334d96a538)

 After given proper shape and sizes the next step is to take the gates and place it on floor plan
 We have the netlist and floorplan along withe pre placed cells . we place the gates in fllorplan
 
![image](https://github.com/user-attachments/assets/bd573487-8233-4edb-bf3d-b97ccbdf9454)

 In this scenario  FF1 is close to DIN and FF2 is close to DOUT , logic gates between them Simillarly we arange all three sections of netlist .
 
![image](https://github.com/user-attachments/assets/a9db05cd-fa6d-4891-9dad-a3fc4646133e)

 Optimize placement:
 --
Optimization is the process of iterating through a design such that it meets timing, area and power specifications
In this we will estimate the wire length , capacitence etc.,

connecting sec-1 :

![image](https://github.com/user-attachments/assets/2ae00022-62f3-408e-824e-a75c3c75adfa)

For sec 2,Between Din2 and FF1. The wire length will be area and it huge and because of huge length it will has more resistance so we will place the buffers to tramsit the signals without lossing the data ,but there is a loss of area .

connecting sec-2:

![image](https://github.com/user-attachments/assets/a170ca7a-969a-4361-84a2-7355c9032a65)

connecting sec-3:

![image](https://github.com/user-attachments/assets/b9a278b6-3684-4085-9804-75ab42e5c35a)

Connecting SEC-4

![image](https://github.com/user-attachments/assets/9da5058f-a466-4221-bc00-a8dc042e2f02)


Need for Charachterization:
---
Ic design flow:

![image](https://github.com/user-attachments/assets/f396c352-a55e-4899-b26a-6e79b3e95150)

The first step is logic synthesis which is reffered as converting the functionality into legal hardware
The output of Logic synthesis is arrangement of gates that will represents the original functionality that is designed using RTL

The next step  of logic synthesis is floorplanning and decide the size of the core and die

The next step is placemwnt we take the logic cells and place it on the chip in a fashion that initial timming is better

The next step is Clock Tree Synthesis .We place Clock tree that will take care of clock signal reaching at each and every clock end points
After this we will Route the cells .Routing step depends on the charachterization of cell

![image](https://github.com/user-attachments/assets/6caafb5a-20df-4997-b397-7cf20347de28)


The final thing is Static Timing Analysis in which we try to find setup time, holdtime and the maximum frequency of the clock 

![image](https://github.com/user-attachments/assets/9e13ac3f-9942-4eb0-847d-a77e2d1c3bdf)


One common thing across all the stages are "GATES or CELLS".

![image](https://github.com/user-attachments/assets/83a78f21-00a2-403b-a793-b28532e0a3dc)


    
  </details> 
  
  <details>
<summary><b>Lab:</b>library binding and placement </summary>   
<br>

Task:

-  Run 'picorv32a' design congestion-aware placement using OpenLANE flow and generate necessary outputs.
-  Load the generated placement DEF in Magic tool and explore the placement.
  
1.Run 'picorv32a' design congestion-aware placement using OpenLANE flow and generate necessary outputs.
--

### Understanding the `run_placement` Command in OpenLANE

Once synthesis and floorplanning are complete, the next step in the physical design flow is **placement**, where standard cells are placed onto legal rows within the die area.

---

#### 🔧 Command to Run Placement

```tcl
run_placement
```

This command initiates **congestion-aware placement** in OpenLANE. It consists of two key sub-steps:

---

###  1. Global Placement

**Global placement** is the first stage of the placement process.

**Purpose:**

* Places cells in approximate locations to minimize wirelength and congestion.
* Ignores legal row boundaries (non-overlapping but not legally aligned).

**Tools involved:**

* OpenROAD's `RePlAce` or `gp` engine is used for global placement.

**Key goals:**

* Minimize half-perimeter wirelength (HPWL).
* Reduce routing congestion.
* Optimize placement density.

---

###  2. Detailed Placement

**Detailed placement** follows global placement.

**Purpose:**

* Adjusts and finalizes cell locations to legal positions within placement rows.
* Ensures no overlaps, obeys design rules, and aligns cells with row sites.

**Tools involved:**

* OpenROAD's `dp` engine or `open_dp` tool.

**Key goals:**

* Legalize all cells.
* Optimize local density and timing.
* Ensure design-rule correctness.

---

screenshots :

This is how we will get when placemnt is done !

![Image](https://github.com/user-attachments/assets/505fa9d2-b697-4ecf-b0c5-ae08b84a5773)

2.Load the generated placement DEF in Magic tool and explore the placement.
-
### Commands to Load Placement DEF in Magic (from a New Terminal)

Use the following steps to load and explore the **placement DEF** file for the `picorv32a` design using Magic.

---

#### 1. Navigate to the Placement Output Directory

```bash
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/21-06_17-40/results/placement/
```

This directory contains the `picorv32a.placement.def` file generated after running the placement stage.

---

#### 2. Launch Magic with Merged LEF and Placement DEF

```bash
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech \
      lef read ../../tmp/merged.lef \
      def read picorv32a.placement.def &
```

**Explanation of the command:**

* `-T` specifies the technology file for Magic (Sky130A).
* `lef read` loads macro and cell definitions from the merged LEF.
* `def read` loads the placed standard cell layout.
* The trailing `&` launches Magic in the background.

---

After executing these commands, Magic will open a GUI window displaying the placed standard cells inside the core area. You can zoom, inspect rows, and check for overlaps or alignment issues.




  screenshots :

  Placement def in magic :
  
![Image](https://github.com/user-attachments/assets/4d45b2c3-8fad-4799-a645-e0f8f5b77d42)

Standard cells legally placed:

![Image](https://github.com/user-attachments/assets/04b0380a-3166-4ab2-8529-223c084b61ef)


    
  </details>
  </details>

  <details>
<summary><b>Topic 3</b>Cell Design and Characterization Flow </summary>   
<br>

We have the placement and routed version of the chip .If we pick up the cells over the chip ,these cells are called Standard Cells.
These Standard Cells are placed in Library

![Screenshot 2024-10-08 151247](https://github.com/user-attachments/assets/63773f7e-7c1e-4a71-ad1c-723314934253)

![Screenshot 2024-10-08 152139](https://github.com/user-attachments/assets/b2875f55-1b97-4c45-bff8-b15f8dbb6d4a)

Library has different gates with different functionality but also got different cells with different sizes.These are the physical characterization of the cells

![Screenshot 2024-10-08 152205](https://github.com/user-attachments/assets/c239416c-d64e-4b17-8aae-3dea4e15522c)
If we take a particular cell lets take an inverter it has different threshold voltages and take more time to .

Cell Design Flow
---
Cells design flow has three steps 

![Screenshot 2024-10-08 152220](https://github.com/user-attachments/assets/62b5ead3-5e95-414a-a2e9-760eb07857ac)

Inputs:
--
Foundary provides PDKS it consists of DRC AND LVS rules and Spice models 

![Screenshot 2024-10-08 152245](https://github.com/user-attachments/assets/0c241abc-9fa5-472f-9560-84dbf15cd642)
![Screenshot 2024-10-08 152307](https://github.com/user-attachments/assets/e8be5bec-5708-48de-9e94-692ebbc1feea)

Library and User designer Specs :

![Screenshot 2024-10-08 190908](https://github.com/user-attachments/assets/c33031eb-5784-4365-9a61-9e8a7707c6ad)

![Screenshot 2024-10-08 190929](https://github.com/user-attachments/assets/51ccdad7-dfa5-4756-96d2-197219c02440)

Design Step :
--
i)Circuit-Design:

Using the input we will design cells
It has two steps :
i)Implement the functionality of the cell
ii)modal the pmos and cmos transistor based on requriments 

![Screenshot 2024-10-08 190959](https://github.com/user-attachments/assets/1af80b77-e364-441b-a356-3950bcfe5d39)

ii) Layout -Design:
 1) In layout Design,we do implementation of function using pmos and nmos 

![Screenshot 2024-10-08 191012](https://github.com/user-attachments/assets/def6784f-3ede-466a-aa43-a1cb2913f6c6)

 2) To derive the pmos and n mos graph using EULIER'S PATH

Eulier's Path:
The path that is traced only once

![Screenshot 2024-10-08 191036](https://github.com/user-attachments/assets/a82cb941-091a-4d78-b31a-a424fd63cbfe)

The next step is Draw the stick Diagram ,based on the circuit we connect the stick diagram


![Screenshot 2024-10-08 191047](https://github.com/user-attachments/assets/548816b4-1394-4eea-afd9-b749d7dd724a)

![Screenshot 2024-10-08 191107](https://github.com/user-attachments/assets/7f0959ba-c2a7-41ea-8aab-ded0538b3f9a)

![Screenshot 2024-10-08 191131](https://github.com/user-attachments/assets/2779c00c-6a65-4c99-8090-a731fa70ac62)

Characterization Flow:
--
We have layout of the buffer and two inverters connected back to back along with pulses and spice netlist

![Screenshot 2024-10-08 191220](https://github.com/user-attachments/assets/a62ca7a5-ee45-48ad-a6cd-b0e99d461e8a)

It has sub circuit model in which actual pmos and n mos specifications are present.In sub circuits we have spice models.

![Screenshot 2024-10-08 191245](https://github.com/user-attachments/assets/09c5d033-5bd9-458c-adfe-0365838730a6)

Charachterization flow:
 1) Reading the models and tech files
 2) Read the extracted spice netlist
 3) Define or recognize the behaviour of buffer
 4) read the sub circuits of inverter
 5) Attach the necessary power supply
 6) Applying the stimulus
 7) Necessary putput capacitors
 8) Necessary simulation commands

These steps are feed in characterization software called GUNA and we generate Timing noise ,Power.libs etc.,

![Screenshot 2024-10-08 191300](https://github.com/user-attachments/assets/5d5f3009-c7fb-4aa0-8afa-3d686972f4af)



  </details>


<details>
<summary><b>Topic 4</b>General timing characterization parameters </summary>   
<br>
Timming characterization:
--

characheterization setup:

![Screenshot 2024-10-08 193549](https://github.com/user-attachments/assets/ce43528f-51fd-414b-98de-66da2c70e150)

Timing threshold definations are reffered as points of different theshold of waveform . 

To understand the different syntax we take this graph:

BLUE- output of inverter 1 and input to inverter 2
RED- output of the buffer

Slow_low_rise_thr: it depicts value close near to zero . The typical value is 20%

![Screenshot 2024-10-08 193610](https://github.com/user-attachments/assets/ca565b60-3563-47fc-a357-98ded214870b)

Slow_high_rise_thr: it depicts value close to top power supply . The typical value is 20%

![Screenshot 2024-10-08 193622](https://github.com/user-attachments/assets/1df74a99-68e6-4685-a910-e9b9d73da91c)

similar for falling waveform:

![Screenshot 2024-10-08 193653](https://github.com/user-attachments/assets/12e56001-f785-4396-8785-97f88b9e3e40)

in_rise_thr: typicaly 50%
in-RED
out-BLUE

![Screenshot 2024-10-08 193718](https://github.com/user-attachments/assets/d57e58a3-8303-4bd9-bb50-0831d57ba2e5)

![Screenshot 2024-10-08 193748](https://github.com/user-attachments/assets/8a828dfa-3581-49c1-bdf7-af1a0e00800b)

simmilarly for falling wave form:
![Screenshot 2024-10-08 193800](https://github.com/user-attachments/assets/5852c4e3-24bb-4170-b1c6-f7d91c64fe03)
![Screenshot 2024-10-08 193811](https://github.com/user-attachments/assets/101a104a-2a46-431e-b1ab-835881378588)


Propogation Delay:
---

The difference between out threshold and input threshold is known as propogation delay 

![Screenshot 2024-10-08 195308](https://github.com/user-attachments/assets/4dd00af9-6a31-456f-b2b5-454ed4b1f449)

Example:
-

![Screenshot 2024-10-08 195344](https://github.com/user-attachments/assets/46c907e9-1c4d-419f-92da-81fed1a74bc3)

Transition time:
--
![Screenshot 2024-10-08 195532](https://github.com/user-attachments/assets/34457052-5d4e-4470-8c3d-c4d9c053e918)

  </details>

</details>

<details>
<summary><b>Day 3:</b> Design library cell using Magic Layout and ngspice characterization </summary>   
<br>
 
 <details>
<summary><b>Topic 1:</b> Labs for CMOS inverter ngspice simulations  </summary>   
<br>
 Task :

- Clone custom inverter standard cell design from github repository: Standard cell design and characterization using OpenLANE flow.
- Load the custom inverter layout in magic and explore.

1.Clone custom inverter standard cell design from github repository: Standard cell design and characterization using OpenLANE flow
-

### Steps to View Custom Inverter Layout in Magic (sky130)

This guide walks through loading a custom standard cell layout, specifically an **inverter**, using Magic with the Sky130 technology. These steps are often used in custom cell design and verification workflows.

---

#### 1. Change to the OpenLANE Working Directory

```bash
cd Desktop/work/tools/openlane_working_dir/openlane
```

This is your base directory where tools and design flows (like OpenLANE) are set up.

---

#### 2. Clone the Standard Cell Design Repository

```bash
git clone https://github.com/nickson-jose/vsdstdcelldesign
```

Clones a GitHub repo that contains layout files (e.g., `.mag` files) for custom-designed standard cells including the inverter.

---

#### 3. Navigate to the Cloned Repository

```bash
cd vsdstdcelldesign
```

Moves into the newly cloned project directory containing the layout files.

---

#### 4. Copy the Magic Tech File

```bash
cp /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech .
```

This command copies the Sky130 Magic technology file into the current directory for convenience. It's needed to view the layout correctly in Magic.

---

#### 5. Check for Required Layout Files

```bash
ls
```

List the directory contents to confirm that layout files (like `sky130_inv.mag`) and the copied tech file are present.

Expected output includes:

* `sky130_inv.mag`
* `sky130A.tech`
* Possibly `.spice`, `.lef`, or `.gds` files if included in the repo.

---

#### 6. Open the Layout in Magic

```bash
magic -T sky130A.tech sky130_inv.mag &
```

This launches Magic using the specified Sky130 technology file and loads the custom inverter layout (`sky130_inv.mag`).

**In the Magic GUI**, you can:

* Zoom and pan across the layout
* Inspect each layer (poly, diffusion, metal, contacts)
* Check for DRC (Design Rule Check) violations

---

Screenshots of these running :

Git cloning :

![Image](https://github.com/user-attachments/assets/a73936a6-df2b-459a-877e-779361e7cb7b)

![Image](https://github.com/user-attachments/assets/95e739fe-a66d-4863-ab94-b9934a0d064c)





2.Load the custom inverter layout in magic and explore.
--

screenshots of the inverter in magic :-
 1.inverter

![Image](https://github.com/user-attachments/assets/c8c41cdf-4ae1-4c14-aa08-fc73f8b0be88)

 2. nmos

![Image](https://github.com/user-attachments/assets/97c0517e-e6c9-411c-bf3f-1c1d727c1322)

 3. nwell

![Image](https://github.com/user-attachments/assets/7d75ca6f-b943-473c-bdbd-35ab4868ed73)

 4.pmos

![Image](https://github.com/user-attachments/assets/046fbfac-7866-4153-8d4e-f417a73b5f19)

 5.poly
![Image](https://github.com/user-attachments/assets/315e79c6-12c9-4a51-8aa7-b69a410b2806)

 6.Topmost cell
![Image](https://github.com/user-attachments/assets/e8b97eae-0463-4a7b-a009-dc0aea32a4ca)

  </details>  

 <details>
<summary><b>Topic 2:</b> Spice extraction of inverter in magic.  </summary>   
<br>
Task :
   
- Spice extraction of inverter in magic.

 ### Commands for SPICE Extraction of Custom Inverter Layout in Magic (via tkcon)

To perform SPICE extraction of a custom layout (inverter) using Magic, the following commands are executed in the **tkcon window** of the Magic GUI after loading the layout.

---

#### 1. Confirm Current Directory

```tcl
pwd
```

Prints the current working directory to ensure Magic is operating in the folder where the layout (`.mag`) file resides. This is also where the `.ext` and `.spice` files will be saved.

---

#### 2. Extract Layout into .ext Format

```tcl
extract all
```

* Extracts device and connectivity information from the loaded layout.
* Generates a `.ext` file (Magic's internal format for circuit extraction).

---

#### 3. Enable Parasitic Resistance and Capacitance Extraction

```tcl
ext2spice cthresh 0 rthresh 0
```

* `cthresh 0` enables **all capacitances**, including parasitics.
* `rthresh 0` enables **all resistances**, allowing RC-aware simulation.

---

#### 4. Generate SPICE Netlist

```tcl
ext2spice
```

* Converts the extracted `.ext` file into a `.spice` netlist.
* Output is usually saved as `sky130_inv.spice` (or based on the `.mag` file name).

---

screenshots of tkcon window :

![Image](https://github.com/user-attachments/assets/9562842e-f5e0-4343-8260-45587c571728)

screenshot of the spice file :

![Image](https://github.com/user-attachments/assets/ba70066a-0305-4f60-aa89-81f05a6cb8b0)

 </details>   


<details>
<summary><b>Topic 3:</b> sky130 Tech file Labs  </summary>   
<br>

Tasks :
-  Editing the SPICE model file for analysis through simulation.
-  Performing post-layout ngspice simulations.
-  Identifying and fixing issues in the DRC section of the old Magic tech file for the SkyWater process.

1.Editing the SPICE model file for analysis through simulation.
--

Measuring unit distance in layout grid 

![Image](https://github.com/user-attachments/assets/d67aba33-8abb-4eef-a82c-c67ea5433623)

Final edited spice file for ngspice simulation :

![Image](https://github.com/user-attachments/assets/0eac6a1a-85b2-418f-b68f-12f47561a070)



2.Performing post-layout ngspice simulations.
--

commands to run ngspice :

#### 1. Perform Post-Layout SPICE Simulation with ngspice

```bash
ngspice sky130_inv.spice
```

This command launches the ngspice terminal and loads the specified SPICE file for simulation.

Inside the ngspice prompt, use the following to plot signals:

```bash
plot y vs time a
```

Where:

* `y` is the output signal node (e.g., V(out)).
* `a` represents time or an input node.

![Image](https://github.com/user-attachments/assets/f757edd9-7cad-4fa1-8f20-19029275a56b)


output :

![Image](https://github.com/user-attachments/assets/60dc3a09-be0f-4c04-8814-ed6c59197fde)

Rise time calculations :
-


The **rise transition time** (also called **rise time**, **tr**)
measures how long an output signal takes to move from 20 % to 80 % of its final value.

---

#### Formula

```
Rise transition time (tr) = T(80 %) − T(20 %)
```

* **T(20 %)** – the timestamp when the output first crosses 20 % of V<sub>DD</sub>.
* **T(80 %)** – the timestamp when the output first crosses 80 % of V<sub>DD</sub>.

For a 3.3 V supply:

* 20 % × 3.3 V = **0.660 V**
* 80 % × 3.3 V = **2.640 V**

---

#### Example Measurement

| Parameter | Value          |
| --------- | -------------- |
| T(20 %)   | **2.11938 ns** |
| T(80 %)   | **2.17953 ns** |

```
tr = 2.217953 ns − 2.11938 ns = 0.06015 ns = 60.1 ps
```

So the **rise transition time** for this inverter output is **≈ 60.1 ps**.

screenshots :-


20% :

![Image](https://github.com/user-attachments/assets/76f0ed03-acaa-4419-bf3d-794007806b19)

![Image](https://github.com/user-attachments/assets/3286494f-078e-497f-a924-f2fb697ad720)


80% :

![Image](https://github.com/user-attachments/assets/91a38934-ee3b-452e-bc78-55990cf16b0d)


![Image](https://github.com/user-attachments/assets/7e28ba8a-3198-442b-9bd9-16f7db818baa)

2.Fall Transition Time Calculation
-

The **fall transition time** (also called **fall time**, **tf**) measures how long an output signal takes to fall from 80% to 20% of its final value.

---

#### Formula

```
Fall transition time (tf) = T(20%) − T(80%)
```

* **T(80%)** – the timestamp when the output starts falling below 80% of V<sub>DD</sub>.
* **T(20%)** – the timestamp when the output crosses below 20% of V<sub>DD</sub>.

For a 3.3 V supply:

* 20% × 3.3 V = **0.660 V**
* 80% × 3.3 V = **2.640 V**

---

#### Example Measurement (Fall)

| Parameter | Value         |
| --------- | ------------- |
| T(80%)    | **4.05 ns** |
| T(20%)    | **4.0961 ns** |

```
tf = 4.0961 ns − 4.05 ns = 0.0461 ns = 46.1 ps
```

So the **fall transition time** for this inverter output is **≈ 46.1 ps**.

screenshots :

20% :

![Image](https://github.com/user-attachments/assets/e2d0963f-f7cc-431a-ad4f-c5594de0d132)

![Image](https://github.com/user-attachments/assets/130e582b-1a98-46b0-b515-caf88f424bd8)

80% :

![Image](https://github.com/user-attachments/assets/9da807a0-bb6c-4777-81e5-aebc21fc9376)

![Image](https://github.com/user-attachments/assets/4bad5084-5af9-438d-a6fc-2fe877b7d01b)

3.Rise Cell Delay Calculation
-

The **rise cell delay** (also called **propagation delay high**, **tp<sub>LH</sub>**) measures the time from the input’s falling transition (50 % level) to the output’s rising transition (50 % level).

---

#### Formula

```
Rise cell delay (tpLH) = T_output(50 % rising) − T_input(50 % falling)
```

* **T\_input(50 % falling)** – timestamp when the input signal falls through 50 % of V<sub>DD</sub>.
* **T\_output(50 % rising)** – timestamp when the output signal rises through 50 % of V<sub>DD</sub>.

For a **3.3 V** supply, **50 % × 3.3 V = 1.65 V**.

---

#### Example Measurement

| Parameter               | Value          |
| ----------------------- | -------------- |
| T\_input (50 % falling) | **2.14986 ns** |
| T\_output (50 % rising) | **2.21043 ns** |

```
tpLH = 2.21043 ns − 2.14986 ns = 0.06057 ns = 60.5 ps
```

So the **rise cell delay** for this inverter is **≈ 60.5 ps**.

screenshots :

50%:

![Image](https://github.com/user-attachments/assets/26be035b-c910-496f-ab24-17d980b4cbc6)

![Image](https://github.com/user-attachments/assets/4fcab278-073c-4a5b-9602-6023701f1578)

4.Fall Cell Delay Calculation
-

The **fall cell delay** (also called **propagation delay low**, **tp<sub>HL</sub>**) measures the time from the input’s rising transition (50 % level) to the output’s falling transition (50 % level).

---

#### Formula

```
Fall cell delay (tpHL) = T_output(50 % falling) − T_input(50 % rising)
```

* **T\_input (50 % rising)** – timestamp when the input signal rises through 50 % of V<sub>DD</sub>.
* **T\_output (50 % falling)** – timestamp when the output signal falls through 50 % of V<sub>DD</sub>.

For a **3.3 V** supply, **50 % × 3.3 V = 1.65 V**.

---

#### Example Measurement

| Parameter                | Value       |
| ------------------------ | ----------- |
| T\_input (50 % rising)   | **4.04943 ns** |
| T\_output (50 % falling) | **4.0777 ns** |

```
tpHL = 4.0777 ns − 4.04943 ns = 0.02827 ns = 28.27 ps
```

So the **fall cell delay** for this inverter is **≈ 28.27 ps**.

screenshots:

50%:

![Image](https://github.com/user-attachments/assets/fb83f9f0-430d-4b9e-a8fe-08acc8376a97)

![Image](https://github.com/user-attachments/assets/cb3d4482-0c57-4a03-b698-b7523b8fdc32)




3.Identifying and fixing issues in the DRC section of the old Magic tech file for the SkyWater process
-


### DRC Debugging and Correction for Sky130 Magic Tech File

This guide walks you through downloading, extracting, and inspecting a corrupted SkyWater process DRC test setup in Magic for the purpose of fixing design rule violations.

---

####  Sky130 Periphery Rules Documentation

To understand the design rules that may require fixing:

* [Sky130 Periphery Rules](https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html)

---

#### 1. Change to Home Directory

```bash
cd
```

Switch to the home directory to begin work in a clean and known location.

---

#### 2. Download DRC Lab Files

```bash
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
```

Downloads a tarball archive containing test designs and configuration files for exploring and debugging DRC issues in the SkyWater process tech.

---

#### 3. Extract the Downloaded Archive

```bash
tar xfz drc_tests.tgz
```

Extracts the compressed `.tgz` file into a folder named `drc_tests` with all associated files.

---

#### 4. Navigate into the Extracted Folder

```bash
cd drc_tests
```

This is the working directory containing layout files, `.magicrc`, and potentially broken or outdated tech file references.

---

#### 5. List All Files in the Directory

```bash
ls -al
```

Verifies that expected files like layout (`*.mag`), config files (`.magicrc`), and perhaps a local copy of `sky130A.tech` are present.

---

#### 6. Open and Inspect the .magicrc File

```bash
gvim .magicrc
```

Opens the Magic configuration file in GVim to review tech file paths, layer settings, and rule load commands. You can update the `.magicrc` to use a corrected or updated version of `sky130A.tech` here.

---

#### 7. Launch Magic with X Rendering Backend

```bash
magic -d XR &
```

Starts Magic with improved graphics using the XRender backend, useful for more responsive DRC rule debugging and layout inspection.

---
screenshots of these commands running :

![Image](https://github.com/user-attachments/assets/9e4c127c-91c7-4a94-8ba2-bddddb352756)

screenshot of poly rules :

![Image](https://github.com/user-attachments/assets/e8227f69-c51b-4f8c-9efa-6d30fb594446)

1.incorrectly implemented poly.9 rule , no drc violation even though spacing <0.48u

![Image](https://github.com/user-attachments/assets/020d7fbd-f897-441b-ab46-c1d3e2024269)

![Image](https://github.com/user-attachments/assets/d0f71314-45eb-4e09-920c-0809e777a1c4)

![Image](https://github.com/user-attachments/assets/ed91003a-bfab-4561-bc1a-fdee181614f5)


### DRC Check with Updated Tech File in Magic

Use the following commands in the Magic layout tool after editing or correcting the technology file (e.g., `sky130A.tech`) to reload the settings and re-evaluate DRC errors.

---

#### 1. Load the Updated Tech File

```tcl
tech load sky130A.tech
```

This command reloads the modified technology file so that new DRC rules or fixes take effect.

---

#### 2. Run DRC Check

```tcl
drc check
```

This re-executes the design rule checking based on the loaded technology file. Any rule violations are reported in the layout window.

---

#### 3. View DRC Error Details

```tcl
drc why
```

Select a region in the layout where DRC errors are marked, then run this command to display textual descriptions of the rule violations.

---

2.incorrectly implemented of poly.2

![Image](https://github.com/user-attachments/assets/14e3adbb-ed15-426d-af0f-a86cb9fa3338)

### DRC Check with Updated Tech File in Magic

Use the following commands in the Magic layout tool after editing or correcting the technology file (e.g., `sky130A.tech`) to reload the settings and re-evaluate DRC errors.

---

#### 1. Load the Updated Tech File

```tcl
tech load sky130A.tech
```

This command reloads the modified technology file so that new DRC rules or fixes take effect.

---

#### 2. Run DRC Check

```tcl
drc check
```

This re-executes the design rule checking based on the loaded technology file. Any rule violations are reported in the layout window.

---

#### 3. View DRC Error Details

```tcl
drc why
```

Select a region in the layout where DRC errors are marked, then run this command to display textual descriptions of the rule violations.

---


3.incorrectly implemented nwell.4 rule no drc violation even though no tap present in nwell

![Image](https://github.com/user-attachments/assets/07c14319-72a5-43b9-acc8-2e1ac660f9fc)  

![Image](https://github.com/user-attachments/assets/f0a80fc1-b805-4d95-bf67-1102c5a38ae7)

![Image](https://github.com/user-attachments/assets/084b3c1a-1c36-4a8d-8b31-6365e0696615)


### DRC Check with Updated Tech File in Magic

After modifying the Sky130 technology file (`sky130A.tech`), reload it and run a full DRC pass to verify the fixes.

---

#### 1. Load the Updated Tech File

```tcl
tech load sky130A.tech
```

Reloads the edited technology file so the new rule definitions are active.

---

#### 2. Enable Full DRC Rule Set

```tcl
drc style drc(full)
```

Switches Magic to the **full DRC** style, ensuring that **all** design rules (including normally off or advisory checks) are evaluated.

---

#### 3. Run DRC Check

```tcl
drc check
```

Executes DRC with the full rule set, marking any violations on the layout.

---

#### 4. Inspect Specific Errors

```tcl
drc why
```

After clicking a highlighted error region, this command prints the rule description and coordinates, helping you understand the violation.
 
</details>   

 
</details>  
<details>
<summary><b>Day 4:</b> Pre-layout timing analysis and importance of good clock tree </summary>   
<br>

Tasks:-
1. **Fix small DRC errors** and verify the design is ready to be inserted into the flow.  
2. **Save the finalized layout** with a custom name and reopen it.  
3. **Generate a LEF** file from the layout.  
4. **Copy the new LEF** (and any required `.lib` files) into the `picorv32a/src` directory.  
5. **Edit `config.tcl`** to reference the new library file and include the extra LEF in the OpenLane flow.  
6. **Run OpenLane synthesis** with the newly inserted custom inverter cell.  
7. **Reduce or eliminate new violations** introduced by the custom inverter by tweaking design parameters.  
8. After synthesis accepts the custom inverter, **run floorplan and placement** to confirm the cell is integrated in the P & R flow.  
9. **Perform post-synthesis timing analysis** using OpenSTA.  
10. **Apply timing ECO fixes** to clear any remaining timing violations.  
11. **Replace the old netlist** with the ECO-fixed netlist and rerun floorplan, placement, and CTS.  
12. **Run post-CTS timing analysis** in OpenROAD.  
13. **Investigate post-CTS timing** further by removing `sky130_fd_sc_hd__clkbuf_1` from `CTS_CLK_BUFFER_LIST` and re-analyzing.


1.**Fix small DRC errors** and verify the design is ready to be inserted into the flow.  
-

### Conditions to Verify Before Using a Custom Designed Standard Cell

Before integrating your custom standard cell (e.g., inverter) into the OpenLane flow, **ensure the following conditions are satisfied**:

1. **Port Alignment**  
   ➤ *The input and output ports of the standard cell should lie on the intersection of the vertical and horizontal tracks.*

2. **Cell Width**  
   ➤ *The width of the standard cell must be an **odd multiple** of the horizontal track pitch.*

3. **Cell Height**  
   ➤ *The height of the standard cell must be an **even multiple** of the vertical track pitch.*

These conditions are essential to ensure **DRC-clean layouts** and **proper integration with placement and routing tools**.

---

### Commands to Open the Custom Inverter Layout in Magic

```bash
# Step 1: Change directory to your standard cell design location
cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign

# Step 2: Launch Magic layout editor with the sky130A technology file
magic -T sky130A.tech sky130_inv.mag &
```

- `sky130A.tech`: Technology file for SkyWater 130nm PDK
- `sky130_inv.mag`: Magic layout file of the custom inverter
- `&`: Runs Magic in the background so you can still use the terminal

---

### Screenshot: `tracks.info` of `sky130_fd_sc_hd`:

tracks.info :

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/cfcf34f3-4299-4e38-a9ad-05a5716c9a2a" />

condition 1verified :

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/fb78055e-43a5-4542-841d-644409d72399" />

condition 2 verified:

<img width="955" height="925" alt="Image" src="https://github.com/user-attachments/assets/34df0964-7bae-4f6a-81fd-a7db4e6a059f" />


condition 3 verified :

<img width="1920" height="937" alt="Image" src="https://github.com/user-attachments/assets/70e0bf0c-36ac-4f5f-b91d-502cb680a906" />


layout :

<img width="1920" height="937" alt="Image" src="https://github.com/user-attachments/assets/bb4cba53-7718-4851-a659-1088ad8b54c0" />




###  Commands to Set Grid as Tracks of Locali Layer in Magic (via tkcon)

```tcl
# Step 1: Start Magic and open your layout
magic -T sky130A.tech sky130_inv.mag &
```

```tcl
# Step 2: Open tkcon window inside Magic (if not already visible)
# From Magic console, type:
tkcon
```

```tcl
# Step 3: Get help on grid command syntax
help grid
```

```tcl
# Step 4: Set grid to match the tracks of the locali (local interconnect) layer
# Format: grid <Xgrid> <Ygrid> <Xorigin> <Yorigin>
grid 0.46um 0.34um 0.23um 0.17um
```

---

- `grid`: Command to set or display the snap grid for layout editing.
- `0.46um`: Grid pitch along the X-axis (horizontal track spacing of locali layer).
- `0.34um`: Grid pitch along the Y-axis (vertical track spacing of locali layer).
- `0.23um`: X origin offset to align grid with locali layer's track origin.
- `0.17um`: Y origin offset to align grid with locali layer's track origin.


<img width="1920" height="937" alt="Image" src="https://github.com/user-attachments/assets/f11ed701-2bb7-4d29-9b43-9d3180239fd6" />




2.**Save the finalized layout** with a custom name and reopen it.  
-


command for tkon window to save the layout with custom name 

###  Command to Save the Layout with Custom Name

```tcl
# Save the current layout with a new name
save sky130_vsdinv.mag
```

---

###  Command to Open the Newly Saved Layout

```bash
# Open the custom inverter layout in Magic using the saved file
magic -T sky130A.tech sky130_vsdinv.mag &
```

- `save sky130_vsdinv.mag`: Saves the current layout with the custom name.
- `magic -T sky130A.tech sky130_vsdinv.mag &`: Opens the newly saved layout in Magic.

screenshots of newly saved layout :

<img width="955" height="925" alt="Image" src="https://github.com/user-attachments/assets/2a2acf7f-3d75-4fdc-a545-036833c8c1bf" />



3.**Generate a LEF** file from the layout.  
--

### ℹ What is a LEF?

- **LEF** stands for **Library Exchange Format**.
- It provides a lightweight, abstract description of a standard‑cell or macro layout, including:
  - Cell boundary and obstruction boxes
  - Pin locations, shapes, and layers
  - Technology routing layers, direction, pitch, and spacing
- Because LEF omits detailed transistor geometry (present in GDS), it is efficient for place‑and‑route (P&R) tools during floor‑planning, placement, and routing.
- P&R engines read LEF to ensure cells align to legal tracks and that routing honors design rules.
- After placement and routing, a detailed GDS (or DEF) file is output for sign‑off verification and mask generation.

### Command to Generate a LEF File from the Layout (tkcon)

```tcl
# Write a LEF view of the current layout
lef write
```
screenshots of command run :


<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/08b7e4c0-409f-429e-9124-ff14a1c21dae" />



4.**Copy the new LEF** (and any required `.lib` files) into the `picorv32a/src` directory.  
--

### Commands to Copy Necessary Files into `picorv32a/src`

```bash
# Copy the LEF file for the custom inverter
cp sky130_vsdinv.lef ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

# Verify that the LEF file was copied
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

# Copy Liberty (.lib) timing libraries for Sky130 HD cells
cp libs/sky130_fd_sc_hd__* ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

# Verify that the .lib files were copied
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
```

---

**Why these steps?**
- `cp sky130_vsdinv.lef …`: Places the cell’s abstract physical view where OpenLane can find it during floor‑planning and routing.
- `cp libs/sky130_fd_sc_hd__* …`: Adds timing libraries so synthesis and STA stages recognize the cell.
- `ls …`: Quick sanity check to confirm files landed in the correct directory.


screenshots of command run:

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/36e56c15-ad38-4497-bb89-a00c1c5fb250" />   


5.**Edit `config.tcl`** to reference the new library file and include the extra LEF in the OpenLane flow.  
--

### Commands to Update `config.tcl` to Include Custom Cell in OpenLane Flow

```tcl
# Set custom Liberty files for synthesis and STA
set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

# Include additional LEF files from the src directory
set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]
```

---

###  Explanation
- These `set` commands ensure that OpenLane uses the updated `.lib` files for synthesis and timing analysis.
- `EXTRA_LEFS` allows OpenLane to recognize and utilize additional LEF files, like your custom inverter, during floorplanning and placement.

screenshots of command run:

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/52015792-feed-4f20-9a23-351911ad897d" />

6.**Run OpenLane synthesis** with the newly inserted custom inverter cell.  
-

### Commands to Invoke OpenLane Flow, Include New LEF, and Run Synthesis

```bash
# Change to the OpenLane flow directory
cd ~/Desktop/work/tools/openlane_working_dir/openlane

# Launch the OpenLane Docker container (alias 'docker' already set up)
docker

# Inside the container, start OpenLane in interactive mode
./flow.tcl -interactive
```

```tcl
# Load the OpenLane Tcl package
package require openlane 0.9

# Prepare the 'picorv32a' design (creates run directory, copies sources, etc.)
prep -design picorv32a

# Add all LEF files from the design's src directory (includes custom cell)
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Run synthesis
run_synthesis
```

---

- Step 1–3: Enter the OpenLane Docker environment and launch the interactive Tcl shell.
- Step 4: Ensures the correct OpenLane version is loaded.
- Step 5: Generates the working directories (`runs/`), copies sources, and sets up config files.
- Step 6: Dynamically includes all `.lef` files in `src/`, so your custom inverter is recognized during floor-planning.
- Step 7: Executes the synthesis stage (Yosys and OpenROAD flow synthesis), producing a synthesized netlist and initial timing reports.

After synthesis completes, you can proceed with `run_floorplan`, `run_placement`, `run_cts`, `run_routing`, or simply call `run_flow` to execute the entire RTL-to-GDSII flow.

Screenshots of commands run :

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/a9a660ad-53d3-4718-9ad3-0cbe792dbaac" />

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/f6a9ad25-6b54-4e1c-8fd6-f24461eb9056" />

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/151d90d9-1a06-4691-84ab-c879e90ecc5a" />
 
7.**Reduce or eliminate new violations** introduced by the custom inverter by tweaking design parameters.  
--


Noting down current design values generated before modifying parameters to improve timing

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/1d35b7b7-40fc-43b3-bf04-8a89e65d0de0" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/30bcba4d-229b-4487-b00d-8a2a2c44a0a0" />



### Commands to Adjust Synthesis Parameters for Timing Optimization

```bash
# Re‑prepare the design to update variables
prep -design picorv32a -tag 21-06_17-40 -overwrite
```

```tcl
# Add all LEF files from the design's src directory (includes merged.lef and custom cells)
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Display the current synthesis strategy
echo $::env(SYNTH_STRATEGY)

# Set a timing‑driven synthesis strategy
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Check whether buffering is enabled
echo $::env(SYNTH_BUFFERING)

# Display current sizing setting
echo $::env(SYNTH_SIZING)

# Enable gate sizing during synthesis
set ::env(SYNTH_SIZING) 1

# Verify the selected driving cell
echo $::env(SYNTH_DRIVING_CELL)

# Run synthesis with the updated parameters
run_synthesis
```

---

- The `prep` command with `-overwrite` regenerates the run directory while preserving updated configuration values.
- `DELAY 3` directs Yosys to target a more aggressive delay optimization point (higher number tightens timing).
- Enabling `SYNTH_SIZING` allows size‑up for critical paths during synthesis.
- Buffering can be toggled via `SYNTH_BUFFERING`; viewing its value helps decide if additional buffers are required.
- Running `run_synthesis` produces a new synthesized netlist reflecting these timing‑oriented settings.

Screenshot of merged.lef in tmp directory with our custom inverter as macro

<img width="955" height="925" alt="Image" src="https://github.com/user-attachments/assets/8a3414af-7103-494e-9ae7-28d0390236d0" />


Screenshots of commands run

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/b96d4b0c-82cf-482b-b077-0bbee2498324" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/770eeabd-e59c-48da-a325-6d07e6de6021" />

Comparing to previously noted run values area has increased and worst negative slack has become 0


8.After synthesis accepts the custom inverter, **run floorplan and placement** to confirm the cell is integrated in the P & R flow.  
---




### Commands to Run Floorplan and Placement

```tcl
# Attempt the floorplan stage
run_floorplan

# If run_floorplan reports an error, execute the sequence manually
init_floorplan
place_io
tap_decap_or
```
Screenshots of commands run

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/d431fe62-af37-4479-8a30-d78545f854a2" />

Screenshots of commands run

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/5182007b-7cd6-4474-bbb7-3f0c89069a2f" />


```tcl
# Run the placement stage
run_placement
```

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/1078182e-4272-43ff-879b-97cc166cd78c" />



---

### Viewing the Placement DEF in Magic

```bash
# Change to the placement results directory (replace with your current run tag if different)
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/21-06_17-40/results/placement/

# Load the placement DEF in Magic
magic -T ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech \
      lef read ../../tmp/merged.lef \
      def read picorv32a.placement.def &
```

---

### Explanation
- `run_floorplan` invokes the standard floor‑planning script. When it fails, the individual commands `init_floorplan`, `place_io`, and `tap_decap_or` reproduce the same sequence.
- `run_placement` performs global and detailed placement.
- The final commands open the generated DEF in Magic for visual inspection. Ensure the run tag (`21-06_17-40`) matches your current run directory.




Screenshot of placement def in magic

<img width="1440" height="732" alt="Image" src="https://github.com/user-attachments/assets/52f8f479-7820-454e-af49-9a6a4add7b9e" />

Screenshot of custom inverter inserted in placement def with proper abutment


<img width="1440" height="732" alt="Image" src="https://github.com/user-attachments/assets/caabd0db-9399-4c8e-b9aa-2d9c673e981d" />


### Viewing Internal Connectivity Layers in Magic

```tcl
# Command to expand internal geometry and show all connectivity layers
expand
```

- `expand`: This Magic command reveals all internal routing and connectivity details within the loaded layout. Useful for visually verifying routed nets or cell connections.


<img width="979" height="340" alt="Image" src="https://github.com/user-attachments/assets/3281e587-6642-4b99-8e79-22b423282f9d" />




9.**Perform post-synthesis timing analysis** using OpenSTA.  
--

### Baseline Synthesis Run for Initial Timing Analysis

This procedure prepares the *picorv32a* design in OpenLane, includes the custom LEF, performs a **minimal‑tuning** synthesis run, and produces timing reports that still contain violations. No aggressive timing parameters (such as `SYNTH_STRATEGY` or extra buffering) are applied—only gate sizing is enabled to obtain a realistic starting point.

```bash
# 1. Change to the OpenLane flow directory
cd ~/Desktop/work/tools/openlane_working_dir/openlane

# 2. Enter the OpenLane Docker container (the long command is aliased to 'docker')
docker

# 3. Inside the container, launch OpenLane in interactive mode
./flow.tcl -interactive
```

```tcl
# 4. Load the OpenLane Tcl package (version 0.9)
package require openlane 0.9

# 5. Prepare the 'picorv32a' design (creates the run directory and copies sources)
prep -design picorv32a

# 6. Add all LEF files from the design's src directory (includes custom inverter)
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# 7. Enable basic gate sizing
set ::env(SYNTH_SIZING) 1

# 8. Run synthesis (Yosys + OpenROAD synthesis)
run_synthesis
```

---

#### What Each Step Does
1. **Directory change**: Ensures subsequent commands execute in the OpenLane repo.
2. **`docker`**: Launches the pre‑configured OpenLane container with PDK mounts.
3. **`./flow.tcl -interactive`**: Opens the Tcl shell where OpenLane commands are entered.
4. **`package require openlane`**: Loads OpenLane Tcl helpers.
5. **`prep`**: Generates the `runs/<date>/` workspace, copies RTL and config files.
6. **`add_lefs`**: Registers your custom LEF so the tool recognises the new cell.
7. **`SYNTH_SIZING`**: Allows Yosys to upsise cells on critical paths during synthesis; no other timing knobs are changed.
8. **`run_synthesis`**: Produces the synthesised netlist and timing reports.

The timing reports for this baseline run will be written to:
```
\<run_tag\>/reports/synthesis/
```
Review `timing.rpt` or `openroad.sdc.rpt` to see worst negative slack (WNS) and total negative slack (TNS). These violations provide a reference before applying advanced timing optimisations.



### STA Configuration for Analysis

This procedure sets up the *picorv32a* design for baseline Static Timing Analysis (STA) using custom configuration files. These steps ensure that synthesis results (with known violations) are analyzed using user-defined constraints.

---

### Custom Files Used

- **`pre_sta.conf`** — placed in the OpenLane root directory
- **`my_base.sdc`** — placed in `openlane/designs/picorv32a/src/`, derived from `openlane/scripts/base.sdc`

These files allow you to:
- Define input/output delays
- Specify clock constraints
- Configure driving and load conditions
- Apply timing exceptions and false paths

---



```bash
# Change to the OpenLane flow directory
cd ~/Desktop/work/tools/openlane_working_dir/openlane

# Invoke OpenSTA with the custom configuration script
sta pre_sta.conf
```

The `pre_sta.conf` script loads the synthesized netlist and applies the timing constraints defined in `my_base.sdc`. Review the resulting reports for worst‑case slack, fanout, and critical path information.

---




To mitigate delay caused by excessive fanout, rerun synthesis with a tighter fanout limit.

```tcl
# Re‑prepare the design (overwrite previous run directory)
prep -design picorv32a -tag 21-06_17-40 -overwrite

# Add all LEF files from the design's src directory (includes custom cells)
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Enable gate sizing
set ::env(SYNTH_SIZING) 1

# Limit maximum fanout per net to 4
set ::env(SYNTH_MAX_FANOUT) 4

# Verify the selected driving cell
echo $::env(SYNTH_DRIVING_CELL)

# Run synthesis with the updated constraints
run_synthesis
```

After synthesis completes, compare the new timing reports in:
```
runs/21-06_17-40/reports/synthesis/
```
Key metrics to observe:
- Changes in worst negative slack (WNS)
- Reduction in total negative slack (TNS)
- Fanout values on previously critical nets


Screenshots of commands run

<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/46c31089-0f79-4bf6-a536-d5a9e5d3ac85" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/e8ff8659-64a8-4194-ac33-a1ddf5902b79" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/47dbb4b9-a83b-419f-8bd2-2b85d5e23c58" />

<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/54dbbad4-c68f-4e52-8ee6-a7e8ff898eb2" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/baf901a8-08d2-4445-b28f-9091ca40381b" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/20f96fb6-a92f-4883-9b2b-67629fb6d956" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/970cc0fb-8db1-4fac-a296-45749d868ee5" />




10.**Apply timing ECO fixes** to clear any remaining timing violations.  
--

OR gate of drive strength 2 is driving 4 fanouts



### Timing Optimization by Replacing Cell with OR Gate (Drive Strength 4)

```tcl
# Report all connections to a specific net
report_net -connections _10566_

# Check syntax and usage for cell replacement command
help replace_cell

# Replace an existing cell instance with a higher drive strength OR3 gate
replace_cell _13165_ sky130_fd_sc_hd__or3_4

# Generate a detailed timing report for analysis after replacement
report_checks -fields {net cap slew input_pins} -digits 4
```

---


- `report_net -connections <net>`: Identifies which cell instances are connected to the specified net.
- `replace_cell <instance> <new_cell>`: Substitutes the instance with a specified higher drive-strength variant to reduce delay.
- `report_checks`: Used to regenerate the STA report with specific fields for accurate timing evaluation.

screenshots of running commands:


<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/bb27a5ea-2a24-41ec-9d54-4b90141aa351" />

<img width="955" height="925" alt="Image" src="https://github.com/user-attachments/assets/58e9eac0-102a-4949-a13b-3e3302d94336" />


Result - slack reduced



OR gate of drive strength 2 driving OA gate has more delay


```tcl
# Report all connections to a specific net
report_net -connections _10543_

# Check syntax and usage for cell replacement command
help replace_cell

# Replace an existing cell instance with a higher drive strength OR3 gate
replace_cell _13132_ sky130_fd_sc_hd__or4_4

# Generate a detailed timing report for analysis after replacement
report_checks -fields {net cap slew input_pins} -digits 4
```


screenshots of running commands :



<img width="955" height="925" alt="Image" src="https://github.com/user-attachments/assets/58e9eac0-102a-4949-a13b-3e3302d94336" />



commands to perform analysis and optimize timing by replacing with OR gate of drive strngth of 4

commands :

```tcl
# Report all connections to a specific net
report_net -connections _10559_

# Check syntax and usage for cell replacement command
help replace_cell

# Replace an existing cell instance with a higher drive strength OR3 gate
replace_cell _13157_ sky130_fd_sc_hd__or4_4

# Generate a detailed timing report for analysis after replacement
report_checks -fields {net cap slew input_pins} -digits 4
```

screenshots :

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/cc6eaf44-74c0-4678-b99e-a5e48d489c0b" />

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/29ddbd2c-6b75-4f36-b9de-f79bd21ff937" />

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/e5ff840a-6950-4cad-92a5-c177429dfcb7" />

generating custom timing report :
--


<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/6c447300-f481-4f3d-91df-dc4f1efc8105" />





We started ECO fixes at wns -23.9000 and now we stand at wns -22.6173 we reduced around 1.2827 ns of violation.


11.**Replace the old netlist** with the ECO-fixed netlist and rerun floorplan, placement, and CTS.  
-


### Commands to Backup Original Netlist and Prepare for Updated Netlist Insertion

```bash
# Change from home directory to synthesis results directory
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/21-06_17-40/results/synthesis/

# List contents of the directory
ls

# Copy and rename the existing synthesis netlist
cp picorv32a.synthesis.v picorv32a.synthesis_old.v

# Confirm the copy
ls
```

Once the backup is complete, you can overwrite the original netlist from within OpenSTA using:

```tcl
# Save the updated netlist after optimizations
write_verilog picorv32a.synthesis.v
```

This updated netlist is now ready to be used in the next stages of the OpenLane flow such as floorplan, placement, and routing.

Screenshot of commands run


<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/86c3d5d5-2a74-418d-b8de-82975a9ba8be" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/1453a4d6-18e1-4dd3-8e47-104119a815ae" />


### Commands to Overwrite the Synthesis Netlist After Timing Optimization

```tcl
# Check the syntax and usage of the write_verilog command
help write_verilog

# Overwrite the existing synthesis netlist with the updated version
write_verilog /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/21-06_17-40/results/synthesis/picorv32a.synthesis.v

# Exit OpenSTA when timing analysis is complete
exit
```

These steps replace the original synthesized netlist with the optimized version and cleanly exit the OpenSTA session.


Screenshot of commands run


Verified that the netlist is overwritten :




### Commands to Continue Clean Design Flow with 0 Violation Baseline

```tcl
# Re-prepare the design to reload clean variables and LEFs
prep -design picorv32a -tag 21-06_17-40 -overwrite

# Include all LEFs from the src directory including merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Set synthesis strategy to delay optimization
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Enable gate sizing during synthesis
set ::env(SYNTH_SIZING) 1

# Run synthesis
run_synthesis

# Floorplanning (equivalent to run_floorplan)
init_floorplan
place_io
tap_decap_or

# Run placement
run_placement

# If placement stage throws CTS-related errors, clear the CTS library variable
unset ::env(LIB_CTS)

# Run Clock Tree Synthesis
run_cts
```

This flow continues the clean design path starting from synthesis with tuned parameters and proceeds to floorplan, placement, and CTS stages using the 0-violation baseline.


Screenshots of commands run

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/5804463d-dee1-470e-a0f9-9276dead584f" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/63eadb2c-faf4-4c0d-80a7-2e81a4733164" />



12. **Run post-CTS timing analysis** in OpenROAD.  
---

### Commands to Run Timing Analysis Using OpenROAD (Integrated OpenSTA)

```tcl
# Launch the OpenROAD tool
openroad

# Read the LEF file (custom and standard cells)
read_lef /openLANE_flow/designs/picorv32a/runs/21-06_17-40/tmp/merged.lef

# Read the DEF file post CTS
read_def /openLANE_flow/designs/picorv32a/runs/21-06_17-40/results/cts/picorv32a.cts.def

# Create a working OpenROAD database
write_db pico_cts.db

# Load the created database (optional reloading step)
read_db pico_cts.db

# Read the netlist after CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/21-06_17-40/results/synthesis/picorv32a.synthesis_cts.v

# Read the complete liberty file
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link the design to the loaded library
link_design picorv32a

# Read the custom timing constraints
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Treat all clocks as propagated (CTS clock tree is active)
set_propagated_clock [all_clocks]

# Verify usage and available options for report_checks
help report_checks

# Generate a detailed timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Exit OpenROAD
exit
```

This sequence performs full post-CTS timing analysis in OpenROAD using custom constraints and reports delay, slew, and net loading for all paths.


Screenshots of commands run and timing report generated

<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/870248f3-ac3d-4f77-b7de-16ef71b9713c" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/3b392b94-61bf-4d7b-95b7-ffaa80ba7faf" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/f300c57e-d0f1-48f1-b191-af45fb736b51" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/56a66456-befe-48a4-962d-6a033ea8642e" />




13.**Investigate post-CTS timing** further by removing `sky130_fd_sc_hd__clkbuf_1` from `CTS_CLK_BUFFER_LIST` and re-analyzing.
--

### Commands to Run OpenROAD Timing Analysis After Modifying CTS_CLK_BUFFER_LIST

```tcl
# Check the current CTS clock buffer list
echo $::env(CTS_CLK_BUFFER_LIST)

# Remove 'sky130_fd_sc_hd__clkbuf_1' from the list
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]

# Confirm removal
echo $::env(CTS_CLK_BUFFER_LIST)

# Check current value of CURRENT_DEF
echo $::env(CURRENT_DEF)

# Set CURRENT_DEF to placement DEF for re-running CTS
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/21-06_17-40/results/placement/picorv32a.placement.def

# Re-run CTS with updated buffer list
run_cts

# Confirm final CTS buffer list
echo $::env(CTS_CLK_BUFFER_LIST)

# Open OpenROAD
openroad

# Read LEF and DEF
read_lef /openLANE_flow/designs/picorv32a/runs/21-06_17-40/tmp/merged.lef
read_def /openLANE_flow/designs/picorv32a/runs/21-06_17-40/results/cts/picorv32a.cts.def

# Save OpenROAD DB and optionally reload
write_db pico_cts1.db
read_db pico_cts.db

# Read post-CTS netlist
read_verilog /openLANE_flow/designs/picorv32a/runs/21-06_17-40/results/synthesis/picorv32a.synthesis_cts.v

# Read Liberty file and link design
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a

# Read SDC and set clock propagation
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]

# Generate timing and skew reports
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4
report_clock_skew -hold
report_clock_skew -setup

# Exit OpenROAD
exit

# Restore original CTS_CLK_BUFFER_LIST
echo $::env(CTS_CLK_BUFFER_LIST)
set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]
echo $::env(CTS_CLK_BUFFER_LIST)
```

This flow demonstrates how to modify the CTS buffer list, re-run CTS, perform post-CTS timing analysis with OpenROAD, and then restore the original buffer list.



Screenshots of commands run and timing report generated

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/8641da26-d3cc-466a-9514-e985a28bbe06" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/306e597d-1a75-4aa3-8d13-46053850fe54" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/efa029f1-41b8-48fd-b07f-1dbf8d37979e" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/2f5a757f-f6bf-4ef9-9b94-58b77811df2d" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/7b62429a-fe2c-4870-a4d7-aa8da74cf5e3" />
<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/fe4c0292-2604-4a78-826a-a45c63db5792" />


</details>  




<details>
<summary><b>Day 5:</b> Final steps for RTL2GDS using tritonRoute and openSTA </summary>   
<br>

Tasks:
-
1. Perform generation of Power Distribution Network (PDN) and explore the PDN layout.
2. Perfrom detailed routing using TritonRoute.
3. Post-Route parasitic extraction using SPEF extractor.
4. Post-Route OpenSTA timing analysis with the extracted parasitics of the route.


1.Perform generation of Power Distribution Network (PDN) and explore the PDN layout.
-

#### 1. **Change Directory to OpenLANE Flow**

```bash
cd Desktop/work/tools/openlane_working_dir/openlane
```

Navigate to the directory where the OpenLANE flow is installed.

---

#### 2. **Start Docker Environment**

```bash
# Alias to simplify Docker execution
alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'

# Start OpenLANE Docker container
docker
```

This mounts the current working directory and PDK path into the Docker container and launches an interactive session.

---

#### 3. **Start OpenLANE in Interactive Mode**

```tcl
./flow.tcl -interactive
```

Launch the OpenLANE flow in interactive mode so individual flow steps can be run manually.

---

#### 4. **Initialize OpenLANE Tcl Package**

```tcl
package require openlane 0.9
```

Load the OpenLANE Tcl package required for running design commands.

---

#### 5. **Prep the Design**

```tcl
prep -design picorv32a
```

Prepare the flow for the `picorv32a` design. This sets up directories and loads config files.

---

#### 6. **Add Custom LEF Files (If Any)**

```tcl
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
```

If there are additional LEF files added to the design source directory, include them in the merged LEF used by OpenLANE.

---

#### 7. **Adjust Synthesis Strategy and Sizing**

```tcl
set ::env(SYNTH_STRATEGY) "DELAY 3"
set ::env(SYNTH_SIZING) 1
```

Customize synthesis behavior by choosing a delay-based optimization strategy and enabling synthesis-time gate sizing.

---

#### 8. **Run Synthesis**

```tcl
run_synthesis
```

Run RTL to gate-level synthesis.

---

#### 9. **Floorplan Initialization (Included in run\_floorplan)**

```tcl
init_floorplan
place_io
tap_decap_or
```

These commands are automatically run by `run_floorplan`. If executed manually, they initialize floorplan, place IO cells, and insert tap/decap cells.

---

#### 10. **Run Placement**

```tcl
run_placement
```

Execute standard cell placement based on the floorplan.

---

#### 11. **Fix CTS Library Issue (If Any)**

```tcl
unset ::env(LIB_CTS)
```

Unset the CTS library if it causes any errors during the clock tree synthesis step.

---

#### 12. **Run Clock Tree Synthesis (CTS)**

```tcl
run_cts
```

Generate and insert clock buffers to drive the clock network.

---

#### 13. **Generate Power Distribution Network (PDN)**

```tcl
gen_pdn
```

Automatically generate the power grid and power straps based on the design floorplan.

---
#### View PDN DEF in Magic VLSI Tool

```bash
# Change directory to path containing generated PDN def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/26-06_13-54/tmp/floorplan/

# Command to load the PDN def in Magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read 14-pdn.def &
```

**Explanation**:

* `cd` navigates to the directory containing the `14-pdn.def` file, which includes the generated PDN layout.
* `magic -T` starts the Magic VLSI layout editor using the Sky130 technology file.
* `lef read` loads the merged LEF to provide cell and layer information.
* `def read` loads the PDN DEF file.
* `&` runs the Magic GUI in the background, keeping the terminal available for other tasks.

This allows you to visualize the layout of the power distribution network (PDN) using the Magic VLSI tool.






screenshots:
--

<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/995f8ea3-bfb1-43f7-8360-61bcbbe8f41b" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/2279680b-3552-4480-bf53-257b00dd8b6e" />
<img width="1920" height="937" alt="Image" src="https://github.com/user-attachments/assets/0793c1e2-9fa6-4d86-a6e2-0b14def4d159" />
<img width="1920" height="937" alt="Image" src="https://github.com/user-attachments/assets/012614c8-e508-4bde-be63-72bb83b9d90e" />
<img width="1920" height="937" alt="Image" src="https://github.com/user-attachments/assets/4c585b80-5c51-40a5-9a24-be5bd8bb784f" />



2.Perfrom detailed routing using TritonRoute and explore the routed layout.
--

#### Detailed Routing with TritonRoute

Below is an explanation of the three Tcl commands used during the routing stage in OpenLANE.

```tcl
# Check value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)
```

**What it does**: Prints the current DEF (Design Exchange Format) file path stored in the `CURRENT_DEF` environment variable.
**Why it matters**: `CURRENT_DEF` should point to the latest placement or routing DEF that TritonRoute will use as its starting point. Verifying it avoids unintentionally routing an outdated layout.

---

```tcl
# Check value of 'ROUTING_STRATEGY'
echo $::env(ROUTING_STRATEGY)
```

**What it does**: Outputs the routing strategy number configured for TritonRoute.
**Why it matters**: OpenLANE supports multiple predefined routing strategies (0, 1, 2 …). The strategy influences layer preferences, cost parameters, and congestion handling. Echoing the value confirms which strategy is active before invoking the router.

| Strategy | Typical Use‑Case       | Notes                                    |
| -------- | ---------------------- | ---------------------------------------- |
| 0        | Balanced default       | Good first try for most designs          |
| 1        | Congestion‑heavy cores | Prioritizes detours to relieve hot spots |
| 2        | Timing‑critical        | Optimizes wirelength on top layers       |

---

```tcl
# Command for detailed route using TritonRoute
run_routing
```

**What it does**: Launches TritonRoute—the detailed router in OpenLANE—to convert the global‑route guides into legal, DRC‑clean metal connections.

**Key steps performed internally**:

1. **Import global routing guides** produced by FastRoute.
2. **Iterative maze routing** to create wires that honor design rules.
3. **DRC fixing passes** to resolve shorts, spacing, and antenna violations.
4. **Parasitic extraction** (optional) producing a final SPEF if enabled.
5. **Writes out** the completed routed DEF (`*-routed.def`) and an updated `CURRENT_DEF` path.

> **Tip:** If the run fails with DRC violations, try adjusting `ROUTING_STRATEGY`, `MAX_LAYER`, or congestion parameters in `config.tcl`, then rerun `run_routing`.

screenshots of running this:
--
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/7eeeb555-15f6-4932-8003-f1676e86d113" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/335db562-dde4-485a-ab75-7e5e5a4a8202" />



#### View Routed DEF in Magic VLSI Tool

```bash
# Change directory to path containing routed DEF
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/26-06_13-54/results/routing/

# Command to load the routed DEF in Magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.def &
```

**Explanation**:

* `cd` changes into the routing output directory for the specific run (`26-06_13-54`) of the `picorv32a` design.
* `magic -T` launches the Magic layout tool using the Sky130 technology file that defines physical layers and design rules.
* `lef read` loads the merged LEF file containing cell abstracts and macro information.
* `def read` loads the fully routed DEF (`picorv32a.def`), which includes routing traces, vias, and placements.
* `&` runs Magic in the background so the terminal remains available.

This lets you visualize the final routed layout including detailed metal traces created by TritonRoute.

Screenshots of routed def :
-

<img width="1853" height="910" alt="Image" src="https://github.com/user-attachments/assets/ddc9d50d-697f-465b-8403-42a7e4810469" />
<img width="1920" height="937" alt="Image" src="https://github.com/user-attachments/assets/7f0c5034-92c7-446a-a37b-98ee78f635f6" />

<img width="1652" height="877" alt="Image" src="https://github.com/user-attachments/assets/7bb26f0a-9e93-41dc-8f81-7b837f421b75" />

3.Post-Route parasitic extraction using SPEF extractor.
--

#### Extract SPEF File from Routed DEF

```bash
# Change directory to SPEF extractor tool
cd Desktop/work/tools/SPEF_EXTRACTOR

# Run the SPEF extractor script with LEF and routed DEF inputs
python3 main.py /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/26-06_13-54/tmp/merged.lef /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/26-06_13-54/results/routing/picorv32a.def
```

**Explanation**:

* `cd`: Moves to the directory containing the custom Python script for extracting Standard Parasitic Exchange Format (SPEF) data.
* `python3 main.py`: Runs the SPEF extractor.
* The first argument is the path to the merged LEF file.
* The second argument is the path to the routed DEF file.

The tool will parse these inputs and generate a `.spef` file that contains estimated parasitic capacitance and resistance values, which are crucial for post-routing timing analysis.


4.Post-Route OpenSTA timing analysis with the extracted parasitics of the route.
-

#### Timing Analysis using OpenROAD (Post-Routing with SPEF)

```tcl
# Command to run OpenROAD tool
openroad
```

**Explanation**: Launches the OpenROAD tool in command-line mode for performing timing analysis and other chip design operations.

---

```tcl
# Reading LEF file
read_lef /openLANE_flow/designs/picorv32a/runs/26-06_13-54/tmp/merged.lef
```

**Explanation**: Loads the physical layout information such as cells, macros, and routing layers needed to interpret the DEF.

---

```tcl
# Reading DEF file
read_def /openLANE_flow/designs/picorv32a/runs/26-06_13-54/results/routing/picorv32a.def
```

**Explanation**: Loads the physical layout of the placed and routed design.

---

```tcl
# Creating an OpenROAD database to work with
write_db pico_route.db
```

**Explanation**: Saves the current state of the design into an OpenROAD database for quick reloads.

---

```tcl
# Loading the created database in OpenROAD
read_db pico_route.db
```

**Explanation**: Reloads the previously saved OpenROAD database file.

---

```tcl
# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/26-06_13-54/results/synthesis/picorv32a.synthesis_preroute.v
```

**Explanation**: Reads in the synthesized Verilog netlist that reflects the post-CTS (Clock Tree Synthesis) logic.

---

```tcl
# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)
```

**Explanation**: Loads the Liberty (.lib) file that defines timing and power information for each standard cell.

---

```tcl
# Link design and library
link_design picorv32a
```

**Explanation**: Matches the netlist with the cells in the loaded Liberty file, establishing a complete representation of the design for analysis.

---

```tcl
# Read in the custom SDC file
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc
```

**Explanation**: Loads the Synopsys Design Constraints (SDC) file which specifies clock definitions, I/O constraints, and timing exceptions.

---

```tcl
# Setting all clocks as propagated clocks
set_propagated_clock [all_clocks]
```

**Explanation**: Tells the STA engine to use actual clock delays as routed in the netlist instead of assuming ideal clocks.

---

```tcl
# Read SPEF
read_spef /openLANE_flow/designs/picorv32a/runs/26-06_13-54/results/routing/picorv32a.spef
```

**Explanation**: Loads the parasitic resistance and capacitance information generated after routing. This is crucial for accurate delay and slew computation.

---

```tcl
# Generate a custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4
```

**Explanation**: Generates a detailed setup and hold timing report that includes:

* **slew**: rate of signal transition
* **trans**: transition time
* **net**: net delay
* **cap**: net capacitance
* **input\_pins**: affected pins

---

```tcl
# Exit to OpenLANE flow
exit
```

**Explanation**: Terminates the OpenROAD session.

---

This sequence enables accurate post-route Static Timing Analysis (STA) using OpenROAD, incorporating layout parasitics and clock tree effects.


screenshots of running these commands:
--
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/e1a682e2-0c81-4801-ae7f-a08d344e9ece" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/7feb0665-6bf9-4b7a-a5cd-0fa14bc338cc" />
<img width="888" height="898" alt="Image" src="https://github.com/user-attachments/assets/23620f83-f65f-4e4a-a12c-74731026c621" />
<img width="955" height="925" alt="Image" src="https://github.com/user-attachments/assets/f82e63e3-3d9d-46aa-b6c3-9de9e015f666" />


</details>  




<details>
<summary><b>Day 5:</b> Acknowledment </summary>   
<br>
  I would like to express my heartfelt gratitude to Mr. Kunal Ghosh, Co-founder of VLSI System Design (VSD) Corp. Pvt. Ltd., Mr. Mohamed Shalan from efabless.com, and Mr. Nickson Jose for their invaluable guidance and support throughout the DIGITAL VLSI SoC Design and Planning workshop.

  This workshop provided a comprehensive understanding of the RTL to GDSII flow and offered hands-on experience with the complete open-source toolchain, OpenLANE. The practical exposure and expert insights shared during the sessions have greatly enriched my knowledge and enhanced my confidence in working with digital design and physical implementation workflows.

  I am truly grateful for the opportunity to be part of this learning experience and for the continuous encouragement from the mentors involved.



</details>  


