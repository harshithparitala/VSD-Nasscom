# VSD-Nasscom

<details>
<summary><b>Day 1:</b>  Inception of open-source EDA, OpenLANE and Sky130 PDK </summary>   
<br>
<details>
<summary><b>Day 1:</b>  Introduction to QFN-48,Package,Die,Core and IP's </summary>   
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

</details>
