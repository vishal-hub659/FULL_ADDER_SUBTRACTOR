# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**
![Screenshot 2024-11-28 182934](https://github.com/user-attachments/assets/359ff0d1-a349-4462-a9bb-f09953902e61)

Write the detailed procedure here
~~~
**Program:**
module de4 (a,b,cin,sum,carry,bo,diff);
    input a,b,cin;
    output sum,carry,bo,diff;
    assign sum=a^b^cin;
    assign carry=((a^b)&cin)|(a&b);
    assign diff=a^b^cin;
    assign bo=((~(a^b))&cin)|(~a)&b;
endmodule
module de42 (df,bo,a,b,bin);
output df;
output bo;
input a;
input b;
input bin;
wire w1,w2,w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(~w1&bin);
assign df=w1^bin;
assign bo=w2|w3;
endmodule

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. Developed by: vishal s
RegisterNumber:24008833
*/
~~~
**RTL Schematic**
![de4](https://github.com/user-attachments/assets/52ae510f-73fe-4349-a44f-e63c19a3f4d6)
![de42](https://github.com/user-attachments/assets/77c39acb-4d4b-409f-a30e-27068ce08249)

**Output Timing Waveform**
![de4 wave](https://github.com/user-attachments/assets/296501cf-7fe3-4e4c-8d56-2c5eb14f4868)
![de 42 wave](https://github.com/user-attachments/assets/0e761186-6acf-404f-b644-20826a674980)

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



