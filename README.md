# LARGEST-OF-N-NUMBERS

# FINDING THE LARGEST NUMBER USING 8051 (Keil)

## AIM:
To write and execute an Assembly language program to find the largest number from a given set of $N$ numbers stored in memory using 8051 Keil. The final result should be available in the Accumulator (A).

---
## APPARATUS REQUIRED:
- Personal computer with Keil software
---

## ALGORITHM:
1. **Start**
2. **Initialize Pointer:** Set DPTR to the starting address of the count $N$ ($\text{4000H}$).
3. **Read Count:** Read the value of $N$ into the Accumulator (A), and copy it to a register like R7 for use as a loop counter.
4. **Read First Number:** Increment DPTR to point to the first number. Load this number into $\text{A}$ and then copy it to a register (R0) to be the initial 'Largest Number'.
5. **Check Count:** Decrement the loop counter R7. If $R7=0$ (i.e., $N$ was 1), skip to the end.
6. **Loop:**
a. Increment DPTR to point to the next number.
b. Read the new number into $\text{A}$.
c. Compare: Subtract the current 'Largest Number' ($\text{R0}$) from the new number ($\text{A}$).
d. Update Largest: If the result of the subtraction shows $\text{A} > \text{R0}$ (Carry flag $C=0$ after $\text{SUBB}$), replace $\text{R0}$ with $\text{A}$.
e. Decrement and Loop: Decrement R7 and jump back to the start of the loop if $R7 \neq 0$.
7. **Output:** Move the final 'Largest Number' from R0 to the Accumulator (A). The result is now in the AL register.End (Halt the program).
8. **End**

---

## FLOWCHART:
<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/fe171881-8691-4f64-acbd-4794827ad66e" /> 

---

## PROGRAM:
```asm
org 00h
mov r0, #05h
mov r1, #30h
mov 40h, @r1
up:inc r1
mov a, @r1
cjne a, 40h, d1
d1:jc d2
mov 40h, @r1
d2:djnz r0,up 
end 
```	
<img width="766" height="396" alt="Screenshot 2025-10-24 160033" src="https://github.com/user-attachments/assets/38d620cb-d590-4f3e-a1b2-bf0f33427560" />


--- 

## OUTPUT:

<img width="919" height="210" alt="Screenshot 2025-10-24 160141" src="https://github.com/user-attachments/assets/5fb82025-56ef-4eef-9310-d4ddbc294472" />


<img width="935" height="256" alt="Screenshot 2025-10-24 160102" src="https://github.com/user-attachments/assets/2e038f01-9aff-436a-91ad-90553108b383" />



---

## RESULT:

Thus, the largest number from a given set of $N$ numbers was calculated and its value was successfully determined and made available in the Accumulator (A) using 8051 Keil.

---
