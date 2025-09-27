# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
likes(john,X):-food(X).
food(apple).
food(chicken).
food(peanuts).
eats(bill,X):-eats(sue,X).
eats(bill,peanuts).

### O![WhatsApp Image 2025-09-27 at 08 19 14_2f54971e](https://github.com/user-attachments/assets/31931a09-91fe-471c-b003-94ebb85faf54)
utput:

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
like(steve,X):-easycourse(X).
hard(sciencecourse).
easycourse(X):-course(X,fundept).
course(bk301,fundept).

### Output:
![WhatsApp Image 2025-09-27 at 08 19 38_523f4c7e](https://github.com/user-attachments/assets/1ec778fb-9af6-42d3-b56a-0c262aea6351)

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:
crime(X):-american(X),weapon(Y),sells(X,Y,Z),hostile(X,Z).
hostile(X,Z):-enemy(Z,X).
enemy(nano,west).
american(west).
weapon(Y):-missile(Y).
missile(m1).
owns(nano,m1).
sells(west,Y,nano):-owns(nano,Y),missile(Y).

### Output:
![WhatsApp Image 2025-09-27 at 08 20 01_d9c6937f](https://github.com/user-attachments/assets/5c83b822-963f-482d-ab26-ae8da11db723)

### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
