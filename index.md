

## Exercise 9.1  Fill in the blanks

```python
values = ____
values.____(1)
values.____(3)
values.____(5)
print('first time:', values)
values = values[____]
print('second time:', values)
```

Output:
```python
first time: [1, 3, 5]
second time: [3, 5]
```

<details>
<summary>Solution
</summary>
<br>
values = []
<br>
values.append(1) 
<br>
values.append(3)
<br>
values.append(5)
<br>
print('first time:', values)
<br>
values = values[1:]
<br>
print('second time:', values)
</details>


## Exercise 9.2 From strings to lists and back

Given this:
```python
print('string to list:', list('tin'))
print('list to string:', ''.join(['g', 'o', 'l', 'd']))
```

Output:
```python
string to list: ['t', 'i', 'n']
list to string: gold
```

1. What does `list('some string')` do?
2. What does `'-'.join(['x', 'y', 'z'])` do?


## Exercise 9.3 Working with the end

What does this print?
```python
element = 'helium'
print(element[-1])
```

1. How does Python interpret a negative index?

<details>
<summary>Solution
</summary>
Python interprets a negative index as starting from the end (as opposed to starting from the beginning). The last element is -1.
</details>

<br>
<br>
2. If `values` is a list, what does `del values[-1]` do?

<details>
<summary>Solution
</summary>
Removes the last element
</details>

<br>
<br>

3. How can you display all elements but the last one without changing values? (Hint: you will need to combine slicing and negative indexing.)


<details>
<summary>Solution
</summary>
print(values[:-1])
</details>

<br><br>

## Exercise 9.4 Stepping through a list

What does this print?

```python
element = 'fluorine'
print(element[::2])
print(element[::-1])
```

1. If we write a slice as `low:high:stride`, what does `stride` do?

<details>
<summary>Solution
</summary>
Step size
</details>

<br><br>


2. What expression would select all even numbered items in the collection?

<details>
<summary>Solution
</summary>
1::2

Starts at element 1 (remember lists start at 0), goes on until the end, and has a step size of 2.
</details>

<br><br>

## Exercise 10.1 Reversing a string

Fill in the blanks in the program below so that it prints “nit” (the reverse of the original character string “tin”).

```python
original = "tin"
result = ____
for char in original:
    result = ____
print(result)
```

<details>
<summary>Solution
</summary>
blank 1 = ""
<br>
blank 2 = char + result
</details>


## Exercise 10.2 Practice accumulating

Fill in the blank to get count of the total length of the strings in the list (i.e. 12)

```python
total = 0
for word in ["red", "green", "blue"]:
    ____ = ____ + len(word)
print(total)
```

<details>
<summary>Solution
</summary>
total = total + len(word)
</details>
<br>
<br>

List of the word lengths (i.e. [3,5,4])

```python
lengths = ____
for word in ["red", "green", "blue"]:
    lengths.____(____)
print(lengths)
```

<details>
<summary>Solution
</summary>
lengths = []
<br>
lengths.append(len(word))
</details>
<br>
<br>

Concatenate all words (i.e. "redgreenblue")

```python
words = ["red", "green", "blue"]
result = ____
for word in words:
    ____
print(result)
```

<details>
<summary>Solution
</summary>
result = ""
<br>
result = result + word
</details>
<br>
<br>


## Exercise 10.3 Spotting errors

Can you spot any errors without running this code?

```python
for number in range(10):
    # use a if the number is a multiple of 3, otherwise use b
    if (Number % 3) == 0:
        message = message + a
    else:
        message = message + "b"
print(message)
```

<details>
<summary>Solution
</summary>
Python variable names are case sensitive: number and Number refer to different variables.
<br>
The variable message needs to be initialized as an empty string.
<br>
We want to add the string "a" to message, not the undefined variable a.
<br>
</details>


## Exercise 11.1 Tracing execution

Without running this, work out what the final statement will print:

```python
pressure = 71.9
if pressure > 50.0:
    pressure = 25.0
elif pressure <= 50.0:
    pressure = 0.0
print(pressure)
```

<details>
<summary>Solution
</summary>
25.0
</details>

## 11.2 Practicing if and else
Fill in the blanks so that this program creates a new list containing 0's where the original list’s values were negative and 1's where the original list’s values were positive.

```python
original = [-1.5, 0.2, 0.4, 0.0, -1.3, 0.4]
result = ____
for value in original:
    if ____:
        result.append(0)
    else:
        ____
print(result)
```

Output:
```python
[0, 1, 1, 1, 0, 1]
```


<details>
<summary>Solution
</summary>
result = []
<br>
if value < 0.0
<br>
result.append(1)
</details>


## Exercise 11.3 Processing small files

What would you insert into the blank space so that the print statement only applies to files wth fewer that 50 records?

```python
import glob
import pandas as pd
for filename in glob.glob('data/*.csv'):
    contents = pd.read_csv(filename)
    ____:
        print(filename, len(contents))
```

<details>
<summary>Solution
</summary>
if len(contents) < 50
</details>


## Exercise 12.1 Determining matches
Which of these files is not matched by: `glob.glob('data/*as*.csv')`?

1. `data/gapminder_gdp_africa.csv`
2. `data/gapminder_gdp_americas.csv`
3. `data/gapminder_gdp_asia.csv`

<details>
<summary>Solution
</summary>
1 is not matched
</details>

