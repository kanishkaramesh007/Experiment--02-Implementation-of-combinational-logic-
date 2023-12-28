# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic gates
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.
 F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
F2=xy’z+x’y’z+w’xy+wx’y+wxy
 
 
 
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
 Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.
## using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'
## Logic Diagram
Using NOR gates NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'
## Procedure
1.Create a project with required entities. 2.Create a module along with respective file name. 3.Run the respective programs for the given boolean equations. 4.Run the module and get the respective RTL outputs. 5/Create university program(VWF) for getting timing diagram. 6.Give the respective inputs for timing diagram and obtain the results.
## Program:
\*
Program to implement the given logic function and to verify its operations in quartus using Verilog programming.
Developed by: KANISHKA R S
RegisterNumber:212223050026  
*/
Using NAND Operation:

module combine1(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R;
assign P = C&(~B)&(~A);
assign Q = D&(~C)&(~A);
assign R = (~C)&B&(~A);
assign F = (~P&~Q&~R);
endmodule
Using NOR Operation:

module combine2(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R,S;
assign P = C&(~B)&A;
assign Q = D&(~C)&A;
assign R = C&(~B)&A;
assign S = ~(P|Q|R);
assign F = ~S;
endmodule
## RTL realization
NAND
![image](https://github.com/kanishkaramesh007/Experiment--02-Implementation-of-combinational-logic-/assets/147321636/ae7b681d-c500-4274-8e8e-212a85aa1b0f)
NOR
![image](https://github.com/kanishkaramesh007/Experiment--02-Implementation-of-combinational-logic-/assets/147321636/e9aab146-3aab-44a1-aa5c-10370b320969)


## Output:
NAND
![image](https://github.com/kanishkaramesh007/Experiment--02-Implementation-of-combinational-logic-/assets/147321636/201dc688-c60c-4865-90d8-42a7a5ca013e)
NOR
![image](https://github.com/kanishkaramesh007/Experiment--02-Implementation-of-combinational-logic-/assets/147321636/5243c098-18d7-490c-843b-66cb98ed4066)

## Timing Diagram
NAND
![image](https://github.com/kanishkaramesh007/Experiment--02-Implementation-of-combinational-logic-/assets/147321636/69443c9a-faa5-45b3-a1f0-ac478b2505d4)
NOR
![image](https://github.com/kanishkaramesh007/Experiment--02-Implementation-of-combinational-logic-/assets/147321636/7548850e-6ca9-4aaa-a08d-cac014bce76c)

## Result:
Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.
