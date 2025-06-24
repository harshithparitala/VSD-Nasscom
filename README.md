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


screenshot of the spice file :



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




2.Performing post-layout ngspice simulations.
--

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









 
</details>   

 
</details>  



<details>
<summary><b>Day 4:</b> Pre-layout timing analysis and importance of good clock tree </summary>   
<br>

</details>  
