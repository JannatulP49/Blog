 <h2>
 JANNATUL PRITY 
 <br>
 11-19-25 
   <hr>
 </h2>
 <br>

<h2>DEBUGGING BLOG</h2>
<hr>
Debugging is typically defined as the process of identifying and correcting errors or bugs in a software's source code. Debugging ensures that your code runs properly without any mistakes. Different programming languages have various debugging methods due to the differences in the structure of the language models. Specifically, we will be going through the process of debugging in Python.

The debugging process in Python code consists of identifying, analyzing, and then resolving the errors in your code. This is a crucial part of being a programmer, making sure the quality and reliability of the code are accurate. There are various error types, such as Syntax Errors, Runtime Errors, and Logical Errors. Identifying the type of error could be confusing, but there are various things that you can look for in your code to identify the type of error. A syntax error is an error that results from violating Python's grammar rules, preventing code execution. On the other hand, Runtime errors are problems encountered during the program's execution, even with correct syntax. Lastly, Logical errors are the most challenging to identify; it's when the code runs without errors but produces incorrect or unexpected results. Then, after identifying the error, you have to analyze it to define what specific type of error it is. Once that is done, you can begin working toward a solution. 

<h3>Example #1: </h3>

```python
text = "Hello, world, my name is"
count = 0

for char in text:
    if char == "":
       count += 1

print(count)
```

Here we have an example of a code that is supposed to count how many spaces are in the given string, but it doesn't work because the condition inside the <strong> if statement </strong> is incorrect. In this case, the programmer wrote char == "", which checks for an empty string, not a space. Since none of the characters in the text are empty strings, the counter never increases. 

To fix the bug, you need to add a space character. That means adding a space inside the quotation marks. 

```python 
if char == " ":
    count += 1
```

<h3>Example #2: </h3>

```python
print("give me a number")
n = input()

for num in range(1, n):
    if num % 2 < 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```

This code is supposed to determine whether each number from the given set is odd or even, but it contains several errors. First, the input from the user is automatically read as a string, not a number. Because of this, the range 1 to n won't work at all. Another issue is that the condition num % 2 < 0 is incorrect; remainders from % 2 are never negative, so this line will never identify even numbers correctly. The loop also stops at n - 1, meaning it won't include the final number the user enters. 

To fix the code, you have to convert the input to an integer using int(), and add +1 to the range so it includes the number n, and lastly, use == 0 instead of < 0 so the code correctly checks if a number is even.

```python
print("give me a number")
n = int(input())

for num in range(1, n + 1):
    if num % 2 == 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```

<h3>Example #3: </h3>

```python
num = int(input("Enter an integer: "))

if num < -1:
  print("No negative numbers.")
else:
  result = 1
  for i in range(1, num):
    result *= i   

  print("Factorial of " + num + "is" + result)
```

This code is supposed to calculate the factorial of a given number, but it contains multiple errors. First, the condition num < -1 is incorrect because the code is meant to block all negative numbers, not just numbers less than –1. That means this condition won’t work properly. Another issue is that the loop runs from 1 to num, but it doesn't include the number the user entered, so the factorial will always be incomplete. Lastly, the line that prints the result uses "Factorial of" + num + "is" + result, which causes a syntax error because you can’t add strings and integers together.

To fix the code, you must first change the condition to < 0 so any negative number is blocked. Then, add +1 to the range so the loop includes the number the user typed in. Lastly, replace the + signs in the print statement with commas so Python doesn’t mix integers and strings incorrectly.

```python
num = int(input("Enter an integer: "))

if num < 0:
    print("No negative numbers.")
else:
    result = 1
    for i in range(1, num + 1):
        result *= i

    print("Factorial of", num, "is", result)
```

<h3>Example 4: </h3>

```python
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1

    if password == "incorrect_password":
        print("Correct password!")
    else:
        print("Incorrect password")

    if attempts > 3:
        print("Too many attempts")
        break
```

This code is supposed to ask the user to enter the correct password, but only allow them 3 attempts. However, it has multiple errors. First, the condition inside the if statement is completely wrong because it checks if the password is equal to "incorrect_password", and if it is, the program prints “Correct password!”. That is the opposite of what the code should do. Another problem is that the code continues running even if the user enters the correct password, which means there is no way to stop the program after success. The code also counts the attempts incorrectly because it stops only when the attempts are greater than 3, meaning it actually allows 4 attempts instead of 3.

To fix these issues, you must change "incorrect_password" to the actual correct password variable and add a break so the loop ends as soon as the right password is entered. You should also make sure the attempt counter only increases on incorrect attempts, or simply keep it as is, but fix the condition so the loop stops once attempts are >= 3. This lets the user try exactly three times.

```python
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    
    if password == correct_password:
        print("Correct password!")
        break
    else:
        print("Incorrect password")
        attempts += 1

    if attempts >= 3:
        print("Too many attempts")
        break
```
<h2>Conclusion:</h2>
<hr>
Debugging is an important part of learning how to code. By fixing errors in these examples, I learned how different mistakes can affect how a program works. I also learned that reading code carefully and testing my changes helps me understand the problem better. This experience will help me in the future because I now know how to find errors faster and make my code work the way I want.

