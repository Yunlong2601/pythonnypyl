IT2153/IT2352/IT2553/IT2653/IT2852
 Data Structures & Algorithms
 TOPIC 05: RECURSION
 VERSION 1.0
 (CONTENT ADAPTED FROM: 
• DATA STRUCTURES & ALGORITHMS USING PYTHON. RANCE D. NECAISE, WILEY, 
1ST EDITION, 2011.
 • DATA STRUCTURES & ALGORITHMS IN PYTHON. MICHAEL T. GOODRICH, ROBERTO 
TAMASSIA & MICHAEL H. GOLDWASSER, WILEY, 1ST EDITION, 2013.)
Recursion
 2
Recursion
 Recursion
 ◦ Recursive Functions
 ◦ Classic example: Factorial function
 ◦ Properties of Recursion
 Recursion Call Tree
 Run Time Stack
Recursion
 Recursionis a process of solving problems by subdividing a 
larger problem into smaller versions of the itself and then 
solving the smaller, more trivial parts.
 Recursion is a powerful programming and problem-solving 
tool, BUT not always the most efficient.
 However, in some instances, recursion is the implementation 
of choice as it allows us to easily develop a solution for a 
complicated problem that may otherwise be difficult to solve.
 4
Recursive Functions
 A function that calls itself is known as a recursive function.
 Classic example – the Factorial function:
 ◦ n! = 1· 2· 3· ··· · (n-1)· n
 Recursive definition
 Python implementation
 # Factorial function
 # Assuming n >= 0
 def factorial(n):
 if n == 0:
 return 1
 else:
 return n * factorial(n-1)
 5
Properties of Recursion
 All recursive solutions must satisfy three rules or properties:
 ◦ A recursive solution must contain a base case
 ◦ A recursive solution must contain a recursive case.
 ◦ A recursive solution must make progress toward the base case.
 6
Properties of Recursion
 Base case:
 ◦ Terminating case and represents the smallest subdivision of the 
problem.
 ◦ Signals the end of the recursive calls.
 ◦ In factorial(), the base case occurred when n = 0.
 Recursive case:
 ◦ The case when the recursive function calls itself.
 ◦ In factorial(), the recursive case occurred when n > 0.
 How does factorial() ensure that it makes progress 
toward the base case?  And what will happen when it does 
not?
 7
Visualizing Recursion
 Recursion call tree
 ◦ A box for each recursive call
 ◦ An arrow from each caller to callee
 ◦ An arrow from each callee to caller showing 
return value
 Example
 call
 return 4*6 = 24
 factorial(4)
 call
 return 3*2 = 6
 factorial(3)
 call
 return 2*1 = 2
 factorial(2)
 call
 final answer
 return 1*1 = 1
 factorial(1)
 call
 factorial(0)
 return 1
 8
Recursion Call Tree
 # A sample program
 # containing three functions.
 def main():
 y = foo( 3 )
 bar( 2 )
 def foo( x ):
 if x % 2 != 0:
 return 0
 else:
 return x + foo( x-1 )
 def bar( n ):
 if n > 0:
 print( n )
 bar( n-1 )
 Draw the recursion call tree.
 What is the output of the program?
 main()
Recursion Call Tree
 # A sample program
 # containing three functions.
 def main():
 y = foo( 3 )
 bar( 2 )
 def foo( x ):
 if x % 2 != 0:
 return 0
 else:
 return x + foo( x-1 )
 def bar( n ):
 if n > 0:
 print( n )
 bar( n-1 )
 NOTE: The edges are listed left to right in the 
order the calls are made.
 main()
Behind the scenes …
 Each time a function is called, an activation record is created to maintain information related to 
the function:
 ◦ Return address – location of the next instruction to be executed when the function terminates
 ◦ Local variables
 When the function terminates, the activation record is destroyed.
 11
Behind the scenes …
 System must:
 ◦ Manage the collection of activation records.
 ◦ Remember the order
 in which they were created.  WHY?
 Allow the system to backtrack and return to the next statement in the 
previous function when an invoked function terminates.
 Using a Run Time Stack  Remember Stacks? LIFO? A data structure 
to be discussed in a later topic.
 12
Run Time Stack
 When the main() routine 
is executed, the first 
activation record is created 
and pushed onto the stack. 
When the factorial function, 
fact(), is called, the 
second activation record is 
created and pushed onto the 
stack.
 # Consider executing this code:
 def main():
 y = fact( 2 )
Run Time Stack
 The factorial 
function, fact(), is 
recursively called 
until the base case is 
reached with a value 
of n = 0.
Run Time Stack
 When the base case statement is 
executed, the activation record for the 
function call fact(0) is popped from 
the stack, and execution returns to the 
function instance fact(1).
 This process continues until all 



  
Data Structures & Algorithms 
 
 
AY2025 S1  Page 1 
Official (Closed) and Sensitive-Normal 
Data Structures & Algorithms 
Python Programming Assignment 2 Set A (60 marks) 
 
 
 
 
 
 
 
  
SUBMISSION REQUIREMENTS: 
 
1) Name the ZIP files containing your solutions according to the 
following requirements:  
 
• ZIP all Python files to be submitted into a zip file and 
named it as “ADMINNO_ASSN.zip”. For example: 
“123456F_ASSIGNMENT.zip”. 
 
2) At the beginning of every Python file to be submitted, include your 
“Name, Student Admin no. and Tutorial Group” as comments. 
 
3) Submission Due Date:  17 August 2025, 2359hrs 
 
