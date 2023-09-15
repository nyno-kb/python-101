---
title: "Conditionals"
teaching: 15
exercises: 15
questions:
- "How can programs do different things for different data?"
objectives:
- "Correctly write programs that use if and else statements and simple Boolean expressions (without logical operators)."
- "Trace the execution of unnested conditionals and conditionals inside loops."
keypoints:
- "Use `if` statements to control whether or not a block of code is executed."
- "Conditionals are often used inside loops."
- "Use `else` to execute a block of code when an `if` condition is *not* true."
- "Use `elif` to specify additional tests."
- "Conditions are tested once, in order."
- "Create a table showing variables' values to trace a program's execution."
---
## Use `if` statements to control whether or not a block of code is executed

*   An `if` statement (more properly called a *conditional* statement)
    controls whether some block of code is executed or not.
*   The structure is similar to a `for` statement:
    *   First line opens with `if` and ends with a colon.
    *   Body containing one or more statements is indented (usually by 4 spaces or tab).

~~~
mass = 3.54
if mass > 3.0:
    print(mass, 'is larger than 3.0')

mass = 2.07
if mass > 3.0:
    print (mass, 'is larger than 3.0')
~~~
{: .python}
~~~
3.54 is larger than 3.0
~~~
{: .output}

## Conditionals are often used inside loops

*   There is not much point in using a conditional when we know the value (as above).
*   But it is useful when we have a collection to process.

~~~
masses = [3.54, 2.07, 9.22, 1.86, 1.71]
for m in masses:
    if m > 3.0:
        print(m, 'is larger than 3.0')
~~~
{: .python}
~~~
3.54 is larger than 3.0
9.22 is larger than 3.0
~~~
{: .output}

## Use `else` to execute a block of code when an `if` condition is *not* true

*   `else` can be used following an `if`.
*   It allows us to specify an alternative to execute when the `if` *branch* isn't taken.

~~~
masses = [3.54, 2.07, 9.22, 1.86, 1.71]
for mass in masses:
    if mass > 3.0:
        print(mass, 'is larger than 3.0')
    else:
        print(mass, 'is smaller than 3.0')
~~~
{: .python}
~~~
3.54 is larger than 3.0
2.07 is smaller than 3.0
9.22 is larger than 3.0
1.86 is smaller than 3.0
1.71 is smaller than 3.0
~~~
{: .output}

## Use `elif` to specify additional tests

*   You may want to provide several alternative choices, each with its own test.
*   Use `elif` (short for "else if") and a condition to specify these.
*   Must always be associated with an `if`.
*   Must come before the `else` (which is the "catch all").
*   `elif` - like `else` - is **only** executed if the `if` condition is not.

~~~
masses = [3.54, 2.07, 9.22, 1.86, 1.71]
for mass in masses:
    if mass > 9.0:
        print(mass, 'is HUGE')
    elif mass > 3.0:
        print(mass, 'is larger')
    else:
        print(mass, 'is smaller')
~~~
{: .python}
~~~
3.54 is larger
2.07 is smaller
9.22 is HUGE
1.86 is smaller
1.71 is smaller
~~~
{: .output}

## Conditions are tested once, in order

*   Python steps through the branches of the conditional in order, testing each in turn.
*   ***But*** if one conditional is fulfilled, Python will "step out of" the statement and *not* test the following conditionals.
*   So ordering matters!
*   Take a look at this script:

~~~
points = 85
if points >= 70:
    print('grade is C')
elif points >= 80:
    print('grade is B')
elif points >= 90:
    print('grade is A')
~~~
{: .python}
~~~
grade is C
~~~
{: .output}

*   What is the problem with the script above?
*   The problem is that a grade can never be higher than 'C', since any `points` above 70 will be "caught" by the `if` condition. Thus, the `elif` conditions will never be tested.
*   A better way to write the above script, would be:

~~~
points = 85
if points >= 90:
    print('grade is A')
elif points >= 80:
    print('grade is B')
elif points >= 70:
    print('grade is C')
~~~
{: .python}
~~~
grade is B
~~~
{: .output}

<br/>
*   Remember that Python scripts are run "chronologically", i.e., from the top down.
*   This means, that a script will *not* automatically go back and re-evaluate if values change.

~~~
speed = 10.0
if speed > 20.0:
    print('moving too fast')
else:
    print('adjusting speed')
    speed = 50.0
~~~
{: .python}
~~~
adjusting speed
~~~
{: .output}

*   Often conditionals are used in a loop to "evolve" the values of variables.

~~~
speed = 10.0
for i in range(5): # execute the loop 5 times
    print(i, ':', speed)
    if speed > 20.0:
        print('moving too fast')
        speed = speed - 5.0
    else:
        print('moving too slow')
        speed = speed + 10.0
print('final speed:', speed)
~~~
{: .python}
~~~
0 : 10.0
moving too slow
1 : 20.0
moving too slow
2 : 30.0
moving too fast
3 : 25.0
moving too fast
4 : 20.0
moving too slow
final speed: 30.0
~~~
{: .output}
<br/>

