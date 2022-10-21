# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
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
~~~
STEP 1:
Use module projname(input,output) to start the Verilog programmming.

STEP 2:
Assign inputs and outputs using the word input and output respectively.

STEP 3:
Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

STEP 4:
Use each output to represnt onre for differnce and the other for borrow.

STEP 5:
End the verilog program using keyword endmodule.
~~~


## Program:
~~~
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by:Manoj M
RegisterNumber: 212221240027

HALF SUBRACTOR:

module subractor(A,b,diff,borrow);
input A,b;
output diff,borrow;
wire X;
xor(diff,A,b);
not(X,A);
and(borrow,X,b);
endmodule


 FULL SUBRACTOR:

 module fullsub(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule 
~~~

## Output:
### HALF SUBTRACTOR:
![1](https://user-images.githubusercontent.com/94588708/197110709-d88b8357-0583-4ae4-8666-58837fe7614d.png)

### LOGIC SYMBOL:
![2](https://user-images.githubusercontent.com/94588708/197110734-3e5d07c9-d134-4e36-b5fa-12cc964c13d3.png)

### RTL REALIZATION:
![3](https://user-images.githubusercontent.com/94588708/197111073-82f4d201-c804-4197-8385-b5fb51eb6f8c.png)

### TIMING DIAGRAM:
![4](https://user-images.githubusercontent.com/94588708/197111088-2e6cfb68-1182-4a52-a10f-b50e5fd13277.png)

### FULL SUBTRACTOR:
### TRUTH TABLE:
![5](https://user-images.githubusercontent.com/94588708/197111333-9d9485cd-621d-4190-9148-ca96d872b3f3.png)

### LOGIC SYMBOL:
![6](https://user-images.githubusercontent.com/94588708/197111382-d8629a45-7462-481f-9b46-a393fb5d6442.png)
### RTL REALIZATION:

![7](https://user-images.githubusercontent.com/94588708/197111578-3b463aa0-a3e3-4513-a3d7-657ed3c9861c.png)

### TIMING DIAGRAM:
![8](https://user-images.githubusercontent.com/94588708/197111597-39f75d75-06a3-4fde-b53d-bef9bb5d0402.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
