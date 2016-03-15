# Getting Started with Python

Python is a popular general purpose programming language that's great for beginners, but it's also used by professionals. It's designed to be easy to read and easy to write, and there are plenty of additional modules. Python can be used to create games, desktop applications and websites, and for controlling physical hardware, robotics and more.

## IDLE and the Python Shell

IDLE is the name of the Python IDE (Integrated Development Environment) that comes with Raspbian.

1. Open Python 3 from the applications menu:

    ![Open Python 3](images/open-python3.png)

    You'll see the IDLE window open up. This window is a Python shell, which will allow you to enter Python commands directly and they will be executed immediately.

1. Enter the following command and press `Enter`:

    ```python
    print("Hello world")
    ```

    *Be careful to enter the brackets `(` and `)` and quotes `"` correctly.*

    You should see the words `Hello world` on the next line. The word `print` means "write to the screen".

1. Now enter the following line:

    ```python
    >>> message = "Hello"
    ```

1. And try:

    ```python
    >>> print(message)
    ```

    This should print out your message, `Hello`.

1. Now enter this line with your own name:

    ```python
    >>> name = "Alex"
    ```

1. And try:

    ```python
    >>> print(message, name)
    ```

    You should see the greeting `Hello Alex` printed out (with your own name).

## Variables and types

So far you've interacted with the Python shell by printing some text. Now you'll look at how variables can be used to store different types of data.

1. Previously you created a variable called `message` which contained the value `Hello`. Enter the following into the shell:

    ```python
    >>> type(message)
    ```

    You'll see `<class 'str'>` printed out. This indicates that the variable `message` is of type **string**.

    *String is the name for data in the form of text. Python interpreted the type by your use of quotation marks.*

1. Try assigning a new variable to a number:

    ```python
    >>> a = 1
    ```

1. Now inspect the type of this new variable:

    ```python
    >>> type(a)
    ```

    You'll see `<class 'int'>`. This means it's an integer (a whole number).

1. What if you entered a number which isn't an integer, say `1.5`? Try it:

    ```python
    >>> b = 1.5
    >>> type(b)
    ```

    You'll see `<class 'float'>`. This means it's a floating point number (a decimal).

1. What if you entered a number in quotation marks? Try it:

    ```python
    >>> c = "2"
    >>> type(c)
    ```

    You'll see `<class 'string'>`.

1. What if you assign `c` to something else? Try this:

    ```python
    >>> c = 3
    >>> type(c)
    ```

    You should now see `<class 'int'>`. You've changed `c` from being the string value `2` to the integer value `3`. Python allowed you to change both the value and the type of the variable.

    *Some programming languages require you to indicate the data type when you create a new variable. Python interprets the data type by its context - quotes, number, decimal point, etc.*

## Adding

Python permits use of the `+` operator to add values together. Let's experiment with it.

1. You previously created variables `a`, `b` and `c` which are all numbers. Try adding any of them together:

    ```python
    >>> a + b
    2.5
    >>> b + c
    4.5
    >>> a + c
    4
    ```

    You'll find you can add together integers and floats.

1. Try making a new variable from the sum of two others:

    ```python
    d = a + c
    e = b + c
    ```

1. Now inspect the type of `d` and `e`:

    ```python
    >>> type(d)
    <class 'int'>
    >>> type(e)
    <class 'float'>
    ```

    You'll find that the sum of two integers makes an integer, and the sum of an integer and a float makes a float (even if it's actually a whole number).

1. What happens when you add two strings together? Try:

    ```python
    >>> greeting = message + name
    'HelloAlex'
    ```

    Adding two strings together makes a longer string. This is called *string concatenation*. Note that no space was added, the words were joined directly.

1. Try adding a space:

    ```python
    >>> greeting = message + " " + name
    'Hello Alex'
    ```

1. What happens if you add a string to an integer?

    ```python
    >>> message + a
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: Can't convert 'int' object to str implicitly
    ```

    An error! Python complains it can't add a string to an integer.

1. In order to do this, you would have to convert the integer to a string:

    ```python
    >>> message + str(a)
    'Hello1'
    ```

1. What happens if you add two number strings together?

    ```python
    >>> 2 + 2
    4
    >>> "2" + "2"
    "22"
    ```

    Here you can see adding two integers together adds the numbers together, but adding the strings together concatenates the two strings to give a different result.

1. Try multiplying:

    ```python
    >>> c * 10
    30
    >>> message * 2
    'HelloHello'
    ```

## Booleans and If/Else

So far you've used `=` to assign values to variables. Now you'll use `==` to check equality, and learn to use `if` and `else` to control flow with logic.

1. What happens when you compare two variables with `==`? Try:

    ```python
    >>> a == 1
    True
    >>> a == 2
    False
    ```

1. Now try assigning a new variable to the output of one of these, and inspect its type:

    ```python
    >>> f = a == 1
    >>> type(f)
    <class 'bool'>
    ```

    You'll see this is a *boolean*. A Boolean is a True/False data type.

1. Booleans are useful for doing different things in different circumstances. Try using the following `if` statement:

    ```python
    >>> if a == 1:
    ...     print("Hello")
    ...
    Hello
    ```

    *You'll notice that pressing `Enter` after a colon (`:`), the next line will be automatically indented. Indentation is important in Python.*

