# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
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
### Developed by:DHIVYA SHRI
### RegisterNumber:2122123009 
~~~~
USING NAND
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign F= f1&~f2&~f3;
endmodule

USING NOR
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(F,f4);
endmodule
~~~~ 
## RTL realization

## Output:
## program 1:
## RTL
![d 1](https://user-images.githubusercontent.com/94154679/198864579-c27ce413-fe63-4411-95c1-3f715a3dcaab.jpg)

## Timing Diagram
![d 2](https://user-images.githubusercontent.com/94154679/198864630-87236827-f52d-489a-a530-57c84c14d2f4.jpg)

## Truth Table
![d 3](https://user-images.githubusercontent.com/94154679/198864676-1ea62e36-2002-476b-805a-5998ea53f5e2.jpg)

## program 2:
## RTL
![d 4](https://user-images.githubusercontent.com/94154679/198864708-80868047-25fd-4525-83c6-09c62120a6fd.jpg)

## Timing Diagram 
![d 5](https://user-images.githubusercontent.com/94154679/198864717-ab10d22b-f645-43e0-86ce-207baef388ff.jpeg)

## Truth Table
![d 6](https://user-images.githubusercontent.com/94154679/198864735-8fb4edbd-bda2-4126-86b5-d600e832f522.jpg)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
