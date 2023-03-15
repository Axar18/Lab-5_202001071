# Lab-5_202001071
IT314 - Software Engineering
Lab 5 - Static Analysis

Date- 15-3-23
ID-202001071
Name- Akshar Chaudhari


Static Analysis:

git repository: https://github.com/jassics/learning-python.git

Language: Python

Tool:mypy/mypy Playground 


1)
Code:

#!/usr/bin/python3
""" First Python Program
    Just to see if we can run python3 successfully
"""

name = Sanjeev
print("hello "+name+"\n")



Errors: main.py:6: error: Name "Sanjeev" is not defined  [name-defined]

In this sample code defined name must be in “”. If not it can't be defined as the given  name.  

![image](https://user-images.githubusercontent.com/123543030/225281983-763bf68a-f3f7-404a-9f7d-2f7840d25ba5.png)

2)

Code:


#!/usr/bin/python
positive_int = 55

negative_float = -2.9987654

complex_num = 1j

positive_float = float(positive_int)  

negative_int = int(negative_float)  

complex_from_int = complex(positive_int)  

print{positive_float}
print(negative_int) 
print(complex_from_int)  

print(type(positive_float)) 
print(type(negative_int)) 
print(type(complex_from_int))




Error: main.py:23: error: Missing parentheses in call to 'print'. Did you mean print(...)?  [syntax]

Tool detected Highlighted red line has a syntax error. Also the tool gives suggestions for correct syntax. Parentheses print should be print(..), that the correct syntax for it.

![image](https://user-images.githubusercontent.com/123543030/225282287-bc950230-45db-4912-a475-5b4df80e5e69.png)

3)

Code:

#!/usr/bin/python
import random



guess_num_range = 20A
num_to_be_guessed = int(guess_num_range * random.random()) + 1
guess == 0

while guess != num_to_be_guessed:
    guess = int(input("Guess the number: "))
    if guess > 0:
        if guess > num_to_be_guessed:
            print("Number is too large")
        elif guess < num_to_be_guessed:
            print("Number is too small")
    else
        print(Sorry that you're giving up!)
        break
else:
    print("Congratulation. You made it!")



Error:

main.py:13: error: invalid decimal literal  [syntax]


main.py:25: error: unterminated string literal (detected at line 25)  [syntax]



Integer and alphabet can’t be together with what the first error says. In the second error print text unterminated.

Observation : Currently in this particular code there are 2 mistakes but mypy can saw only 1 bug at a time.

![image](https://user-images.githubusercontent.com/123543030/225282547-979613f5-90c4-480b-a1f5-24dbd814c915.png)


4)

Code:

#!/usr/bin/python

'''def function_name():
    {
        # some code here
    }
'''

def add_numbers(num1, num2)
    return num1+num2


print(add_numbers(5,4))

def  is_even(num):
    if num%2 == 0:
         True
    return False

num = 12
result = is_even(num)
if result:
    print(f'{num} is even')
else:
    print(f'{num} is not even')
    
    

Error:


main.py:20: error: expected ':'  [syntax]

Tool detected the error but didn't give a specification about the error!


![image](https://user-images.githubusercontent.com/123543030/225281500-5eccbdab-2ad5-4ee2-b5ea-d72f268b9c82.png)
