## Name:Nidhish B
## Register Number:23014111
## Experiment:04-Implementation-of-Half-subtractor-and-Full-subtractor-circuit
 
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime

## Theory:
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor & Full Subtractor:

## Half Subtractor:
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)

Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Procedure:
1.Use module projname(input,output) to start the Verilog programmming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.Use each output to represnt onre for differnce and the other for borrow.

5.End the verilog program using keyword endmodule

## Program:
~~~
module DE_EXP_4(a,b,diff,borrow);
input a,b;
output diff,borrow;
assign diff=a^b;
assign borrow=~a&b;
endmodule
~~~

## RTL realization:
![image](https://github.com/Nidhish055/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145979818/af4dd46a-5d0d-411f-8663-82ea12f78efb)

## Truth Table:
![image](https://github.com/Nidhish055/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145979818/5a6e4b81-6b2b-405c-9b27-bb6454197478)

## Timing Diagram:
![image](https://github.com/Nidhish055/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145979818/1e63085d-ed46-4ade-95dc-5d216f1cdf67)


## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Program:

```
module DE_EXP_4_1(a,b,bin,borrow,diff);
input a,b,bin;
output diff,borrow;
assign diff=(a^b)^bin;
assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
endmodule
```

##  RTL realization:
![image](https://github.com/Nidhish055/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145979818/47eba206-f0e0-45cb-a9eb-6a2c2ab6d08d)

## Truth Table:
![image](https://github.com/Nidhish055/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145979818/1da0b231-ac43-4d24-942a-cc30ee2ebeaa)

## Timing Diagram:
![image](https://github.com/Nidhish055/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145979818/3eb2cf92-ad1e-47b7-96f2-f35c7f309709)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