4) The deliverable is to be submitted to your module tutor via Bright 
Space 
 
5) Late Submission:  Marks will be deducted accordingly to the NYP 
policy for late submission. 
 
6) Code review will be scheduled in week 16/17 during LAB and TUT 
sessions. There will be code-review and technical questions asked 
about the assignment completed by the student. Marks will be given 
during the code-review 
 
 
Data Structures & Algorithms 
 
 
AY2025 S1  Page 2 
Official (Closed) and Sensitive-Normal 
Student Management System Phase II 
 
User Requirements (60 marks) 
We have reached phase two of the project development. This assignment will build on the 
application (Studentship management program) which you have developed in assignment 1. 
The customer would like to add more features. 
 
1. Sort Students using Insertion Sort on the Student Name in 
descending order and display the outcome. 
• Display the Admin No in each pass to demonstrate how the 
sorting works. 
• After sorting, the changes are made permanent. (Marks 
will be deducted if the final results are not updated back 
into the collections after each sort) 
• Display the final sorted details of the Students in the 
repository. (Marks will be deducted if the final outcome is 
not displayed after each sort.) 
• Correctness of the algorithm: The implementation should 
correctly sort the input collections in descending order 
using the insertion sort algorithm. 
• Handling of boundary conditions: The implementation 
should handle boundary scenarios such as empty 
collections etc. 
• Efficiency: The implementation should have a reasonable 
time complexity.  
• Clarity: The code should be easy to read and understand, 
with meaningful variable/function names and relevant 
comments. 
• Modularity: The code should be modular with the sorting 
algorithm implemented in a separate function or method. 
10 marks 
2. Create a function to use Merge Sort to sort the Student in 
ascending order by Student Group followed by their AccGPA 
column. - Display the Admin No in each pass to demonstrate how the 
sorting works. - After sorting, the changes are made permanent. (Marks 
will be deducted if the final results are not updated back 
into the collections after each sort) - Display the final sorted details of the Students in the 
repository. (Marks will be deducted if the final outcome is 
not displayed after each sort.) - Correctness of the algorithm: The implementation should 
correctly sort the input collections in ascending order using 
the merge sort algorithm by Student Group followed by 
their AccGPA. - Handling of boundary conditions: The implementation 
should handle boundary scenarios such as empty 
collections etc. 
10 marks 
 
Data Structures & Algorithms 
 
 
AY2025 S1  Page 3 
Official (Closed) and Sensitive-Normal - Efficiency: The implementation should have a reasonable 
time complexity.  - Clarity: The code should be easy to read and understand, 
with meaningful variable/function names and relevant 
comments. - Modularity: The code should be modular with the sorting 
algorithm implemented in a separate function or method. 
3. Add a new menu and function to handle Student requests. - Correctness of the algorithm: Update the phase 1 codes to 
implement the new attribute request. 
 
4 marks 
3a Create a system so that the teacher can service request from 
the Students using a stack.  
Correctness of the algorithm: - Add a function in the application that allows the teacher to 
add a student’s request into the system using a new class 
object. - Creation and use of a new class object named 
“StudRequest” that contains Admin_No(String)  and 
Request (String). - Before allowing the object to be added to the stack, the 
function will also perform a sequential search to check if 
the Admin No already exists in the system.  - The object will only be allowed to be added if the request 
is from a valid student.  - The stack will allow duplicate requests to be added. - Clarity: The code should be easy to read and understand, 
with meaningful variable/function names and relevant 
comments. - Proper use of Stack ADT - Modularity: The code should be modular with the sorting 
algorithm implemented in a separate function or method. 
10 marks 
3b Create a function to allow the teacher to see the number of requests 
left in the queue. 
3 marks 
3c Create a function to allow teacher to handle the next request in the 
Queue. 
Correctness of the algorithm - The implementation should correctly allow the teacher to 
retrieve the request from the stack in the correct order. - Details of the request including the student details must be 
displayed correctly as in the screen capture - Once viewed and accepted, the request will be removed 
from the stack, and the remaining number of requests 
shown. - If the teacher is not ready to handle the request, the request 
will be sent to the back of the top of the stack - Handling of boundary conditions: The implementation 
should handle boundary scenarios such as empty stack etc. - Efficiency: The implementation should have a reasonable 
time complexity.  
12 marks  
 
Data Structures & Algorithms 
 
 
AY2025 S1  Page 4 
Official (Closed) and Sensitive-Normal - Clarity: The code should be easy to read and understand, 
with meaningful variable/function names and relevant 
comments. - Modularity: The code should be modular with the sorting 
algorithm implemented in a separate function or method. 
 
4 To improve on the display of all records.  
A function is to be added to allow the teacher to specify the 
number of records to display per row  - The implementation should correctly allow the teacher to 
decide on the number of records to display per row of data 
for all records. - Recursive function must be used - Once set, the value will apply to all calls to display all 
records. - The default is one record per row - Handling of boundary conditions: The implementation 
should handle boundary scenarios  - Efficiency: The implementation should have a reasonable 
time complexity.  - Clarity: The code should be easy to read and understand, 
with meaningful variable/function names and relevant 
comments. - Modularity: The code should be modular with the sorting 
algorithm implemented in a separate function or method. 
10 marks 
5 Update the menu with the new additional functions. 1 mark 
 
Note: Proper code discipline must be maintained. For example, proper use of classes 
and separation of files for each class for code readability and maintenance. 
 
 
activation records have been popped 
from the stack and the program 
terminates.
