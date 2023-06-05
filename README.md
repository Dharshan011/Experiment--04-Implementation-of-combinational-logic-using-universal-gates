# Experiment--02-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: DHARSHAN V
RegisterNumber: 212222230031
## Nand Program:
```
module combine1(A,B,C,D,F);
input A,B,C,D;
output F;
assign P = C&(~B)&(~A);
assign Q = D&(~C)&(~A);
assign R = (~C)&B&(~A);
assign F = (~P&~Q&~R);
endmodule
```
## Nor Program:
```
module combine2(A,B,C,D,F);
input A,B,C,D;
output F;
assign P = C&(~B)&A;
assign Q = D&(~C)&A;
assign R = C&(~B)&A;
assign S = ~(P|Q|R);
assign F = ~S;
endmodule
```

## RTL realization
## NAND
![Screenshot 2023-03-30 104824](https://user-images.githubusercontent.com/113497491/228737215-aa120efe-8d27-4b92-9ba7-963cfb9971fb.png)
## NOR
![Screenshot 2023-03-30 104831](https://user-images.githubusercontent.com/113497491/228737257-3fa17b72-fb75-458b-bb6e-315c32f35a48.png)
## Truth Table:
NAND
![Screenshot 2023-03-30 104841](https://user-images.githubusercontent.com/113497491/228737692-b54cf4d6-589b-42cd-8a4c-9c846d2a3029.png)

NOR
![Screenshot 2023-03-30 104849](https://user-images.githubusercontent.com/113497491/228737403-f82e7c7a-5e19-454e-aeac-1afa325f576c.png)

## Timing Diagram
![Screenshot 2023-03-30 104903](https://user-images.githubusercontent.com/113497491/228737643-374d8409-7deb-4393-804a-e305dcf3c793.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
