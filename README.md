1.  AREA PROGRAM, CODE, READONLY 
EXPORT __main 
__main 
MOV R0,#10 
MOV R1, #0 
loop  
ADD R1,R0 
SUBS R0,#01 
BNE loop 
here B here 
END 

2. AREA PROGRAM, CODE, READONLY 
EXPORT __main 
__main 
MOV R0, #10 
MOV R1, #01 
loop 
SUBS R0, R1 
CMP R0, #00 
BNE loop 
here  
B here 
END 

 2b) Write an ALP to count numbers from 0 to 10 
main 
MOV R0, #00 
MOV R1, #01 
loop  
Program: 
AREA PROGRAM, CODE, READONLY 
EXPORT main 
ADD R0,R1 
CMP R0, #10 
BNE loop 
here B here 
END 

3. AREA PROGRAM, CODE, READONLY 
EXPORT main 
main 
MOV R0, #45 
MOV R1, #50 
loop  
CMP R0, R1 
SUBGT R0,R0,R1 
SUBLT R1, R1, R0 
BNE loop 
stop  
B stop 
END 

Calculate GCD without using SUBGT/SUBLT instructions 
AREA PROGRAM, CODE, READONLY 
EXPORT main 
main 
MOV R0, #45 
MOV R1, #50 
Loop CMP R0, R1 
BGE endw 
BGT cond1 
B cond2 
cond1 SUB R0, R1 
B loop 
cond2 SUBR1,R0 
B loop 
endw 
here B here 
END 

4.   Write an ALP to multiply two 16 bit binary numbers. 
AREA multiply, CODE, READONLY 
ENTRY 
EXPORT  main 
main 
MOV r1,#6400 
MOV r2,#3200 
MUL r3,r1,r2 
NOP 
NOP 
END

5.Write an ALP to find factorial of a number. 
AREA FACTORIAL , CODE, READONLY 
ENTRY 
EXPORT  main 
main 
MOV r0, #7 
MOV r1,r0 
FACT SUBS r1, r1, #1 
BEQ STOP 
MUL r3,r0,r1; 
MOV r0,r3 
BNE FACT 
STOP NOP 
NOP 
NOP 
END

6. ) Write an ALP to add two 64 bit numbers. 
AREA ADDITION , CODE, READONLY 
ENTRY 
;Mark first instruction to execute START 
EXPORT  main 
main 
LDR R0,=0X1234E640 
LDR R1,=0X43210010 
LDR R2,=0X12348900 
LDR R3,=0X43212102 
ADDS R4,R1,R3 
ADC R5,R0,R2 
NOP 
NOP 
NOP 
END
