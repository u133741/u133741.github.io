# Flqarl

### Main
![Main function image][00]   
The flow of the main function is the following:

1. Prints "Enter the password to continue".
2. It asks a password.
3. Checks if it is correct with **check_password** function.
4. **r15** is tested.
    * 4.1 If it is equal to **0** "Invalid password; try again" is printed and the program ends.
    * 4.2 If it is **not** equal **0** (this is what it has to be achieved), it prints "Access Granted!" and the door is opened.

### Check Password
![Main function image][01]   
I can see that the password is hard coded. It is comparing the password's **WORDS** (0x5057, 0x6e32, 0x0734 and 0x7b45) with my input. If the input is correct, **0x1** is moved to **r15**, otherwise **0x0**. This is done in a weird way, **r15** gets the value from **r14** at the end of the function (mov r14, r15). If any comparison fails, the flow jumps to address **0x44ac** (clr r14), clearing **r14**s value. **r14** receives **0x1** after the third comparison and if the last one is correct, the flow jumps to **0x44ae** avoiding the order that clears **r14**.

### Solution
In this case the solution was: **50576e3207347b45**

[00]: img/Flqarl_00.png
[01]: img/Flqarl_01.png