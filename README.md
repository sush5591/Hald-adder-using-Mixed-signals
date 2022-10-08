# Half-adder-using-Mixed-signals
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