1. You can use `else` to determine what happens when the condition is not met:

    ```python
    >>> if a == 2:
    ...     print("Hello")
    ... else:
    ...     print("Goodbye")
    ...
    Goodbye
    ```

    *Note that the `else` line is unindented to the same level as the `if` line. Press `Backspace` to unindent at this point.*

1. You can also use `and` and `or` to use multiple conditionals:

    ```python
    >>> if a == 1 and b == 2:
    ...     print("Hello")
    ... else:
    ...     print("Goodbye")
    ...
    Goodbye
    ```

    or:

    ```python
    >>> if a == 1 or b == 2:
    ...     print("Hello")
    ... else:
    ...     print("Goodbye")
    ...
    Hello
    ```

1. Or you can use nested `if` statements:

    ```python
    >>> if a == 1:
    ...     if b == 2:
    ...         print("A")
    ...    else:
    ...         print("B")
    ... else:
    ...     if b == 2:
    ...         print("C")
    ...    else:
    ...         print("D")
    ...
    B
    ```

1. You can also use `>` (greater than) and `<` (less than) to compare values:

    ```python
    >>> if a > 1:
    ...     print("Hello")
    ...
    ```

1. Or use `>=` (greater than or equal to) and `<=` (less than or equal to):

    ```python
    >>> if a >= 1:
    ...     print("Hello")
    ...
    Hello
    ```

## Lists, loops and dictionaries

As well as storing single values, you can use **lists** to store multiple values.

1. Create a list:

    ```python
    >>> names = ["Alice", "Bob", "Charlie"]
    ```

1. Inspect the size of the list with `len`:

    ```python
    >>> len(names)
    3
    ```

1. Access individual list items by their index number:

    ```python
    >>> names[0]
    Alice
    >>> names[1]
    Bob
    >>> names[2]
    Charlie
    ```

    *Note that list index numbers start at 0 and end at one less than the list length*

1. You can iterate over a list of items with a `for` loop:

    ```python
    >>> for name in names:
    ...     print(name)
    Alice
    Bob
    Charlie
    ```

    *Note that the plural word `names` was chosen for the list, and the singular `name` for each individual name. Variables can be called anything, but sensible names like this help make code readable.*

1. Try creating a second list and adding it to the first:

    ```python
    >>> more_names = ["Daniel", "Eve", "Fred"]
    >>> all_names = names + more_names
    >>> all_names
    ["Alice", "Bob", "Charlie", "Daniel", "Eve", "Fred"]
    ```

    *Adding two lists together makes a new list with the items from the first list followed by the items from the second.*

1. Another way of achieving this is to use `extend` to add the items from the second list to the end of the first list in its original place:

    ```python
    >>> names.extend(more_names)
    >>> names
    ["Alice", "Bob", "Charlie", "Daniel", "Eve", "Fred"]
    ```

1. To add an individual item to a list, you can use `append`:

    ```python
    >>> names.append("Grace")
    >>> names
    ["Alice", "Bob", "Charlie", "Daniel", "Eve", "Fred", "Grace"]
    ```

1. Another data structure for storing multiple values is a **dictionary**. A dictionary is a relational mapping between pairs of values. Try creating a simple dictionary:

    ```python
    >>> people = {"Alice": 14, "Bob": 15}
    ```

1. Dictionaries are key-value pairs. You can look up a key's corresponding value:

    ```python
    >>> people["Alice"]
    14
    >>> people["Bob"]
    15
    ```

1. You can iterate over dictionary items with a `for` loop:

    ```python
    >>> for name, age in people.items():
    ...     print(name + " is " + str(age) + " years old")
    ...
    Alice is 14 years old
    Bob is 15 years old
    ```

1. You can add items to the dictionary:


    ```python
    >>> people["Charlie"] = 16
    >>> people["Daniel"] = 18
    ```

1. Try adding an `if` statement inside this `for` loop to show different messages according to each person's age:

    ```python
    >>> for name, age in people.items():
    ...     if age >= 18:
    ...         print(name + " is an adult")
    ...     else:
    ...         print(name + " is a child")
    ...
    Alice is a child
    Bob is a child
    Charlie is a child
    Daniel is an adult
    ```

## While loops and user input



## Creating a Python file

So far, all you've used is the IDLE shell, which is great for experimenting with, but it's useful to save all your commands in a file so you can execute them all in one go.

1. Go to `File > New window` in the IDLE menu bar. This will open a blank window alongside your IDLE shell.

1. Start by saving the new file (`File > Save`) and save as `hello.py`.

1. Enter the following lines into your new file:

    ```python

    ```

## What next?

Now you've got to grips with the basics of Python, try some more starter activities:

- [Turtle Snowflakes](https://www.raspberrypi.org/learning/turtle-snowflakes/)
- [Storytime](https://www.raspberrypi.org/learning/storytime/)

Why not try some physical computing with add-on boards or components?

- [Getting Started with GPIO Zero](https://www.raspberrypi.org/learning/getting-started-with-gpio-zero/)
- [Getting Started with Picamera](https://www.raspberrypi.org/learning/getting-started-with-picamera/)
- [Getting Started with the Sense HAT](https://www.raspberrypi.org/learning/getting-started-with-the-sense-hat/)

Or use Python code to explore the Minecraft world:

- [Getting Started with Minecraft Pi](https://www.raspberrypi.org/learning/getting-started-with-minecraft-pi/)