> ## Compound statements; using `and`, `or`, and parentheses
>
> * Often, you want some combination of things to be true.
> * You can combine relations within a conditional using `and` and/or `or`. 
> * This is called [compound statements](https://docs.python.org/3/reference/compound_stmts.html).
> * Continuing the example above, suppose you have:
>
> ~~~
> mass     = [ 3.54,  2.07,  9.22,  1.86,  1.71]
> speed = [10.00, 20.00, 30.00, 25.00, 20.00]
>
> for i in range(5):
>     if mass[i] > 5 and speed[i] > 20:
>         print("Fast heavy object. Duck!")
>     elif mass[i] > 2 and mass[i] <= 5 and speed[i] <= 20:
>         print("Normal traffic")
>     elif mass[i] <= 2 and speed[i] <= 20:
>         print("Slow light object. Ignore it.")
>     else:
>         print("Whoa! Something is up with the data. Check it.")
> ~~~
> {: .python}
>
> Just like with arithmetic, you can and should use parentheses whenever there is possible ambiguity.\
> A good general rule is to *always* use parentheses when mixing `and` and `or` in the same condition.  That is, instead of:
>
> ~~~
> if mass[i] <= 2 or mass[i] >= 5 and speed[i] > 20:
> ~~~
> {: .python}
>
> write one of these:
>
> ~~~
> if (mass[i] <= 2 or mass[i] >= 5) and speed[i] > 20:
> if mass[i] <= 2 or (mass[i] >= 5 and speed[i] > 20):
> ~~~
> {: .python}
>
> so it is perfectly clear to a reader (and to Python) what you really mean.
{: .callout}

> ## Tracing Execution
>
> What does this program print?
> 
> ~~~
> pressure = 71.9
> if pressure > 50.0:
>     pressure = 25.0
> elif pressure <= 50.0:
>     pressure = 0.0
> print(pressure)
> ~~~
> {: python}
> >
> > ## Solution
> > ~~~
> > 25.0
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Trimming Values
>
> Fill in the blanks so that this program creates a new list
> containing zeroes where the original list's values were negative
> and ones where the original list's values were positive.
>
> ~~~
> original = [-1.5, 0.2, 0.4, 0.0, -1.3, 0.4]
> result = ____
> for value in original:
>     if ____:
>         result.append(0)
>     else:
>         ____
> print(result)
> ~~~
> {: .python}
>
> ~~~
> [0, 1, 1, 1, 0, 1]
> ~~~
> {: .output}
> > ## Solution
> > ~~~
> > original = [-1.5, 0.2, 0.4, 0.0, -1.3, 0.4]
> > result = []
> > for value in original:
> >    if value < 0:
> >        result.append(0)
> >    else:
> >       result.append(1)
> > print(result)
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

> ## Processing Small Files
>
> Modify this program so that it only processes files with fewer than 50 records.
>
> ~~~
> import glob
> import pandas
> for filename in glob.glob('data/*.csv'):
>     contents = pandas.read_csv(filename)
>     ____:
>         print(filename, len(contents))
> ~~~
> {: .python}
> > ## Solution
> > ~~~
> > import glob
> > import pandas
> > for filename in glob.glob('data/*.csv'):
> >    contents = pandas.read_csv(filename)
> >    if len(contents) < 50:
> >        print(filename, len(contents))
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

> ## Initializing
>
> Modify this program so that it finds the largest and smallest values in the list
> no matter what the range of values originally is.
>
> What are the advantages and disadvantages of using this method
> to find the range of the data?
> ~~~
> values = [...some test data...]
> smallest, largest = None, None
> for v in values:
>     if ____:
>         smallest, largest = v, v
>     ____:
>         smallest = min(____, v)
>         largest = max(____, v)
> print(smallest, largest)
> ~~~
> {: .python}
>
> > ## Solution
> > ~~~
> > values = [1, 3, 4, 5, 10]
> > smallest, largest = None, None
> > for v in values:
> >    if largest is None:
> >        smallest, largest = v, v
> >    else:
> >        smallest = min(smallest, v)
> >        largest = max(largest, v)
> > print(smallest, largest)
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

> ## Using Functions With Conditionals in Pandas
>
> Functions will often contain conditionals.  Here is a short example that
> will indicate which quartile the argument is in based on hand-coded values
> for the quartile cut points.
>
> ~~~
> def calculate_life_quartile(exp):
>     if exp < 58.41:
>         # This observation is in the first quartile
>         return 1
>     elif exp >= 58.41 and exp < 67.05:
>         # This observation is in the second quartile
>        return 2
>     elif exp >= 67.05 and exp < 71.70:
>         # This observation is in the third quartile
>        return 3
>     elif exp >= 71.70:
>         # This observation is in the fourth quartile
>        return 4
>     else:
>         # This observation has bad data
>        return None
>
> calculate_life_quartile(62.5)
> ~~~
> {: .python}
>
> ~~~
> 2
> ~~~
> {: .output}
>
> That function would typically be used within a `for` loop, but Pandas has
> a different, more efficient way of doing the same thing, and that is by
> *applying* a function to a dataframe or a portion of a dataframe.  Here
> is an example, using the definition above.
>
> ~~~
> data = pd.read_csv('Americas-data.csv')
> data['life_qrtl'] = data['lifeExp'].apply(calculate_life_quartile)
> ~~~
> {: .python}
>
> There is a lot in that second line, so let's take it piece by piece.
> On the right side of the `=` we start with `data['lifeExp']`, which is the
> column in the dataframe called `data` labeled `lifExp`.  We use the
> `apply()` to do what it says, apply the `calculate_life_quartile` to the
> value of this column for every row in the dataframe.
{: .callout}
