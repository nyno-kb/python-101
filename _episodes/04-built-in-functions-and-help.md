---
title: "Built-in Functions and Help"
teaching: 20
exercises: 10
questions:
- "How can I use built-in functions?"
- "How can I find out what they do?"
- "What kind of errors can occur in programs?"
objectives:
- "Explain the purpose of functions."
- "Correctly call built-in Python functions."
- "Use help to display documentation for built-in functions."
- "Correctly describe situations in which SyntaxError and NameError occur."
keypoints:
- "Use comments to add documentation to programs."
- "A function may take zero or more arguments."
- "Commonly-used built-in functions include `max`, `min`, and `round`."
- "Functions may only work for certain (combinations of) arguments."
- "Functions may have default values for some arguments."
- "Use the built-in function `help` to get help for a function."
- "Every function returns something."
- "Python reports a syntax error when it can't understand the source of a program."
- "Python reports a runtime error when something goes wrong while a program is executing."
---
## Use comments to add documentation to programs

When coding, it is always a good idea to write comments explaining what the code does - and why.\
Comments will help other people understand what the program does.\
Just like we spoke about in regards to meaningful variable names, the most important “other person” is your future self!

~~~
# This sentence isn't executed by Python.
name = 'Python for Absolute Beginners'   # Neither is this comment - anything after '#' is ignored.
~~~
{: .python}

## A function may take zero or more arguments

We have seen some functions already (like `print()` and `type()`) --- now let's take a closer look.
*   An *argument* is a value passed into a function.
*   Any arguments you want to pass into a function must go into the `()`
    * `print("I am an argument and must go here.")`
*   You must always use parentheses, because this is how Python knows you are calling a function.
    * You leave them empty if you don't want or need to pass any arguments in.
*   `len` takes exactly one argument.
*   `int`, `str`, and `float` create a new value from an existing one.
*   `print` takes zero or more arguments.
    *   `print()` prints a blank line.

~~~
print('before')
print()
print('after')
~~~
{: .python}
~~~
before

after
~~~
{: .output}

## Commonly-used built-in functions include `max`, `min`, and `round`

*   Use `max` to find the largest value of one or more values.
*   Use `min` to find the smallest value of one or more values.
*   Both work on character strings as well as numbers.
    *   "Larger" and "smaller" use (0-9, A-Z, a-z) to compare letters.
    *   This means that:
        *   `'a'` is smaller than `'b'`
        *   `'A'` is smaller than `'a'`
        *   `'0'` is smaller than `'a'`
    *   This is useful for ordering alphabetically.

~~~
print(max(1, 2, 3))
print(min('a', 'b', 'c'))
print(min('a', 'A'))
~~~
{: .python}
~~~
3
a
A
~~~
{: .output}

