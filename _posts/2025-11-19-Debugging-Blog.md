<style>
  .image-container {
    text-align: center; 
    margin-top: 20px;   
  }

  .image-container img {
    border: 5px solid #000;  
    padding: 5px;           
    border-radius: 8px;      
  }
</style>


  

 JANNATUL PRITY 
 <br>
 11-19-25 
 <br>
 DEBUGGING BLOG 

Debugging is usually defined as the process of finding and fixing errors or bugs in the source code of any software. Debugging ensure that your code runs properly with out any mistakes, different programming languages have various debugging methods due to the difference in structure of the language models. Specifically we will be going into the process of debugging in python.

The debugging process in Python code consists of identifying, analyzing, and then resolving the errors in your code. This is a crutial part of being a programmer making sure the quality and reliablilty of the code is accurate. There are various error types such as, Syntax Errors, Runtime Errors, and Logical Errors. Identifying the type of error could be confusing but there are various things that you can look out for in your code to identify the type of error. Syntax error is an error that consists of violations of Python's grammar rules, preventing code execution. On the other hand, Runtime errors are problems encountered during the programs execution, even with correct syntax. Lastly, Logical erros are the most challenging to identify, its when the code runs without errors but produces incorrect or unexpected results. 

Then after identifying the error, you have to analyze it to define what specific type of error it is. Once that is done, now you can begin working toward a solution. In Python, this often means checking the traceback message,, which tells you exactly where the problem occured, reviewing the logic of your code, and using debugging tools such as print statements or the built in debugger. Print statements also allow you to track the errors your making step by step. After testing possible fixes, you can then run the code again to make sure that the issue is fully resolved.

Example #1: 

'''
text = "Hello, world, my name is"
count = 0

for char in text:
    if char == "":
       count += 1

print(count)

'''

Here we have an example of a code that is supposed to count how many spaces are in the given string, but it doesn't work because the condition inside the <strong> if statement </strong> is incorrect. In this case the programmer wrote char == "", which checks for an empty string, not a space. Since non of the characters in the text are empty strings, the counter never increases. 

In order to fix the bug you must need to add a space character. That means adding a space inside the quotation marks. 

''' 
if char == " ":
    count += 1
'''

Example #2: 

'''
print("give me a number")
n = input()

for num in range(1, n):
    if num % 2 < 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")

'''

This code is supposed to determine whether each number from the given set is odd or even, but it contains several errors. First, the input from the user is automatically read as a string, not a number because of this, the range 1 to n won't work at all. Another issue is that the condition num % 2 < 0 is incorrect, remaineders from % 2 are never negative, so this line will never identify even numbers correctly. The loop also stops at n - 1, meaning it won't include the final number the user enters. 

To fix the code you have to convert the input to an integer using int(), and add +1 to the range so it includes the number n, and lastly, use == 0 instead of < 0 so the code correctly checks if a number is even.

'''
print("give me a number")
n = int(input())

for num in range(1, n + 1):
    if num % 2 == 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")

'''


