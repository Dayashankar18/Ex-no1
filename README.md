# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<<img width="1024" height="1536" alt="add_flowchart" src="https://github.com/user-attachments/assets/c1947a37-7253-4cb7-9bac-8909a0519dc0" />" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV CL,00H
MOV AX,1234H
MOV BX,124H
ADD AX,BX
JNC L1
INC CL
L1:MOV SI,1200H
MOV [SI], AX
MOV [SI+2], CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|           1200            |           58              |
|           1201            |         13             |

#### Manual Calculations

(Add your calculation here)

---

## OUTPUT IMAGE FROM MASM SOFTWARE
<<img width="642" height="157" alt="Screenshot (47)" src="https://github.com/user-attachments/assets/66720d8e-3ada-41df-91a8-16f4d85210d5" />


## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<"<img width="1024" height="1536" alt="flowchart_mul" src="https://github.com/user-attachments/assets/1eea2aa2-39d3-4492-b2d0-32a0f8e3bac4" />
 />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV CL,00H
MOV AX,1250H
MOV BX,1200H
SUB AX,BX
JNC L1
INC CL
L1:MOV SI,1200H
MOV [SI], AX
MOV [SI+2], CL
MOV AH,4CH
INT 21H
CODE ENDS
END

```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|    1200                 |         50               |
|    1201                 |         00               |

#### Manual Calculations

(Add your calculation here)

---


## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="638" height="130" alt="Screenshot (61)" src="https://github.com/user-attachments/assets/8d47f89b-ca2f-4f9c-9518-53e513b5d703" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV CL,00H
MOV AX,1234H
MOV BX,124H
MUL AX
JNC L1
INC CL
L1:MOV SI,1200H
MOV [SI], AX
MOV [SI+2], CL
MOV AH,4CH
INT 21H
CODE ENDS
END

```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------ ------------------ |
|     1200                   |        90                  |
|     1201                |           5A              |

#### Manual Calculations

(Add your calculation here)

---

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="638" height="130" alt="Screenshot (61)" src="https://github.com/user-attachments/assets/38395367-0af4-447c-b9e9-9731e5f489a0" />


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE

ORG 1000H

    MOV CL, 00H        ; Clear CL (optional flag/remainder indicator)

    MOV AX, 0084H     ; Dividend (low word)
    MOV BX, 0004H     ; Divisor
    MOV DX, 0000H     ; Clear DX before division

    DIV BX             ; AX = AX / BX, DX = remainder

L1:
    MOV SI, 1200H
    MOV [SI], AX       ; Store QUOTIENT at 1200H
    MOV [SI+2], DX     ; Store REMAINDER at 1202H

    MOV AH, 4CH
    INT 21H

CODE ENDS
END

```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     1200                |       21                 |
|     1201                |       00                 |

#### Manual Calculations

(Add your calculation here)

---
## OUTPUT FROM MASM SOFTWARE

<img width="644" height="147" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/8cd07269-8710-4b6b-8942-d1d67637db72" />


## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

