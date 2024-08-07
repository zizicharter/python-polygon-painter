# Python refresher

If you've already done some coding before this is a quick refresher on some ways that Python may be different. If you need some more detail, feel free to go back to the [introduction page](01-introduction.md).

## Whitespace

While some programming languages use brackets, Python uses indentation to indicate a block of code. For example, 

```
a = 1
b = 2
if a > b:
    print('a = ' + str(a))
    print("a is bigger than b")
else:
    print('b = ' + str(b))
    print("b is bigger than a")
```
This will print out

```
b = 2
b is bigger than a
```
because those print statement are indended under the else statement.


## If statements

In Python, there are no brackets around the condition of the if statement and else if are written using `elif`:

```
if a > b:
    print('a = ' + str(a))
    print("a is bigger than b")
elif a == b:
    print("a and b are equal")
else:
    print('b = ' + str(b))
    print("b is bigger than a")
```

## Comments

To write a comment in Python you need to start the line with a #

```
# This is a comment
```

Python does not support multi-line comments.

## Next

Next up: [Turtle](02-turtle.md)