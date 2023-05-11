# Experiment--03-Half-Subtractor-and-Full-subtractor
# Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:

To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
 Hardware – PCs, Cyclone II , USB flasher
 Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure

1.Use module projname(input,output) to start the Verilog programmming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.Use each output to represent one for difference and the other for borrow.

5.End the verilog program using keyword endmodule.

## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by:D.Dhanumalya

RegisterNumber:212222230030

## Half Sub
module halfsub(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire X;
xor(Diff,A,B);
not(X,A);
and(Borrow,X,B);
endmodule

## Full Sub
module fullsub(A,B,C,Difference,Borrow);
input A,B,C;
output Difference,Borrow;
assign Difference = ( A^B^C);
assign Borrow = (~A &(B ^ C) | (B & C));
endmodule
```
 
# Output:

## Truthtable
## Half Sub
![image](https://user-images.githubusercontent.com/119218812/229308006-65308877-9b05-47c9-9867-c85e95cbe3d2.png)
## Full Sub
![image](https://user-images.githubusercontent.com/119218812/229308018-52b220ab-df95-4dc4-8a0d-7d02c3878e28.png)

##  Logic Symbol
## Half Sub
![image](https://user-images.githubusercontent.com/119218812/229308035-e43800ec-96b1-4ad8-b774-3f4c41fb42af.png)
## Full Sub
![image](https://user-images.githubusercontent.com/119218812/229308046-a6bcef09-1c75-4ede-a597-d544aa521f37.png)

##  RTL realization
## Half Sub
![Screenshot (69)](https://user-images.githubusercontent.com/119218812/229308130-d0f06b61-35b6-4bb3-955f-e1e7b655e531.png)

## Full Sub
![Screenshot (72)](https://user-images.githubusercontent.com/119218812/229308136-e0151e46-a774-4df2-9f9b-6e429904d12f.png)

## Timing diagram 
## Half Sub
![Screenshot (71)](https://user-images.githubusercontent.com/119218812/229308144-8ded40ee-f242-4722-a215-87454520b44a.png)

## Full Sub
![Screenshot (74)](https://user-images.githubusercontent.com/119218812/229308151-15202fb0-4f40-4c89-b373-bbdf20aa0abb.png)

## Result:

Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
