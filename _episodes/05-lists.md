---
title: "Lists"
teaching: 15
exercises: 15
questions:
- "How can I store multiple items?"
objectives:
- "Explain why programs need collections of items."
- "Write programs that create flat lists, index them, slice them, and modify them through assignment and method calls."
keypoints:
- "A list stores many items in a single structure."
- "Use an item's index to fetch it from a list."
- "Lists' items can be replaced by assigning to them."
- "Appending items to a list lengthens it."
- "Use `del` to remove items from a list entirely."
- "The empty list contains no items."
- "Lists may contain items of different types."
- "Character strings are immutable."
- "Indexing beyond the end of the collection is an error."
---
## A list stores many items in a single structure

Scenario: You have set up an thermometer to do temperature measurements in a storage room for rare books.
*   Doing calculations with a hundred variables called `temperature_001`, `temperature_002`, etc.,
    would be at least as slow as doing them by hand.
*   Use a *list* to store many items together.
    *   List items are contained within square brackets `[...]`.
    *   List items are separated by commas `,`.
    *   List items are ordered by their index number.
*   Use `len` to find out how many items are in a list.

~~~
temperatures = [17.3, 17.5, 17.7, 17.5, 17.6]
print('temperatures:', temperatures)
print('length:', len(temperatures))
~~~
{: .python}
~~~
temperatures: [17.3, 17.5, 17.7, 17.5, 17.6]
length: 5
~~~
{: .output}

## Use an item's index to fetch it from a list

