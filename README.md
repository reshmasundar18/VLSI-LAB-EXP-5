## VLSI-LAB-EXP-5
# SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE 

## AIM: 
        To simulate and synthesis finite state machine using Xilinx ISE.

## APPARATUS REQUIRED: 
                       Xilinx 14.7 Spartan6 FPGA

## PROCEDURE:
STEP:1 Start the Xilinx navigator, Select and Name the New project. 

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 

STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is 
       obtained. 
       
STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.

STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. 

STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output. 

STEP:12 Load the Bit file into the SPARTAN 6 FPGA

## LOGIC DIAGRAM :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


## PROGRAM:
```
module FSM_moore(clk, rst, x, z);
input clk, rst, x;
output z;
reg [2:1] present_state, NEXT_STATE; 
parameter S0=2'b00, S1=2'b01, S2=2'b10, S3=2'b11;
always@(x,present_state)
case(present_state)
S0:	if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S0;
S1:	if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S2;
S2:	if(x)
NEXT_STATE=S3;
else
NEXT_STATE=S0;
S3:	if(x)
NEXT_STATE=S1;
else
NEXT_STATE=S2;
endcase
always@(negedge rst, posedge clk)
if(rst)
 present_state<=S0;
else 
present_state<=NEXT_STATE;
assign z=(present_state==S3); 
endmodule
```

## OUTPUT:

![Screenshot 2024-05-17 133841](https://github.com/reshmasundar18/VLSI-LAB-EXP-5/assets/166894571/ec77595d-b635-48ac-ba4b-3430ea4bff8b)


## RESULT:
          Thus, The Finite State Machine are simulated and implemented successfully using Xilinx ISE.



