Challenge: https://crackmes.one/crackme/61eec94433c5d413767ca64f

The solution of this challenge narrows down to the **sub_559C0AB771E9** where in the highlighted line (breakpointed) eax is compared with edx. Modified user's input is in edx and the flag is in eax. In each iteration one character of user's input is compared with the value of eax. In subroutine that I renamed to compare in the second screenshot, you can find that the length of the string is 30. After 30 iterations of the loop in **sub_559C0AB771E9**, we can find each character that is read from memory. The 30 numbers are as follows: 

six + six + thirty + thirty three + seven + seven + three + seven + thirty two + six + three + five + thirty five + three + five + seven + seven + seven + six + thirty six + seven + five + six + six + three + five + three + seven + thirty + seven

Our task is to supply an input in a way that writes those numbers into memory.

But, as I said first, modified user's input is in memory. The modifications happens in compare. In sub_562A85BC624B, if the ascii code of each character is even, it chooses to run loc_562A85BC630E where the ascii code is right shifted 4 times, or it is devided by 16. If it is even, it will be shifted to right only once, or divided by 2 (in the other subroutine). I wrote the script that for small numbers like 6, 7, 5, they are multiplied by 64 and for bigger ones they are multiplied by 2. This way, it makes sense for ascii codes. At the end, you can see the flag was found.

![Image 1](https://github.com/pyDeb/crackmes/blob/main/flag_eater_crackme/Screenshot%20from%202022-01-29%2015-14-23.png)

![Image 2](https://github.com/pyDeb/crackmes/blob/main/flag_eater_crackme/Screenshot%20from%202022-01-29%2015-15-58.png)

![Image 3](https://github.com/pyDeb/crackmes/blob/main/flag_eater_crackme/Screenshot%20from%202022-01-29%2016-11-37.png)
