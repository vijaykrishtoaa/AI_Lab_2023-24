# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
To write a logic program to design a circuit like half adder and half subtractor.
###  Algorithm:
1. Start the Program
2. Design a AND gate logic if both inputs are 1 then output is 1.
3. Design a OR gate logic if any one of input is 1 then output is 1.
4. Design a XOR gate logic if both inputs are different then output is 1.
5. Design a NOT gate logic if input is 0 then output is 1.
6. Design a half adder and half subtractor using the rules.
7. Test the logic.
8. Stop the program.

### Program:
and(0,0,0).
and(0,1,0).
and(1,1,1).
and(1,0,0).
xor(1,0,1).
xor(1,1,0).
xor(0,1,1).
xor(0,0,0).
not(0,1).
not(1,0).
or(0,0,0).
or(0,1,1).
or(1,1,1).
or(1,0,1).
halfadder(A,B,Sum,Carry):-
    xor(A,B,Sum),
    and(A,B,Carry).
halfsubtractor(A, B, Difference, Borrow):-
    xor(A, B, Difference),
    not(A, NA),
    and(NA, B, Borrow).










### Output:
<img width="922" height="105" alt="image" src="https://github.com/user-attachments/assets/1b8b233b-97c3-471b-ac16-a9aa26f05d0e" />



### Result:
Thus the truth table of circuit verified sucessfully.