<br/>
To see more built-in functions, visit the [Python Documentation](https://docs.python.org/3/library/functions.html)

## Functions may only work for certain (combinations of) arguments

*   `max` and `min` must be given at least one argument.
*   And they must be given things that can meaningfully be compared.

~~~
print(max(1, 'a'))
~~~
{: .python}
~~~
TypeError: '>' not supported between instances of 'str' and 'int'
~~~
{: .error}

<br/>
The error message tells us, that we cannot compare strings and integers.

## Functions may have default values for some arguments

*   `round` will round off a floating-point number.
*   By default, rounds to zero decimal places.

~~~
round(3.712)
~~~
{: .python}
~~~
4
~~~
{: .output}

*   We can specify the number of decimal places we want.

~~~
round(3.712, 1)
~~~
{: .python}
~~~
3.7
~~~
{: .output}

## Use the built-in function `help` to get help for a function

*   Every built-in function has online documentation.

~~~
help(round)
~~~
{: .python}
~~~
Help on built-in function round in module builtins:

round(...)
    round(number[, ndigits]) -> number

    Round a number to a given precision in decimal digits (default 0 digits).
    This returns an int when called with one argument, otherwise the
    same type as the number. ndigits may be negative.
~~~
{: .output}

## Python reports a syntax error when grammar rules (that's Python grammar, not English grammar) have been violated

You've seen errors when you try to use a function incorrectly, but you can also have errors when you use punctuation incorrectly.
*   Python will run the program up until that point, but if the grammar of that line
    of code has produced an error, then the program will shut down with an error.
*   Error messages will try and guide you to the point, where the error happened.
*   Python error messages may vary slightly depending on your Python environment.

~~~
# Forgot to close the quotation marks around the string.
name = 'Feng
~~~
{: .python}
~~~
    name = 'Feng
           ^
SyntaxError: unterminated string literal
~~~
{: .error}

~~~
# An extra '=' in the assignment.
age = = 52
~~~
{: .python}
~~~
    age = = 52
          ^
SyntaxError: invalid syntax
~~~
{: .error}

*   Look more closely at the error message:

~~~
print("hello world"
~~~
{: .python}
~~~
  Cell In[1], line 1
    print("hello world"
                       ^
SyntaxError: incomplete input
~~~
{: .error}

*   The message indicates a problem in cell number 1 on first line of the input ("line 1").
*   Next is the problematic line of code,
    indicating the problem with a `^` pointer.

## Python reports a runtime error when something goes wrong while a program is executing

In Python, a runtime error is an error that occurs while a Python program is running. These errors are also known as exceptions. 
Runtime errors in Python are typically caused by unexpected conditions or events that disrupt the normal flow of the program.\
They can happen for various reasons, for example:

~~~
age = 53
remaining = 100 - aege # mis-spelled 'age'
~~~
{: .python}
~~~
NameError: name 'aege' is not defined
~~~
{: .error}

*   Fix syntax errors by reading the source.
*   Fix runtime errors by tracing execution.

## Every function returns something

*   Every function call produces some result.
*   If the function doesn't have a useful result to return,
    it usually returns the special value `None`.

~~~
result = print('example')
print('result of print is', result)
~~~
{: .python}
~~~
example
result of print is None
~~~
{: .output}

Contrary to what we might expect, `print` does not return any value as such. I carries out the execution (i.e., it prints),
but after that nothing is returned. Thus, it has a return value of `None`.

## Exercises

> ## What Happens When
>
> 1. Explain in simple terms the order of operations in the following program:
>    when does the addition happen, when does the subtraction happen,
>    when is each function called, etc.
> 2. What is the final value of `word`?
>
> ~~~
> word = 'blah '
> word = max(min(word * 2 + 'blur ', 'aaah '), 'ping')
> print(word)
> ~~~
> {: .python}
>
> > ## Solution
> >
> > ~~~
> > ping
> > ~~~
> > {: .output}
> >
> > 1. **Initialization**: `word` is assigned the initial value 'blah '.
> > 2. **Inside `max()` function**:
> >    - `word * 2` results in 'blah blah '. (Repeats the string 'blah ' twice using `*`.)
> >    - 'blah blah ' + 'blur ' results in 'blah blah blur '. (Concatenates the two strings using `+`.)
> >    - 'aaah ' is compared with 'blah blah blur '. The `min()` function returns the smaller of the two strings, which is 'aaah '.
> > 3. **Outer `max()` function**:
> >    - The result of the `min()` function ('aaah ') is passed as an argument.
> >    - The `max()` function then compares 'aaah ' with 'ping' and returns the larger of the two strings, which is 'ping'.
> > 4. **Assignment**: Finally, the value 'ping' is assigned to the variable `word`.
> > 5. **Output**: The program prints the value of `word`, which is 'ping'.
> >
> {: .solution}
{: .challenge}


> ## Spot the Difference
>
> 1. Predict what each of the `print` statements in the program below will print.
> 2. Does `max(len(rich), poor)` run or produce an error message?
>    If it runs, does its result make sense to you? (Remember that we are comparing the _value_ of the variable and not the _name_ of the variable.)
>
> ~~~
> rich = "gold"
> poor = "tin"
> print(max(rich, poor))
> print(max(len(rich), len(poor)))
> ~~~
> {: .python}
>
> > ## Solution
> >
> > ~~~
> > tin
> > 4
> > ~~~
> > {: .output}
>{: .solution}
{: .challenge}

> ## Why Not?
>
> Why don't `max` and `min` return `None` when they are given no arguments?
> > ## Solution
> >
> > Both functions require at least one argument to execute.
> > ~~~
> > print(max())
> > ~~~
> > {: .python}
> > ~~~
> > TypeError: max expected at least 1 argument, got 0
> > ~~~
> > {: .error}
>{: .solution}
{: .challenge}

> ## Last Character of a String
>
> If Python starts counting from zero,
> and `len` returns the number of characters in a string,
> what index expression will get the last character in the string `name`?
> (Note: we will see a simpler way to do this in a later episode.)
>
> > ## Solution
> >
> > `name[len(name) - 1]`
> {: .solution}
{: .challenge}
