# PES-Assignment-3
The assignment contains a program that involves blinking red, green, blue, and white LEDs with certain (specified) delays. A capacitive touch sensor has also been used to make a specific pattern (color) of LEDs. Programing Environment: MCUXpresso IDE with KL25Z128VLK4 board SDK is used for programing. Apart from the files that IDE uses for building a project, Blinkled.c contains the primary code for the project. The Code: There are, in total, three .c files (blinkled.c, touch.c) and two .h files (touch.h, blinkled.h)

Peer Code Review comments:
Comments received from - Mrunal Yadav (myra3714@colorado.edu)

1. Delay timing can be included in the delay function to improve code readability. 
2. Introduce polling time for the on time period.
3. Intriduce polling time for off time period.
3. Intendation can be checked and corrected to improve code readability. 
4. Comments for some functions can be introduced.
5. Debug was not mentioned for printf statements.



Reviewed for: Mrunal Yadav (myra3714@colorado.edu)

1. A Macro can be defined in place of every shift operation mentioned for setting and clearing functions. Eg: define MASK(x) (1 << PIN) and use MASK macro.
2. Delay needs to be uncommented in the main.c file. It affects the logic of the program.
3. In Touch files, OFFSET can be cleared to zero and then the respective touch ranges can be calculated for sensor values (i.e Touch count value - Offset value).
4. Introduce comments for some functions.
5. Intendations can be corrected to improve code readability. 
6. Naming of the variables can be modified to improve readability.


