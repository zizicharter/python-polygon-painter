# Introduction

This is a course that teaches some Python and the Turtle library with the aim to create beautiful polygon pictures using programming!

## Getting started

A popular way to start coding is to write a 'Hello World' script so that is where we will start!

Create a new file called `Script.py` and on the first line type:
```
print("Hello world!")
```
Anything inside the brackets of a `print` statement will get outputted to the terminal when the script is run.

To run the script type `python Script.py` in the terminal. You should see `Hello world!`.

> 💡 Exercise: Try adding a new `print` statement that will display your name in the terminal.

## Variables

Variables are a way of giving a name to something you want to use later. For example, try typing:
```
message = "Hello world!"
print(message)
```
When you run the script, this should output `Hello world!` as before. This is because you have created a variable called `message` and now whenever the code sees that variable it knows you mean `"Hello world!"`.

> 💡 Exercise: Try changing the text of the message variable and see how that changes what is output to the terminal when you run the script.

### Types

In Python, when somethings has `""` or `''` around it, we called it a `string`. This is called its type. However, variables do not have to just be a `string`. They can be any [type that Python supports](https://www.w3schools.com/python/python_datatypes.asp). 

For example, you can create a variable that holds a number:
```
x = 7
print(x)
```
This should print `7` to the terminal when you run the script.

### Variable addition 

You can also add variables of the same type together:
```
x = 6
y = 8
z = x + y
```
This will assign the variable `z` the value `14`.
```
greeting = "Hello"
name = "Rosie"
message = greeting + name
```
The code above will assign the variable `message` the value  `HelloRosie`. Notice there is no space between `Hello` and `Rosie`. This is because when 'adding' strings together, Python will put the second string straight on the end of the first one. If we wanted a space we could:
1. have a space on the end of the greeting string `greeting = "Hello "`
2. have a space at the start of the name string `name = " Rosie"`
3. add a space in when constructing the message variable `message = greeting + " " + name`

### Adding different types

Try adding the following lines to your script:
```
message_prefix = "My favourite number is"
fav_num = 2
message = message_prefix + " " + fav_num
print(message)
```
This will produce an error message in the terminal because we have tried to add a number to a string which Python does not know how to do as they are different 'types'. If we wanted to print out the message containing the string and the favourite number we can change the line to:
```
message = message_prefix + " " + str(fav_num)
```
Anything inside the brackets after `str`, Python will convert to a string so it can happily add it to another string.

## Mathematical operations

You can use Python a bit like a calculator. It supports the normal mathematical operators: addition `+`, substraction `-`, multiplication `*` and division `/`.

```
a = 3 + 4   # same as a = 7 
b = 10 - 7  # same as b = 3
c = 5 * 4   # same as c = 20
d = 30 / 3  # same as d = 10
```
<details> <summary> <b> Advanced mathematical operations </b> </summary>

Python can also do some more advanced operators: modulo `%`, floor division `//` and `**` exponentiation.

### Modulo

Modulo returns the remainder, the leftover number when you divide the number in front of the `%` by the number after it.

```
x = 10 % 3 # same as x = 1
```

### Floor division

Floor division divides the first number by the second number and then rounds the result down to the nearest whole number.

```
x = 10 // 3 # same as x = 3
```

### Exponetiation

Exponentiations takes the first number and raises it to the power of the second number.

```
x = 10 ** 3 # same as x = 1000
```

</details>


## Loops
Say we wanted to write some code that outputted the numbers 0 to 99. We could write out 100 `print` statements with each of the numbers in but this is quite a lot of lines. 

With Python we can use loops to run a block of code a specified number of times. So to output the numbers 0 to 99 we can write:
```
for x in range(100):
    print(x)
```
A `for` loop will repeat the block of code indented under it as many times as specified by `range`. Notice how we use `range(100)`. This is because `range(100)` is the values 0 to 99. If we wanted to start from a number other than 0 we can type `range(5, 100)`. This is the numbers 5 to 99. There are [other ways for writing loops in Python](https://www.w3schools.com/python/python_for_loops.asp).

## If statements
An `if` statement allow us to specify when a block of code should be run based on a condition. 

For example, say we wanted to print out to the terminal if one number was bigger than another:
```
a = 27
b = 13
if a > b:
    print("a is bigger than b")
```
With the these values of `a` and `b`, `a is bigger than b` would be printed out to the terminal when the script ran. However, if we changed the code the first line to...
```
a = 7
```
...then nothing would be printed out as 7 is not bigger than 13.

We can add a second condition for the code to try in the case of the first one not being true. We use `elif` to specify the second condition which is the way Python shortens 'else if':

```
a = 7
b = 7
if a > b:
    print("a is bigger than b")
elif a == b:
    print("a is equal to b")
```
Because `a` is not stictly bigger than `b`, the first condition isn't true so Python checks the next condition. With these values of `a` and `b`, `a is equal to b` would be printed out to the terminal.

We can also have `else` statements. This tells the code what to do if none of the conditions are true. 
```
a = 7
b = 13
if a > b:
    print("a is bigger than b")
elif a == b:
    print("a is equal to b")
else:
    print("a is smaller than b")
```
In this case, `a is smaller than b` would be printed to the terminal as none of the conditions were true.

> 💡 Exercise: Try writing some code that will output if a variable is bigger, smaller or equal to the number 10.

## Functions

Functions allow us to write blocks of code that we can 'call' at another point. This allows us to repeat certain blocks of code multiple times without having to write the same code every time. We write functions like this:

```
def my_function_name():
    print("This is in a function")
```
This code on its own will not print anything to the terminal because the function has not been 'called'. We have to 'call' it by writing the function name with brackets like this:
```
my_function_name()
```
We can give a function some information that it can use when it is called. This is called a function argument. For example, we can add the `name` argument to the function we created earlier:
```
def my_function_name(name):
    print("Hello " + name)
```
This function will, when called, print `Hello` and then the name given to the function. For example `my_function_name("Rosie")` will print `Hello Rosie` to the terminal and `my_function_name("James")` will print `Hello James`. We call the information we give to the function arguments.

> 💡 Exercise: Try creating a function that takes one number argument and prints out if it is bigger, smaller or the same as the number 10 (look at the section on `if` statements if you need help with this)


## User input

Python allows us to get input from the user. We do this by using the `input()` function. For example:
```
name = input("Enter your name:")
```
When Python sees an `input()` it will print what is inside the brackets to the terminal, pause the script and wait for the user to type something and press enter. Once the user has done this, the script will continue to run.

You can use what the user has typed like a normal variable:
```
print("The name you entered was " + name)
```
This will print `The name you entered was ` and then whatever the user typed. For example if the user typed `Rosie` it will print `The name you entered was Rosie`. 

As it is a normal variable we can use it as an argument to a function. For example...

```
def my_function_name(name):
    print("Hello " + name)

input_name = input("Enter your name:")
my_function_name(input_name)
```
...will output `Hello` and the users name.

> 💡 Exercise: Try adding an input to your script that asks for a number and uses your function from the functions section to decide if it is bigger, smaller or the same as the number 10.

## Random

Python has a feature that allows us to generate (pseudo-)random numbers. In order to do this we need to tell it we want to use the set of functions that create these numbers. To do this add this line to the top of your script:
```
import random
```

### Produce random number

We can produce a random number with a range (between two numbers) by using `randrange`:

```
x = random.randrange(1, 10) # Produces a random number between 1 and 10
```

> 💡 Exercise: Try creating a random number between 0 and 100 and print it to the terminal. Notice each time you run the script it produces a different number!

### Seed

A computer can't produce truly random numbers and uses an algorithm to generate the numbers. You can control what random numbers are generated with the `seed` function:

```
random.seed(2) # Initialize the random number generator with the seed '2'
```

> 💡 Exercise: Now try running your script lots of times and see how that changes what numbers it produces.

## Next

Next up: [Turtle](02-turtle.md)