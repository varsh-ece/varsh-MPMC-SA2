## Aim
To Write an assembly language program in 8051 to count the number of even and odd numbers in an array of 10 elements and display the counts.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)
1.Initialize:
----
Set R0 (data pointer) to 30H.

Set R1 (Even Count) and R2 (Odd Count) to 0.

Set R3 (Loop Counter) to 10.

Loop (10 Times):

Load the byte from the address in R0 into the Accumulator (A).

Use RRC A (Rotate Right through Carry) to move the byte's Least Significant Bit (LSB) into the Carry Flag (C).

2.Check Carry (C):
---

If C = 0 (Even number), increment R1.

If C = 1 (Odd number), increment R2.

Increment R0 to point to the next byte.

Decrement R3 and repeat the loop until R3 = 0.

3.Finish:
---
Store the final Even Count (R1) in memory location 50H.

Store the final Odd Count (R2) in memory location 51H.

Halt the program. 


## Program (Ascending order)

````````````````````
ORG 00H
LJMP MAIN


MAIN:
MOV R0,#30H
MOV R1,#00H
MOV R2,#00H
MOV R3,#0AH

LOOP:
MOV A,@R0
RRC A
JNC EVEN_COUNT
INC R2
SJMP NEXT

EVEN_COUNT:
INC R1

NEXT:
INC R0
DJNZ R3, LOOP

FINISH:
MOV 50H,R1
MOV 51H,R2
SJMP $

END
````````````````````````````````

## OUTPUT

![WhatsApp Image 2025-10-24 at 08 12 13_12864bed](https://github.com/user-attachments/assets/f75b27a4-660f-4f78-8220-a2835b0ae56d)

![WhatsApp Image 2025-10-24 at 08 13 23_63fb7231](https://github.com/user-attachments/assets/1dca1023-e63c-423f-817a-462965659fbd)


---


## RESULT:
Thus  Write an assembly language program in 8051 to count the number of even and odd numbers in an array of 10 elements and display the counts.
done using 8051 keil software.

