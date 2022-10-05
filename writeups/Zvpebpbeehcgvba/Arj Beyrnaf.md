# Arj Beyrnaf

### Main
![Main function image][00]   
The flow of the main function is the following:

1. Calls **create_password**.
2. Prints "Enter the password to continue".
3. It asks a password.
4. Checks if it is correct with **check_password** function.
5. **r15** is tested.
    * 5.1 If it is equal to **0** "Invalid password; try again" is printed and the program ends.
    * 5.2 If it is **not** equal 0 (this is what it has to be achived), it prints "Acess Granted!" and the door is opened.

There are two interesting functions, **create_password** and **check_password**. I'm going to explain both of them.

### Create password
![Create password function image][01]   
As it can be seen, 8 hardcoded bytes (7 + null byte) are being written in memory from address 2400 to 2407 (0x7e, 0x7b, 0x3f, 0x60, 0x32, 0x27, 0x6f and 0x00).

### Check password
![main function][02]   
As said before, the password is stored in range **2400-2407** (red box). **r15**s value is **439c** (the start of my input, blue box). Here the program will compare one by one if they bytes of the password and the input are the same. If they are, **0x1** is moved to **r15**. Otherwise **r15** is cleared.

### Solution
In this case the solution was: **7e7b3f6032276f**

[00]: img/Arj_Beyrnaf_00.png
[01]: img/Arj_Beyrnaf_01.png
[02]: img/Arj_Beyrnaf_02.png