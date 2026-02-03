# 8-Bit-Arithmetic-Operations-using-8085
## Aim:
To perform 8-bit arithmetic operations such as addition, subtraction, multiplication, and division using the 8085 microprocessor.

## Apparatus Required:
•	Laptop with internet connection

## Algorithm:

### For Addition (With Carry Consideration):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Add the contents of registers A and B.
4.	If carry is generated, store carry in 4301H.
5.	Store the sum in memory location 4300H.
   
### Program:
LDA 1000H
MOV B,A
LDA 1001H
ADD B
STA 4300H
JC STORE_CARRY
HLT
STORE_CARRY:MVI A,01H
STA 4301H
HLT
### Output:
<img width="288" height="450" alt="image" src="https://github.com/user-attachments/assets/96952581-390b-4368-8cc0-d2867328226c" />
<img width="1529" height="594" alt="image" src="https://github.com/user-attachments/assets/35adc794-b25f-47f3-9030-7a102a856736" />
<img width="306" height="462" alt="image" src="https://github.com/user-attachments/assets/28905b1d-8582-4e8c-a94a-96b9c715819c" />

### For Subtraction (Considering Greater Number):
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Compare A and B.
4.	If A < B, swap the values of A and B to ensure positive result.
5.	Subtract the content of B from A.
6.	Store the result in memory location 4300H.

### Program:
LDA 1000H
MOV C,A
LDA 1001H
CMP C
JC SWAP
SWAP:
MOV B,A
MOV A,C
SUB B
STA 4300H
HLT

### Output:
<img width="294" height="463" alt="image" src="https://github.com/user-attachments/assets/035d2cfc-11e6-416f-b499-335775ca4dc0" />

<img width="1462" height="597" alt="image" src="https://github.com/user-attachments/assets/f753b492-5301-409c-968a-247a554bb990" />

<img width="298" height="365" alt="image" src="https://github.com/user-attachments/assets/be8e1bcb-9f01-4e83-b73f-01b3e8163c27" />

### For Multiplication:
1.	Load the first number from memory location 4200H into register A.
2.	Load the second number from memory location 4201H into register B.
3.	Multiply A and B using repeated addition.
4.	Store the result in memory locations 4300H and 4301H (if required for higher bits).

### Program:
LDA 1000H
MOV C,A
LDA 1001H
MOV B,A
MVI A,00H
LOOP:ADD C
DCR B
JNZ LOOP
STA 4300H
HLT
### Output:
<img width="298" height="469" alt="image" src="https://github.com/user-attachments/assets/ea105d2e-7151-4480-9d8d-302893c78df4" />
<img width="1445" height="590" alt="image" src="https://github.com/user-attachments/assets/9706f499-61bf-4e08-9253-056afb277aad" />
<img width="316" height="388" alt="image" src="https://github.com/user-attachments/assets/e659f91c-4a82-4fc4-bc2f-b11ebf6e4bc6" />

### For Division:
1.	Load the dividend from memory location 4200H into register A.
2.	Load the divisor from memory location 4201H into register B.
3.	Perform division using repeated subtraction.
4.	Store the quotient in 4300H and remainder in 4301H.

### Program:
LDA 3200H
MOV C,A
LDA 3201H
MOV B,A
MVI A,00H
LOOP:CMP B
JC END
SUB B
INR A
JMP LOOP
END: STA 3300H
MOV A,C
STA 3301H
HLT

### Output:
<img width="305" height="452" alt="image" src="https://github.com/user-attachments/assets/ab83b025-1c13-48b5-819f-1469847bcef5" />
<img width="325" height="437" alt="image" src="https://github.com/user-attachments/assets/54ad288b-3034-40c8-b78d-f6106ddba0bb" />
<img width="311" height="451" alt="image" src="https://github.com/user-attachments/assets/b64feb15-eda8-4d3e-8901-6d99675bcaa6" />
## Result:
The 8-bit arithmetic operations using the 8085 microprocessor have been successfully executed and verified using memory access for input and output.

