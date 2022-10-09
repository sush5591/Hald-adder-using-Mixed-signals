# Half-adder-using-Mixed-signals
- [Abstract](#abstract)
- [Reference Circuit Diagram](#reference-circuit-diagram)
- [Reference Waveform](#reference-waveform)
- [Circuit Details](#circuit-details)
- [Truth Table](#truth-table)
- [Software Used](#software-used)
  * [eSim](#esim)
  * [NgSpice](#ngspice)
  * [Makerchip](#makerchip)
  * [Verilator](#verilator)
- [Circuit Diagram in eSim](#circuit-diagram-in-esim)
- [Verilog Code](#verilog-code)
- [Makerchip](#makerchip-1)
- [Makerchip Plots](#makerchip-plots)
- [Netlists](#netlists)
- [NgSpice Plots](#ngspice-plots)
- [Steps to run generate NgVeri Model](#steps-to-run-generate-ngveri-model)
- [Steps to run this project](#steps-to-run-this-project)
- [Acknowlegdements](#acknowlegdements)
- [References](#references)


## Abstract
<p> In this project, half adder is designed by mixed signals using SKY130mode. The design includes both analog and digital circuits. Digital block i.e. 2-bit counter, NOT, BUFFER, EX-NOR gates is designed using Makerchip-NgVeri and analog block i.e. NAND gate is designed using Ngspice. The pulses are given to a 2-bit counter as an analog signal. This counter generates specific sequences which get added with the adder circuit. Adder circuit again consists of mixed signal i.e. EX-OR gate for SUM and Complementary metal oxide semiconductor (CMOS) NAND gate with NOT gate for CARRY.</p>

## Reference Circuit Diagram
![image](https://user-images.githubusercontent.com/114681343/194699479-364ad210-51af-471d-8086-bb5990d3459b.PNG)
## Reference Waveform
![image](https://user-images.githubusercontent.com/114681343/194699559-768536c0-9e2d-4a8b-9cda-6f7116a7822b.PNG)
## Circuit Details
The above shown figure is of hald adder. A logic circuit for the addition of two 1-bit numbers is referred to as a half adder. We can achieve SUM with the help of EX-OR gate and CARRY with the help of AND gate. </br>
## Truth Table

| Input A  | Input B | Output SUM | Output CARRY |
| ------------- | ------------- | ------------- | ------------- |
| 0  | 0 | 0  | 0|
| 0  | 1 | 1| 0|
| 1  | 0 |1|0|
| 1 | 1 |0|1|
## Software Used
### eSim
It is an Open Source EDA developed by FOSSEE, IIT Bombay. It is used for electronic circuit simulation. It is made by the combination of two software namely NgSpice and KiCAD.
</br>
For more details refer:
</br>
https://esim.fossee.in/home
### NgSpice
It is an Open Source Software for Spice Simulations. For more details refer:
</br>
http://ngspice.sourceforge.net/docs.html
### Makerchip
It is an Online Web Browser IDE for Verilog/System-verilog/TL-Verilog Simulation. Refer
</br> https://www.makerchip.com/
### Verilator
It is a tool which converts Verilog code to C++ objects. Refer:
https://www.veripool.org/verilator/

## Circuit Diagram in eSim
The following is the schematic in eSim:
![image](https://user-images.githubusercontent.com/114681343/194699816-4dda267d-7fe4-43d7-8d9b-f92bd140dec0.PNG)
## Verilog Code
### 2-bit COUNTER
![image](https://user-images.githubusercontent.com/114681343/194699854-79f1e80d-ad7a-4c41-9a0f-e16ca95af6f1.PNG)

### EX-OR gate
![image](https://user-images.githubusercontent.com/114681343/194699860-8cd68d4e-3a14-48f9-82c0-e0be58ba06b8.PNG)

### NOT gate
![image](https://user-images.githubusercontent.com/114681343/194699868-a93e6e8a-dc79-42b4-b036-a1bb0d57b3f2.PNG)

### BUFFER
![image](https://user-images.githubusercontent.com/114681343/194699872-aff7d465-9980-4f6b-a4f2-fa047618253f.PNG)
## Makerchip
### 2-bit COUNTER
```
\TLV_version 1d: tl-x.org
\SV
/* verilator lint_off UNUSED*/  /* verilator lint_off DECLFILENAME*/  /* verilator lint_off BLKSEQ*/  /* verilator lint_off WIDTH*/  /* verilator lint_off SELRANGE*/  /* verilator lint_off PINCONNECTEMPTY*/  /* verilator lint_off DEFPARAM*/  /* verilator lint_off IMPLICIT*/  /* verilator lint_off COMBDLY*/  /* verilator lint_off SYNCASYNCNET*/  /* verilator lint_off UNOPTFLAT */  /* verilator lint_off UNSIGNED*/  /* verilator lint_off CASEINCOMPLETE*/  /* verilator lint_off UNDRIVEN*/  /* verilator lint_off VARHIDDEN*/  /* verilator lint_off CASEX*/  /* verilator lint_off CASEOVERLAP*/  /* verilator lint_off PINMISSING*/    /* verilator lint_off BLKANDNBLK*/  /* verilator lint_off MULTIDRIVEN*/     /* verilator lint_off WIDTHCONCAT*/  /* verilator lint_off ASSIGNDLY*/  /* verilator lint_off MODDUP*/  /* verilator lint_off STMTDLY*/  /* verilator lint_off LITENDIAN*/  /* verilator lint_off INITIALDLY*/    

//Your Verilog/System Verilog Code Starts Here:
module sushant_counter2bit (input clk, input rst, output reg[1:0] out);

always @ (posedge clk)
begin

if (rst)
out <= 0;
else
out <= out+1;
end
endmodule

//Top Module Code Starts here:
	module top(input logic clk, input logic reset, input logic [31:0] cyc_cnt, output logic passed, output logic failed);
		logic  rst;//input
		logic  [1:0] out;//output
//The $random() can be replaced if user wants to assign values
	always @(posedge clk) 
         begin
        		   rst = $random();
            end
		sushant_counter2bit sushant_counter2bit(.clk(clk), .rst(rst), .out(out));
	
\TLV
//Add \TLV here if desired                                     
\SV
endmodule

```
### EX-OR gate
```
\TLV_version 1d: tl-x.org
\SV
/* verilator lint_off UNUSED*/  /* verilator lint_off DECLFILENAME*/  /* verilator lint_off BLKSEQ*/  /* verilator lint_off WIDTH*/  /* verilator lint_off SELRANGE*/  /* verilator lint_off PINCONNECTEMPTY*/  /* verilator lint_off DEFPARAM*/  /* verilator lint_off IMPLICIT*/  /* verilator lint_off COMBDLY*/  /* verilator lint_off SYNCASYNCNET*/  /* verilator lint_off UNOPTFLAT */  /* verilator lint_off UNSIGNED*/  /* verilator lint_off CASEINCOMPLETE*/  /* verilator lint_off UNDRIVEN*/  /* verilator lint_off VARHIDDEN*/  /* verilator lint_off CASEX*/  /* verilator lint_off CASEOVERLAP*/  /* verilator lint_off PINMISSING*/    /* verilator lint_off BLKANDNBLK*/  /* verilator lint_off MULTIDRIVEN*/     /* verilator lint_off WIDTHCONCAT*/  /* verilator lint_off ASSIGNDLY*/  /* verilator lint_off MODDUP*/  /* verilator lint_off STMTDLY*/  /* verilator lint_off LITENDIAN*/  /* verilator lint_off INITIALDLY*/    

//Your Verilog/System Verilog Code Starts Here:
module sushant_xor_gate (output reg Y, input A, B);
always @ (A or B) 
begin
    if (A == 1'b0 & B == 1'b0) 
	begin
        Y = 1'b0; 
   end   
  else if (A == 1'b1 & B == 1'b1) 
   begin
       Y = 1'b0; 
   end    
   else 
       Y = 1'b1; 
 end
endmodule

//Top Module Code Starts here:
	module top(input logic clk, input logic reset, input logic [31:0] cyc_cnt, output logic passed, output logic failed);
		logic  Y;//output
		logic  A;//input
		logic  B;//input
//The $random() can be replaced if user wants to assign values
		 always @(posedge clk) 
         begin
         A = $random();
		     B = $random();
            end
		sushant_xor_gate sushant_xor_gate(.Y(Y), .A(A), .B(B));
	
\TLV
//Add \TLV here if desired                                     
\SV
endmodule

```
### NOT gate
```
\TLV_version 1d: tl-x.org
\SV
/* verilator lint_off UNUSED*/  /* verilator lint_off DECLFILENAME*/  /* verilator lint_off BLKSEQ*/  /* verilator lint_off WIDTH*/  /* verilator lint_off SELRANGE*/  /* verilator lint_off PINCONNECTEMPTY*/  /* verilator lint_off DEFPARAM*/  /* verilator lint_off IMPLICIT*/  /* verilator lint_off COMBDLY*/  /* verilator lint_off SYNCASYNCNET*/  /* verilator lint_off UNOPTFLAT */  /* verilator lint_off UNSIGNED*/  /* verilator lint_off CASEINCOMPLETE*/  /* verilator lint_off UNDRIVEN*/  /* verilator lint_off VARHIDDEN*/  /* verilator lint_off CASEX*/  /* verilator lint_off CASEOVERLAP*/  /* verilator lint_off PINMISSING*/    /* verilator lint_off BLKANDNBLK*/  /* verilator lint_off MULTIDRIVEN*/     /* verilator lint_off WIDTHCONCAT*/  /* verilator lint_off ASSIGNDLY*/  /* verilator lint_off MODDUP*/  /* verilator lint_off STMTDLY*/  /* verilator lint_off LITENDIAN*/  /* verilator lint_off INITIALDLY*/    

//Your Verilog/System Verilog Code Starts Here:
module sushant_not_gate (output reg Y, input A);
always @ (A)
 begin
    if (A == 1'b0 )
	begin
        Y = 1'b1;
    end
    else if (A == 1'b1)
	begin
       Y = 1'b0;
end
end
endmodule

//Top Module Code Starts here:
	module top(input logic clk, input logic reset, input logic [31:0] cyc_cnt, output logic passed, output logic failed);
		logic  Y;//output
		logic  A;//input
//The $random() can be replaced if user wants to assign values
		 always @(posedge clk) 
         begin
         A = $random();
            end
		sushant_not_gate sushant_not_gate(.Y(Y), .A(A));
	
\TLV
//Add \TLV here if desired                                     
\SV
endmodule

```
### BUFFER
```
\TLV_version 1d: tl-x.org
\SV
/* verilator lint_off UNUSED*/  /* verilator lint_off DECLFILENAME*/  /* verilator lint_off BLKSEQ*/  /* verilator lint_off WIDTH*/  /* verilator lint_off SELRANGE*/  /* verilator lint_off PINCONNECTEMPTY*/  /* verilator lint_off DEFPARAM*/  /* verilator lint_off IMPLICIT*/  /* verilator lint_off COMBDLY*/  /* verilator lint_off SYNCASYNCNET*/  /* verilator lint_off UNOPTFLAT */  /* verilator lint_off UNSIGNED*/  /* verilator lint_off CASEINCOMPLETE*/  /* verilator lint_off UNDRIVEN*/  /* verilator lint_off VARHIDDEN*/  /* verilator lint_off CASEX*/  /* verilator lint_off CASEOVERLAP*/  /* verilator lint_off PINMISSING*/    /* verilator lint_off BLKANDNBLK*/  /* verilator lint_off MULTIDRIVEN*/     /* verilator lint_off WIDTHCONCAT*/  /* verilator lint_off ASSIGNDLY*/  /* verilator lint_off MODDUP*/  /* verilator lint_off STMTDLY*/  /* verilator lint_off LITENDIAN*/  /* verilator lint_off INITIALDLY*/    

//Your Verilog/System Verilog Code Starts Here:
module sushant_buffer (output reg Y, input A);
always @ (A)
 begin
    if (A == 1'b0 )
	begin
        Y = 1'b0;
    end
    else if (A == 1'b1)
	begin
       Y = 1'b1;
end
end
endmodule

//Top Module Code Starts here:
	module top(input logic clk, input logic reset, input logic [31:0] cyc_cnt, output logic passed, output logic failed);
		logic  Y;//output
		logic  A;//input
//The $random() can be replaced if user wants to assign values
		always @(posedge clk) 
         begin
         A = $random();
            end
		sushant_buffer sushant_buffer(.Y(Y), .A(A));
		
\TLV
//Add \TLV here if desired                                     
\SV
endmodule

```
## Makerchip Plots
### 2-bit COUNTER
![image](https://user-images.githubusercontent.com/114681343/194701599-c442134a-95a4-4ea4-a659-c8adfa3e1bc9.PNG)

### EX-OR gate
![image](https://user-images.githubusercontent.com/114681343/194701670-cba5ed96-6173-4d0a-8afe-654fe9bcf040.PNG)

### NOT gate
![image](https://user-images.githubusercontent.com/114681343/194701682-416abf0a-db8b-46cf-860b-3fc7ca613ae9.PNG)

### BUFFER
![image](https://user-images.githubusercontent.com/114681343/194701698-6f1a2ece-0d7d-49a4-85cd-a23e5909cb33.PNG)

## Netlists
![image](https://user-images.githubusercontent.com/114681343/194703223-b359d1e4-f424-49d7-b8d7-6fd918c83d62.PNG)

![image](https://user-images.githubusercontent.com/114681343/194703154-64804649-1c7c-416e-b420-2ae3c623cf9f.PNG)
## NgSpice Plots
![image](https://user-images.githubusercontent.com/114681343/194702364-7ad3d2fc-e2ad-4e28-b5a6-5e0ee10610dc.PNG)
## Steps to run generate NgVeri Model
1. Open eSim
2. Run NgVeri-Makerchip 
3. Add top level verilog file in Makerchip Tab
4. Click on NgVeri tab
5. Add dependency files
6. Click on Run Verilog to NgSpice Converter
7. Debug if any errors
8. Model created successfully
## Steps to run this project
1. Open a new terminal
2. Clone this project using the following command:</br>
```git clone https://github.com/sush5591/Half-adder-using-Mixed-signals ```</br>
3. Change directory:</br>
```cd eSim_project_files/half-adder-using-Mixed-signals```</br>
4. Run ngspice:</br>
```ngspice half-adder-using-Mixed-signals.cir.out```</br>
5. To run the project in eSim:

  - Run eSim</br>
  - Load the project</br>
  - Open eeSchema</br>
## Acknowlegdements
1. FOSSEE, IIT Bombay
2. Steve Hoover, Founder, Redwood EDA
3. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
4. Sumanto Kar, eSim Team, FOSSEE
5. 	http://iitb.ac.in/
6.	https://www.google.co.in/
7.	https://fossee.in/
8.	https://spoken-tutorial.org/
9.	https://www.vlsisystemdesign.com/
10.	https://www.c2s.gov.in/

## References
[1] https://www.vsdiat.com.

[2] Book by R P Jain,  Modern Digital Electronics.

[3] https://github.com/Eyantra698Sumanto/XOR-XNOR-Gate/edit/main/README.md






