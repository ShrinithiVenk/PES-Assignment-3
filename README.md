# PES-Assignment-3
The assignment contains a program that involves blinking red, green, blue, and white LEDs with certain (specified) delays. A capacitive touch sensor has also been used to make a specific pattern (color) of LEDs. Apart from the files that IDE uses for building a project, Blinkled.c contains the primary code for the project. The Code: There are, in total, three .c files (blinkled.c, touch.c) and two .h files (touch.h, blinkled.h)

Extra credit:
1. What is the address of your main() function, and what is the size in bytes of your delay() function? 
### ANS: 00000694
2. Size in bytes for the delay() function : 
### ANS: (in Hex) 1f98-1fc8 = (in decimal) 8136 - 8188 = 48 bytes.
Show the full disassembly of your delay() function, adding comments to each line to explain the functionality. 
   1. 1f98:	b580      	push	{r7, lr} //Pushes the data to the stack
   2. 1f9a:	b084      	sub	sp, #16 //Subtracts value from the stack pointer
   3. 1f9c:	af00      	add	r7, sp, #0 //Adds value to the stack pointer and Stores it in R7
   4. 1f9e:	6078      	str	r0, [r7, #4] //Loads the data value from (R7+4) into R0 register
   5. 1fa0:	2300      	movs	r3, #0 //Moves value 0 into R3 register
   6. 1fa2:	60fb      	str	r3, [r7, #12] //Loads the data value from (R7+12) into R3 
   7. 1fa4:	687a      	ldr	r2, [r7, #4] //Stores the value of R7 to the immediate offset of 4 to R2 register 
   8. 1fa6:	0013      	movs	r3, r2 //Moves R2 to R3
   9. 1fa8:	015b      	lsls	r3, r3, #5 //The LSL instruction updates the N and Z flags according to the result
   10. 1faa:	1a9b      	subs	r3, r3, r2 //Subtracts R3 from R2 and stores value in R3
   11. 1fac:	009b      	lsls	r3, r3, #2 //The LSL instruction updates the N and Z flags according to the result
   12. 1fae:	189b      	adds	r3, r3, r2 //Adds R3 and R2 and stores value in R3
   13. 1fb0:	011b      	lsls	r3, r3, #4 //The LSL instruction updates the N and Z flags according to the result
   14. 1fb2:	60fb      	str	r3, [r7, #12] //Loads the data value from (R7+12) into R7 register
   15. 1fb4:	46c0      	nop			; (mov r8, r8) //Null
   16. 1fb6:	68fb      	ldr	r3, [r7, #12] //Stores the value of R7 to the immediate offset of 12 to R3 register 
   17. 1fb8:	1e5a      	subs	r2, r3, #1 //Subtracts (R3-1) and stores value in R2
   18. 1fba:	60fa      	str	r2, [r7, #12] //Loads the data value from (R7+12) into R2 register
   19. 1fbc:	2b00      	cmp	r3, #0 //Compare R3 with 0
   20. 1fbe:	d1fa      	bne.n	1fb6 <delay+0x1e> //If data in R3 is not equal to 0, it goes back to address location 0x1e (iterate the loop again)
   21. 1fc0:	46c0      	nop			; (mov r8, r8) //Null
   22. 1fc2:	46c0      	nop			; (mov r8, r8) //Null
   23. 1fc4:	46bd      	mov	sp, r7 //Moves value from R7 register to the stack pointer
   24. 1fc6:	b004      	add	sp, #16 //Adds value 16 to the stack pointer 
   25. 1fc8:	bd80      	pop	{r7, pc} //Retrieves the data from the stack



### Peer Code Review comments:
Comments received from - Mrunal Yadav (myra3714@colorado.edu)

1. Delay timing can be included in the delay function to improve code readability. 
2. Introduce polling time for the on time period.
3. Intriduce polling time for off time period.
3. Intendation can be checked and corrected to improve code readability. 
4. Comments for some functions can be introduced.
5. Debug was not mentioned for printf statements.





