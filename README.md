# Program to Reverse an Array in 8086 Assembly Language
# AIM:

To write an 8086 assembly language program to reverse the elements of an array andstore the reversed array in another memory location.

### APPARATUS REQUIRED:
- Personal computer
- Masm software

## ALGORITHM:
1.Start the program
 - Initialize the code segment and data segment if required.
2. Set up pointers
- Load the starting address of the input array (1200h) into SI (source index).
- Load the starting address of the output array (1300h) into DI (destination index).
3 .Set the loop counter
- Load CX with the number of elements in the array (e.g., 5).
4. Move SI to the last element of input array
-  Add (number of elements - 1) to SI so that it oints to the last element
5. start the loop Repeat until all elements are reversed:
   - a. Copy the element at [SI] intoDI].
   - b. Decrement SI to move backward in the input array.
   - c. Increment DI to moveforward in the output array.
   - d. Decrement CX automatically using the loop instruction.
6. End the loop
   - When CX = 0, all elements are reversed.
7. Terminate the program
- Use DOS interrupt int 21h with AH = 4Ch to exit.
  
## PROGRAM:
```
code segment
assume cs:code, ds:code
org 1000h
start:
   mov si,1200h
   mov di,1300h
   mov cx,05h
   add si,04h

l1: mov al,[si]
    mov [di],al
    dec si
    inc di
    loop l1

    mov ah,4Ch
    int 21h
code ends
end start
```
## OUTPUT:
<img width="635" height="431" alt="Screenshot 2025-10-30 210134" src="https://github.com/user-attachments/assets/49fd5860-5521-4321-af4b-f9e7a50abe1b" />

## RESULT:
Program successfully reverses the array elements and stores them in another memory
location.
