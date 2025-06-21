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

   </details> 
</details>
</details>