*   Just like with strings, we can use index to find a given item in a list.
*   And just like with strings, the elements in a list are 0-indexed. (See lesson about [Data Types]({{page.root}}/01-data-types/index.html#index).)

~~~
print('zeroth item of temperatures:', temperatures[0])
print('fourth item of temperatures:', temperatures[4])
~~~
{: .python}
~~~
zeroth item of temperatures: 17.3
fourth item of temperatures: 17.6
~~~
{: .output}

## Slice

*   Just like with [strings]({{page.root}}/01-data-types/index.html#slice), we can use indexing syntax to slice lists.
*   If `l` is a list, an expression of the form `l[start:stop]` returns the portion of `l` starting with position `start`, and up to ***but not including*** position `stop`.
*   Take a look at the example with the list of temperatures:

~~~
print(temperatures)
print(temperatures[1:4])
~~~
{: .python}
~~~
[17.3, 17.5, 17.7, 17.5, 17.6]
[17.5, 17.7, 17.5]
~~~
{: .output}

## Lists are mutable

In Python, _mutable_ data types, such as lists, are data structures that can be modified or changed after they are created. This means you can add, remove, or modify elements within a list without creating a new list.

For example, you can append new items, insert items at specific positions, remove items, and change the values of existing items in a list. This behavior contrasts with _immutable_ data types, like integers, floats, and strings, where once created, their contents cannot be altered without creating a new object. (This was briefly mentioned in the lesson about [Variables and Assignment]({{page.root}}/02-variables-and-assignment/index.html#use-variables-to-store-values).)

## Lists' items can be replaced by assigning to them

Use an index expression on the left of the assignment operator (`=`) to replace a value:

~~~
temperatures[0] = 16.5
print('temperatures is now:', temperatures)
~~~
{: .python}
~~~
temperatures is now: [16.5, 17.5, 17.7, 17.5, 17.6]
~~~
{: .output}

## Appending items to a list lengthens it

Use `list_name.append` to add items to the end of a list:

~~~
print('temperatures is initially:', temperatures)
temperatures.append(17.9)
temperatures.append(18.2)
print('temperatures has become:', temperatures)
~~~
{: .python}
~~~
temperatures is initially: [16.5, 17.5, 17.7, 17.5, 17.6]
temperatures has become: [16.5, 17.5, 17.7, 17.5, 17.6, 17.9, 18.2]
~~~
{: .output}

*   `append` is a *method* of lists.
    *   Like a function, but tied to a particular object.
*   Use `object_name.method_name` to call methods.
*   We will meet other methods of lists as we go along.
    *   Use `help(list)` for a preview.

<table style="border: 1px solid black;">
    <tr>
        <th>Method</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>`append()`</td>
        <td>Adds an element at the end of the list</td>
    </tr>
    <tr>
        <td>`clear()`</td>
        <td>Removes all the elements from the list</td>
    </tr>
    <tr>
        <td>`copy()`</td>
        <td>Returns a copy of the list</td>
    </tr>
    <tr>
        <td>`count()`</td>
        <td>Returns the number of elements with the specified value</td>
    </tr>
    <tr>
        <td>`extend()`</td>
        <td>Add the elements of a list (or any iterable), to the end of the current list</td>
    </tr>
    <tr>
        <td>`index()`</td>
        <td>Returns the index of the first element with the specified value</td>
    </tr>
    <tr>
        <td>`insert()`</td>
        <td>Adds an element at the specified position</td>
    </tr>
    <tr>
        <td>`pop()`</td>
        <td>Removes the element at the specified position</td>
    </tr>
    <tr>
        <td>`remove()`</td>
        <td>Removes the first item with the specified value</td>
    </tr>
    <tr>
        <td>`reverse()`</td>
        <td>Reverses the order of the list</td>
    </tr>
    <tr>
        <td>`sort()`</td>
        <td>Sorts the list</td>
    </tr>
</table>


| Method     | Description                                             |
|------------|---------------------------------------------------------|
| `append()` | Adds an element at the end of the list                 |
| `clear()`  | Removes all the elements from the list                |
| `copy()`   | Returns a copy of the list                             |
| `count()`  | Returns the number of elements with the specified value|
| `extend()` | Adds the elements of a list (or any iterable) to the end of the current list |
| `index()`  | Returns the index of the first element with the specified value |
| `insert()` | Adds an element at the specified position              |
| `max()` | Calculates the maximum of all the elements of the List              |
| `min()` | Calculates the minimum of all the elements of the List              |
| `pop()`    | Removes the element at the specified position          |
| `remove()` | Removes the first item with the specified value        |
| `reverse()`| Reverses the order of the list                         |
| `sort()`   | Sorts the list                                         |


## Use `del` to remove items from a list entirely

*   `del list_name[index]` removes an item from a list and shortens the list.
*   Not a function or a method, but a statement in the language.

~~~
numbers = [2, 3, 5, 7, 11]
print('numbers before removing last item:', numbers)
del numbers[4]
print('numbers after removing last item:', numbers)
~~~
{: .python}
~~~
numbers before removing last item: [2, 3, 5, 7, 11]
numbers after removing last item: [2, 3, 5, 7]
~~~
{: .output}

## The empty list contains no items

*   Use `[]` on its own to represent a list that doesn't contain any items.
    *   "The zero of lists."
*   Helpful as a starting point for collecting values
    (which we will see in the next episode about [For Loops]({{page.root}}/06-for-loops/)).

## Lists may contain items of different types

A single list may contain numbers, strings, and anything else.

~~~
goals = [1, 'Create lists.', 2, 'Extract items from lists.', 3, 'Modify lists.']
print(goals)
~~~
{: .python}
~~~
[1, 'Create lists.', 2, 'Extract items from lists.', 3, 'Modify lists.']
~~~
{: .output}

## Character strings are immutable

Remember that you can get single characters from a character string using indexes in square brackets:

~~~
element = 'carbon'
print('zeroth character:', element[0])
print('third character:', element[3])
~~~
{: .python}
~~~
zeroth character: c
third character: b
~~~
{: .output}

<br/>
***But!***

*   You cannot alter the characters in a string after it has been created.
    *   *Immutable*: cannot be changed after creation. E.g., strings.
    *   In contrast, lists are *mutable*: they can be modified in place.
*   Python considers the string to be a single value with parts,
    not a collection of values.

~~~
element[0] = 'C'
~~~
{: .python}
~~~
TypeError: 'str' object does not support item assignment
~~~
{: .error}

*   Lists and character strings are both *collections*.

<br/>
> ## Notice the difference between overwriting and changing values
>
> In Python, when you use the assignment operator (`=`) with a variable (*and not a variable index!*), 
> it doesn't change the original value of the variable. 
> Instead, it replaces the current value of the variable with the new value on the right-hand side of the assignment.
>
> ~~~
> element = 'carbon'
> print(element)
> element = 'helium'
> print(element)
> ~~~
> {: .python}
> ~~~
> carbon
> helium
> ~~~
> {: .output}
>
> In the code above, the variable `element` initially holds the value 'carbon', but when the second line is executed, it is overwritten with the new value 'helium'.
> The old value 'carbon' is effectively discarded, and `element` now contains 'helium'.
>
> In contrast, when assigning to a list index:
>
> ~~~
> elements = ['carbon', 'helium']
> print(elements)
> elements[0] = 'hydrogen'
> print(elements)
> ~~~
> {: .python}
> ~~~
> ['carbon', 'helium']
> ['hydrogen', 'helium']
> ~~~
> {: .output}
>
> We don't overwrite the variable `elements` but rather we change the content of the zeroth index.\
> Thus, the difference between *immutable* and *mutable* data types.
>
{: .callout}

## Indexing beyond the end of the collection is an error

*   Python reports an `IndexError` if we attempt to access a value that doesn't exist.
    *   This is a kind of [runtime error]({{page.root}}/04-built-in-functions-and-help/index.html#python-reports-a-runtime-error-when-something-goes-wrong-while-a-program-is-executing).

~~~
print('99th element of element is:', element[99])
~~~
{: .python}
~~~
IndexError: string index out of range
~~~
{: .output}

## Exercises

> ## Fill in the Blanks
>
> Fill in the blanks so that the program below produces the output shown.
>
> ~~~
> values = ____
> values.____(1)
> values.____(3)
> values.____(5)
> print('first time:', values)
> values = values[____]
> print('second time:', values)
> ~~~
> {: .python}
>
> ~~~
> first time: [1, 3, 5]
> second time: [3, 5]
> ~~~
> {: .output}
> > ## Solution
> > ~~~
> > values = []
> > values.append(1)
> > values.append(3)
> > values.append(5)
> > print('first time:', values)
> > values = values[1:3]
> > print('second time:', values)
> > ~~~
> > {: .python}
> > ~~~
> > first time: [1, 3, 5]
> > second time: [3, 5]
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## How Large is a Slice?
>
> If 'low' and 'high' are both non-negative integers,
> how long is the list `values[low:high]`?
> > ## Solution
> > The list's length would be equal to `high - low`.  
> {: .solution}
{: .challenge}

> ## From Strings to Lists and Back
>
> Given this:
>
> ~~~
> print('string to list:', list('tin'))
> print('list to string:', ''.join(['g', 'o', 'l', 'd']))
> print('list to string:', '-'.join(['g', 'o', 'l', 'd']))
> ~~~
> {: .python}
> 
> ~~~
> string to list: ['t', 'i', 'n']
> list to string: gold
> list to string: g-o-l-d
> ~~~
> {: .output}
> 
> 1.  Explain in simple terms what `list('some string')` does.
> 2.  What does `'-'.join(['x', 'y'])` generate?  
> 
> > ## Solution
> >  1.  It creates a list of the `some string`s characters as elements. 
> >  2.  It creates a string composed of `x` and `y`, separated by a hyphen character(`-`).  
> {: .solution}
{: .challenge}

> ## Working With the End
>
> What does the following program print?
>
> ~~~
> element = 'helium'
> print(element[-1])
> ~~~
> {: .python}
>
> 1.  How does Python interpret a negative index?
> 2.  If a list or string has N elements,
>     what is the most negative index that can safely be used with it,
>     and what location does that index represent?
> 3.  If `values` is a list, what does `del values[-1]` do?
> 4.  How can you display all elements but the last one without changing `values`?
>     (Hint: you will need to combine slicing and negative indexing.)  
> 
> > ## Solution
> > ~~~
> > m
> > ~~~
> > {: .output}
> > 1.  A negative index begins at the final element. 
> > 2.  `-(N)` corresponds to the first index, which is the [0] index.
> > 3.  It removes the final element of the list. 
> > 4.  You could do the following: `print(values[0:-1])`
> {: .solution}
{: .challenge}

> ## Stepping Through a List
>
> What does the following program print?
>
> ~~~
> element = 'fluorine'
> print(element[::2])
> print(element[::-1])
> ~~~
> {: .python}
>
> 1.  If we write a slice as `low:high:stride`, what does `stride` do?
> 2.  What expression would select all of the even-numbered items from a collection?  
> 
> > ## Solution
> > ~~~
> > furn
> > eniroulf
> > ~~~
> > {: .output}
> > 1.  `stride` indicates both the number of steps, and from which end: positive starts from first element, negative from the last element. 
> > 2.  `element[1::2]`
> {: .solution}
{: .challenge}

> ## Slice Bounds
>
> What does the following program print?
>
> ~~~
> element = 'lithium'
> print(element[0:20])
> print(element[-1:3])
> ~~~
> {: .python}
> > ## Solution
> > 
> > ~~~
> > lithium 
> > ''
> > ~~~
> > {: .output}
> > There is no 20th index, so the entire string is captured.  
> > There is no element after the -1 index.  
> {: .solution}
{: .challenge}

> ## Sort and Sorted
>
> What do these two programs print?
> In simple terms, explain the difference between `sorted(letters)` and `letters.sort()`.
>
> ~~~
> # Program A
> letters = list('gold')
> result = sorted(letters)
> print('letters is', letters, 'and result is', result)
> ~~~
> {: .python}
>
> ~~~
> # Program B
> letters = list('gold')
> result = letters.sort()
> print('letters is', letters, 'and result is', result)
> ~~~
> {: .python}
>
> > ## Solution
> > Program A:
> > ~~~
> > letters is ['g', 'o', 'l', 'd'] and result is ['d', 'g', 'l', 'o']
> > ~~~
> > {: .output}
> > Program B:
> > ~~~
> > letters is ['d', 'g', 'l', 'o'] and result is None
> > ~~~
> > {: .output}
> > `sorted(letters)` returns a sorted copy of the list without changing the original list, while `letters.sort()` sorts the original list but does not return anything, i.e. returns `None`.
> {: .solution}
{: .challenge}

> ## Copying (or Not)
>
> What do these two programs print?
> In simple terms, explain the difference between `new = old` and `new = old[:]`.
>
> ~~~
> # Program A
> old = list('gold')
> new = old      # simple assignment
> new[0] = 'D'
> print('new is', new, 'and old is', old)
> ~~~
> {: .python}
>
> ~~~
> # Program B
> old = list('gold')
> new = old[:]   # assigning a slice
> new[0] = 'D'
> print('new is', new, 'and old is', old)
> ~~~
> {: .python}
>
> > ## Solution
> > Program A:
> > ~~~
> > new is ['D', 'o', 'l', 'd'] and old is ['D', 'o', 'l', 'd']
> > ~~~
> > {: .output}
> > Program B:
> > ~~~
> > new is ['D', 'o', 'l', 'd'] and old is ['g', 'o', 'l', 'd']
> > ~~~
> > {: .output}
> > 
> > `new = old` is assigning `old` to `new`, whereas `new = old[:]` is a **slice assignment**, which will only return a copy of `old`.
> {: .solution}
{: .challenge}
