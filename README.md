### Ex. No. 6
#### Date: 19.5.23
# Implementation of 4 bit synchronous counters using Verilog HDL
## Aim:
To design and implement the following synchronous counters using Verilog HDL.
1.	UP counter
2.	DOWN counter
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
A Synchronous counter is the counter in which the clock input with all the flip-flops uses the same source and produces the output at the same time.
## UP Counter
### State table
![image](https://github.com/rvinifa/Counter/assets/133735746/ede78598-89fd-4aeb-9d82-329e45d05f2a)

### K-map Simplification

   ![image](https://github.com/rvinifa/Counter/assets/133735746/21554263-611b-44a2-8f78-7b2220ef5a05)
   
### Logic Diagram
![image](https://github.com/rvinifa/Counter/assets/133735746/2ab715d3-f6d5-4cf6-8fda-8fa666518c0b)



## DOWN Counter
### State Table
 ![image](https://github.com/rvinifa/Counter/assets/133735746/5be9585c-11aa-47c3-beaf-0dca916750f2)

### K-map simplification
 ![image](https://github.com/rvinifa/Counter/assets/133735746/dde7bc60-3a4f-4fb7-811d-f420cb74bdef)

### Logic Diagram
 ![image](https://github.com/rvinifa/Counter/assets/133735746/64e2d7b7-1646-4ca7-bc6c-c7c10881223c)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
Upcounter:
```
module upcounter(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always @(posedge clk)
begin
q4=(q1&q2&q3)^q4;
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end
endmodule
```
Downcounter:
```
module downcounter(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always@(posedge clk)
begin
q4=((~q1)&(~q2)&(~q3))^q4;
q3=((~q1)&(~q2))^q3;
q2=(~q1)^q2;
q1=1^q1;
end
endmodule 
```

## RTL Schematic:
Upcounter:

<img width="506" alt="up counter rtl" src="https://github.com/Jothikrishnan-jk/Counter/assets/129312867/b6ed0703-0ad8-4431-a879-83931516d3d6">

Downcounter:

<img width="514" alt="down counter rtl" src="https://github.com/Jothikrishnan-jk/Counter/assets/129312867/c886a250-6036-486c-806b-6f4a5735e18a">


## Timing Diagram:
Upcounter:

<img width="898" alt="up counter wave fporm" src="https://github.com/Jothikrishnan-jk/Counter/assets/129312867/d0c3373d-451c-478a-a361-9e5001ae7e13">

Downcounter:

<img width="958" alt="down counter  timing" src="https://github.com/Jothikrishnan-jk/Counter/assets/129312867/bb459e3a-617e-465d-ac3c-bdb007d72b11">

## Result:
Thus the Synchronous UP and DOWN counters using T flipflops are implemented and the state tables are verified.

