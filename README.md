# PES-Assignment-3
The assignment contains a program that involves blinking red, green, blue, and white LEDs with certain (specified) delays. A capacitive touch sensor has also been used to make a specific pattern (color) of LEDs. Apart from the files that IDE uses for building a project, Blinkled.c contains the primary code for the project. The Code: There are, in total, three .c files (blinkled.c, touch.c) and two .h files (touch.h, blinkled.h)

Extra credit:
1. What is the address of your main() function, and what is the size in bytes of your delay() function? 
## ANS: 00000694
2. Size in bytes for the delay() function : 
## ANS: (in Hex) 1f98-1fc8 = (in decimal) 8136 - 8188 = 48 bytes.
3.  Show the full disassembly of your delay() function, adding comments to each line to explain the functionality. 
    1f98:	b580      	push	{r7, lr} //Pushes the data to the stack
    1f9a:	b084      	sub	sp, #16 //Subtracts value from the stack pointer
    1f9c:	af00      	add	r7, sp, #0 //Adds value to the stack pointer and Stores it in R7
    1f9e:	6078      	str	r0, [r7, #4] //Loads the data value from (R7+4) into R0 register
    1fa0:	2300      	movs	r3, #0 //Moves value 0 into R3 register
    1fa2:	60fb      	str	r3, [r7, #12] //Loads the data value from (R7+12) into R3 
    1fa4:	687a      	ldr	r2, [r7, #4] //Stores the value of R7 to the immediate offset of 4 to R2 register 
    1fa6:	0013      	movs	r3, r2 //Moves R2 to R3
    1fa8:	015b      	lsls	r3, r3, #5 //The LSL instruction updates the N and Z flags according to the result
    1faa:	1a9b      	subs	r3, r3, r2 //Subtracts R3 from R2 and stores value in R3
    1fac:	009b      	lsls	r3, r3, #2 //The LSL instruction updates the N and Z flags according to the result
    1fae:	189b      	adds	r3, r3, r2 //Adds R3 and R2 and stores value in R3
    1fb0:	011b      	lsls	r3, r3, #4 //The LSL instruction updates the N and Z flags according to the result
    1fb2:	60fb      	str	r3, [r7, #12] //Loads the data value from (R7+12) into R7 register
    1fb4:	46c0      	nop			; (mov r8, r8) //Null
    1fb6:	68fb      	ldr	r3, [r7, #12] //Stores the value of R7 to the immediate offset of 12 to R3 register 
    1fb8:	1e5a      	subs	r2, r3, #1 //Subtracts (R3-1) and stores value in R2
    1fba:	60fa      	str	r2, [r7, #12] //Loads the data value from (R7+12) into R2 register
    1fbc:	2b00      	cmp	r3, #0 //Compare R3 with 0
    1fbe:	d1fa      	bne.n	1fb6 <delay+0x1e> //If data in R3 is not equal to 0, it goes back to address location 0x1e (iterate the loop again)
    1fc0:	46c0      	nop			; (mov r8, r8) //Null
    1fc2:	46c0      	nop			; (mov r8, r8) //Null
    1fc4:	46bd      	mov	sp, r7 //Moves value from R7 register to the stack pointer
    1fc6:	b004      	add	sp, #16 //Adds value 16 to the stack pointer 
    1fc8:	bd80      	pop	{r7, pc} //Retrieves the data from the stack



## Peer Code Review comments:
Comments received from - Mrunal Yadav (myra3714@colorado.edu)

1. Delay timing can be included in the delay function to improve code readability. 
2. Introduce polling time for the on time period.
3. Intriduce polling time for off time period.
3. Intendation can be checked and corrected to improve code readability. 
4. Comments for some functions can be introduced.
5. Debug was not mentioned for printf statements.



## Reviewed for: Mrunal Yadav 
Code reviewer name: Shrinithi Venkatesan (shve4446@colorado.edu)

1. A Macro can be defined in place of every shift operation mentioned for setting and clearing functions. Eg: define MASK(x) (1 << PIN) and use MASK macro.
2. Delay needs to be uncommented in the main.c file. It affects the logic of the program.
3. In Touch files, OFFSET can be cleared to zero and then the respective touch ranges can be calculated for sensor values (i.e Touch count value - Offset value).
4. Introduce comments for some functions.
5. Intendations can be corrected to improve code readability. 
6. Naming of the variables can be modified to improve readability.


