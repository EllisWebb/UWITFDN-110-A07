# Pickling Errors Using Python
*Carter Webb 06.01.2023*

## Introduction
In this lesson we will be focusing on exploring the use of Structured Error Messages to improve user performance with our software; as well as introduce the use of binary files through a Python library called Pickle.

Structured Error Handling can give a programmer a better way to understand and work with the user experience by formulating common errors in more broadly digestibly terminology. This type of error handling is most often seen in only Object Oriented Programming languages as the errors themselves are assigned to specific object class’s and, thus, is object oriented by its very nature. 

On the other hand, the use of binary files in python by way of the Pickle library can allow for the programmer to obscure sensitive information that may be stored or saved by their software code. 

Together, structuring the user’s interactivity by “Pickling Errors” (this is not a real term, simply a catchy handle mad up for the purposes of this assignment) is one way to show the user what is expected of them by the program while also removing any bias that could come from the user accessing previous answers. 

## Programing – Shaping the User’s Experience
First let’s define both Error Handling and the use of Binary Files, mediated by the Pickle Library
### Structured Error Handling
In order to start, we must first define some important nomenclature:

	•Object Oriented Programming
	-A programming paradigm whose crux is defining meaning based on the unique attributes and behaviors of a 
	given or created data field. 
	
	•Exception(s)
	-Conditions, or parts of code, that break the normal flow or executions of the given program. 
	-Thus, these conditions can be said “to be handled with an exception parameter”. 

Structured Error Handline is a practice by which a programmer can better communicate Hardware Exceptions (division by zero) and Software Exceptions (unknown file extension, use .txt). Through strategic planning, a programmer can predict user errors and their corresponding object-oriented Software or Hardware Exceptions. One can then “catch” these errors through the use of a Try-Except Block, a conditional statement that will perform an action, store the data from the action, and then return any exceptions it encountered along the way. 

You can imagine this already to be an improvement on Python base exceptions/error messages. The later fails to store any information from the action that “broke the flow of normal processing”, while, the Try-Except Block can.  
```
try: # the code or function specified first
    quotient = 5/0 # still saves/initializes the variable quotient despite its assignment dividing by 0!
    
except ZeroDivisionError as e: # when this exception is encountered, print this message, with this structure
    print("Please do not use Zero for the second number!")
    print("Built-In Python error info: ")
    print(e, e.__doc__, type(e), sep='\n')
```
The above depicts the use of a Try-Except Block used to “catch” a 0 division error (Hardware Exception) Root - IT FDN 110 A - 2023

The Try-Except Block can be used to “catch” a wide variety of exceptions, some of which we have already mentioned. A common example is that of filtering what and how files can be saved. If your program is meant to run only .txt files a Software Exception will likely pop up if a previous user was allowed to save their data as a .csv file. Thus, a Try-Except Block can be used to avoid such an error by only allowing the saving of .txt files by “catching” when the user saves as .csv.

### Binary Files and the Pickle Library
Binary Files are characterized by a general inaccessibility to the human eye, or rather Binary Files are written in a language other than that of humans. Such a file can be in Binary 1 and 0’s or in another symbolic language produced by the computer. This goes to say, that the computer can always understand Binary Files and therefore can be extremely useful in a user-data interface. 

Through Binary Files, a programmer can immediately obscure the data to themselves and the user, effectively applying a level of objectivity to any data saved within this file type. This file type is known as .dat and different in nature from .txt and .csv files. 
```
import pickle  # This imports code from another code file!

intId = int(input("Enter an Id: "))
strName = str(input("Enter a Name: "))
lstCustomer = [intId, strName]
print(lstCustomer)

#Now we store the data with the pickle.dump method
objFile = open("AppData.dat", "ab")
pickle.dump(lstCustomer, objFile)
objFile.close()
```
The above depicts the import and use of the Pickle Library and How To Save User Data using the pickle. Dump command
Root - IT FDN 110 A - 2023

## Demo
Now let’s combine the two to create a layer of code that asks for the user to save some input, however, only as a Binary or .dat file!

![Pickled Errors Demo](web address "Pickled Errors Demo")![image](https://github.com/EllisWebb/UWITFDN-110-A07/blob/111732e405b0038edab1eb6229370b60dd485c21/Screen%20Shot%202023-06-01%20at%209.43.55%20AM.png)


The above depicts the use of a Try-Except Block used to “catch” file naming errors (Software Exception) 
## Conclusion 
In conclusion, Python provides a wide range of user interface and user direction tools whether it be from Python’s base code or from a simple import from the base library. With these tools the programmer can make future use of the software more streamline and even prevent crashes by limiting how the user can interact (save files) with the code. Furthermore, we can also make the users experience better using custom errors that can allow for greater flexibility and digestibly or error messages and code breaking.

## Sources
### Structured Error Handling
https://docs.progress.com/bundle/openedge-abl-error-handling-117/page/What-is-structured-error-handling.html#:~:text=Structured%20error%20handling%20is%20an,your%20own%20error%20types%20(classes)

https://learn.microsoft.com/en-us/windows/win32/debug/structured-exception-handling 

https://www.techtarget.com/searchapparchitecture/definition/object-oriented-programming-OOP?Offer=abMeterCharCount_var1
### Binary Files/Pickle
https://www.futurelearn.com/info/courses/programming-103-data/0/steps/64743

https://docs.python.org/3/library/pickle.html
### Class Materials 
Randall Root - IT FDN 110 A – 2023 Assignment 7 Python Programming Notes

