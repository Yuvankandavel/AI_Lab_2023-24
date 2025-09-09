# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE:  06-09-2025                                                                          
### REGISTER NUMBER : 212223060315
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

1. ∀x(Food(x)→Likes(John,x))
2. Food(Apples)
3. Food(Chicken)
4. ∀x(Eats(Bill,x)→Eats(Sue,x))
5. Eats(Bill,Peanuts)
   
### Output:
1. Food(x)→Likes(John,x)≡¬Food(x)∨Likes(John,x)
2. {Food(Apples)}
3. {Food(Chicken)}
4. ¬Eats(Bill,x)∨Eats(Sue,x)
5. {Eats(Bill, Peanuts)}

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
1. { ¬Easy(x), Likes(steve,x) }
2. { ¬InDept(x,have_fun), Easy(x) }
3. { InDept(bk301,have_fun) }
4. { ¬Likes(steve,bk301) }

### Output:
1. { ¬Easy(bk301), Likes(steve,bk301) }.
2. { ¬Likes(steve,bk301) } on Likes(steve,bk301):{ ¬Easy(bk301) }.
3. { ¬InDept(bk301,have_fun), Easy(bk301) }.
4. { InDept(bk301,have_fun) } on InDept(bk301,have_fun):{ Easy(bk301) }.

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:

¬American(p)∨¬Weapon(i)∨¬HostileTo(n,america)∨¬Sold(p,i,n)∨Criminal(p)

{ ¬American(west), ¬Weapon(missiles), ¬HostileTo(nano,america), ¬Sold(west,missiles,nano), Criminal(west) }
### Output:
→ R1: { ¬Weapon(missiles), ¬HostileTo(nano,america), ¬Sold(west,missiles,nano), Criminal(west) }

→ R2: { ¬HostileTo(nano,america), ¬Sold(west,missiles,nano), Criminal(west) }

→ R3: { ¬Sold(west,missiles,nano), Criminal(west) }

→ R4: { Criminal(west) }

→ empty clause ⊥ (contradiction)
### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
