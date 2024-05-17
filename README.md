## VLSI-LAB-EXP-5
# SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

## AIM: 
        To simulate and synthesis finite state machine using Xilinx ISE.

## APPARATUS REQUIRED: 
                       Xilinx 14.7 Spartan6 FPGA

## PROCEDURE:
(https://github.com/SwarnaMallikaPL/VLSI-LAB-EXP-6)

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



