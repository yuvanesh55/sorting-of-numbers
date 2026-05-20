# sorting-of-numbers
## Aim
To write and execute an Assembly Language Program for sorting data in Ascending and  descending order using 8051 microcontroller on Keil software.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)
1. Initialize the register **R7** with count (number of elements).  
2. Get the first two elements into two registers.  
3. Compare the two elements:  
   - If the value in register **R0** is lower, exchange **A** and **R0** data.  
   - Otherwise, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0** → if yes, move the register **R0 & A**.  
5. Increment pointer and decrement **R7**.  
6. If **R7 ≠ 0**, repeat from Step 2.  
7. Otherwise, stop the program.  
---

## Program (Ascending order)

```
ORG 0000H
MOV R4, #04H ；Number of passes (N-1)
OUTER: MOV R3, #04H ； Inner 1oop counter
MOV R0,#50H ；Array starting address
INNER: MOV A, @R0
MOV B, A
INC R0
CLR C
SUBB A,@R0 ； Compare adjacent elements
JC NO_SWAP ;If A< @RO (Carry), no swap
；Exchange elements
MOV A, @R0
ХСН А, В
MOV @R0, A 
DEC RO 
MOV A, B 
XСH A, B 
MOV @R0,A 
INC R0
NO_SWAP: DJNZ R3, INNER
DJNZ R4, OUTER
END

```
## OUTPUT(Ascending order)


<img width="774" height="261" alt="WhatsApp Image 2026-05-16 at 11 33 18" src="https://github.com/user-attachments/assets/1e131530-aed5-42e4-9b57-d749825d4a3f" />


---

## Algorithm(Descending order)
1. Initialize the register **R7** with count.  
2. Get first two elements in two registers.  
3. Compare the two elements of data:  
   - If the value of **R0** register is high, then exchange **A** and **R0** data.  
   - Else, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0**, then move the contents of **R0** and **A**.  
5. Again increment pointer and decrement **R7**.  
6. Check if **R7 = 0**:  
   - If **No**, repeat the process from Step 2.  
   - If **Yes**, stop the program.  
---
## Program (Descending order)

```
ORG 0000H

MOV R4,#04H        ; Number of passes

OUTER: MOV R3,#04H ; Inner loop counter
       MOV R0,#50H ; Starting address

INNER: MOV A,@R0   ; Get first element
       MOV B,A

       INC R0      ; Next element

       CLR C
       SUBB A,@R0  ; Compare two elements

       JNC NO_SWAP ; If first > second, no swap

       ; Swap elements

       MOV A,@R0
       XCH A,B
       MOV @R0,A

       DEC R0
       MOV A,B
       MOV @R0,A

       INC R0

NO_SWAP:
       DJNZ R3,INNER
       DJNZ R4,OUTER

END

```
## OUTPUT(Descending order)

<img width="751" height="287" alt="image" src="https://github.com/user-attachments/assets/739dfa93-7df8-4332-aaa6-ea9c6c0167cb" />

---
## RESULT:
Thus the sorting of given data was done using 8051 keil software.
