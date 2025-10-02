# Python Intro notes

## Basics on numbers and inbuilt functions

### numbers, strings, Boolean etc.

- most common types of data stored in variables are: **strings, numbers and Boolean Terms** (`True` and `False`)
- it is possible to change data format as follows:
`str()`    translates integer between brackets into a string 
`int()`    translates into an integer, rounding down
`float()`  translates into a real number

### None value and zero

- absence of a value - no value at all, to distinguish from Errors, zero  or blanks - conveys absence rather than emptiness
- **Python starts counting at 0**

### inbuilt functions 
(not commands, but intuitively same feel like commands)

- `input()`  expects the user to input text with keyboard and press enter. **Note**: it always returns as a string.
  ```python
  name= input("Enter your name: ") #create a variable from user input

- `print()`  prints string between quotations ''
- `len()`    counts number of characters (length) in a string

### import functions

- `import`  ~modulename
- brings the whole module into your code.
- module includes several functions, to call a function inside a module need to include both module and command name

- `module.function()` accesses the command defined inside the module.

```python

import random

# Generate a random integer between 1 and 10
number = random.randint(1, 10)

print(number)
```


- import alternative: `from math import *` the asterisk means import entire math moduel into current namespace an no need to retype `math.` as a prefix each time 
  
### terminate a program

- first import `sys`
- end programme by calling `sys.exit()`
- manual interrupt the programme(i.e. when stuck): Strg+c
  
### end and sep

- in print command  a line break is added at end automatically
- you can define what is put at the end you can write `end =''` -  i.e. no space, nothing between the two quotes, meaning no line break
- `sep=','` specifies how you want strings to be separated in this example, by a comma

```python
for i in range(5, 0, -1):
    print(i, end='...')

print("Lift off!")

>>>5...4...3...2...1...Lift off!

# without end'...' :
>>>
5
4
3
2
1
Lift off!
```

### operators/arithmetic

- `*` is used to multiply strings - `5*'hello'`  &rarr; 'hellohellohellohellohello'

- `==`    		equal to (works with string)
- `!=`    		not equal to (works with string)
- `<`/`>`   	less and greater than (two differnt ones) (*not* work with string)
- `<=` or `>=`	less than or equal/greater than or equal (*no* strings)

*handy functions for numbers*
- modulus `%`it devides first number by second number and returns the remainder `10%2`returns 0, there is no remainder
- `abs()`returns absolute value
- `pow(3,2)`raises the first number to the power of the second number
- `max()` and `min()`returns the larger/smaller of the two numbers given to it
- `round()`allows to round a number to next integer
- `floor()` and `ceil()`like round but always to lowerst/highest full integer (note this requires the maths module to be imported)
- `sqrt()` takes squareroot of number

### Boolean operators - not, and, or

hierarchy (order of application) is 
1. not
2. and
3. or

True and True	&rarr; True
True and False	&rarr; False
False and False	&rarr; False
False and True	&rarr; False

True or True &rarr;		True
True or False &rarr;	True
False or True &rarr; 	True
False or False &rarr; 	False

not True &rarr; False
not Fasle &rarr; True

## Flow control (if, elif, else)

- determine the order in which code is executed (such as looping through data)
- block of code starts when indentation begins
- can contain nested blocks
- end when indentation goes to 0

### if 

ask programem to execute an action if a condition if True

1. `if`  + the condition + colon `:`
2. next line indented follows the action to be taken if condition is true

### elif 

- allows for a chain of conditions that stops if one of them is True
- only continues if all previous conditions are false
- one or none of them will be executed, 
- if an earlier condition is true, all the subsequent ones are skipped
1. `elif` +condition + `:`n
2. indented if clause

### else 

- specifies action to carry out if condition is False
1. Format: `else:`
2. next line indented follows action to be taken if condition is false

```python
if x > 0:
   print("Positive")
elif x == 0:
   print("Zero")
else:
   print("Negative")
```

### while statement

- repeats an action until the condition is false
- same structure as if 
- `while True:` is an infinite loop, the condition is always true and never ends on it's own
- it is used when we don't know how long, how many iterations a loop is for and want to run it until a certain condition is met

```python
while True:
    print("This will print forever!")
```

### break or continue a loop

- `break`  exits a loop
- `continue` makes execution start back at the beginning of the loop


| Statement            | Description                        |
| -------------------- | ---------------------------------- |
| `if`, `elif`, `else` | Conditional execution              |
| `for`                | Loop through a sequence            |
| `while`              | Loop while a condition is `True`   |
| `break`              | Exit the loop early                |
| `continue`           | Skip the current loop iteration    |
| `pass`               | Do nothing (used as a placeholder) |
| `return`             | Exit a function and return a value |

### range

- specifies the number of times a loop is run
- starts at 0 and ends (n-1), moves in integers
- one argument in brackets specifies end: `range(5)` &rarr;  0, 1, 2, 3, 4
- two arguments specify start point and end point `range(12,17)` &rarr; 12, 13, 14, 15, 16
three arguments specify start point, end point, steps:`range(5, 50, 10)`&rarr; 5, 15, 25, 35, 45

1.  `for i in range ():`
2.  function saying what should happen that number of times


## Functions
### define

- `def function(argument):`
- function - is like a mini programme that you can define
- function runs all the code inside it (i.e. all the code that is indented)
- used to avoid duplication (things you need to do over and over again)
- anything that you use more than once define in a function. It helps with debugging. If there is an error it only needs correcting once

**Example:** define a function called 'greet' that prints a greeting for every new user

```python
def greet(user):	
#define function called 'greet' with parameter 'user' It meeans whenever fucntion is called there must be a parameter provided
	message = "Hello" + user 
	#inside the function, define variable 'message', which is a string concatenated with parametre 'user'
	print(message) 
	#the function asks the programme to print the variable 'message'

greet(" Walrus") #call the function with argument Walrus.
>>> Hello Walrus
```

### key terms
**variable:**
- variables are like containers in which to store data
- defined inside the function to store a value (i.e.the expression the function is generating) 
- created and used inside the function
  
*local:* exists inside the function (like 'message' in example above) destroyed once function ends 
*global*: defined outside the function - exists as long as porgramme is running 

**parameter:** 
- a placeholder for the value that you will give the function (i.e. user)
- formally a 'named variable' that specifies what kind of input the function can expect

**argument:**
- the value that the parameter can take when the function is called (i.e. Bob or Kate). 
- argument is supplied by the caller at the moment the function is called. 
- once the function is executed the value will be forgotten. 
  
```python
	# for parameter 'user', caller supplies argument 'Bob' and calls the function 'greet'
	greet (Bob)
	# the programme will print
	>>> Hello Bob
```

### return statement

-  `return` specifies teh value a function returns back to the caller after it is called 


```python
#in maths terms, 

def f(x):       #for each parametre x this function
	y=x+2
	return y  	#returns y
```


### try and except

- if you define a function but you foresee an error, you can use try and specify what happens in case the error occurs.
  


try:
	#do the thing
except *the condition that may cause an error*:
	#do something els


## Lists, Tuples, Dictionaries

compound data types that group values

### lists

- a list is written as comma seperated elements between square brackets
- can mix types (str, int, float etc.) `my_list = [42, "hello", 3.14, True]`
- different ways to define the same list
  - `example = ['a', 'b', 'c', 'd', 'e']`
  - `example=list('abcde')`
<br>

- the sequence in calling list elements is **`[start : stop : step]`**
- elements are *indexed*
- indexing starts at **0** , calling  `example[2]` returns 'c' 
- supports counting backwards (`-1` is the last element, `-2` the penultimate, …). `example[-3:]` starts counting at third elements from the back and returns ['c', 'd', 'e']
- `stop` excludes the last element.`example[0:5:2]` returns ['a' ,'c' ,'e']
<br>

**Cheat sheet**
```
seq[a:b]      # a … b‑1
seq[:b]       # start → b‑1
seq[a:]       # a → end
seq[:]        # copy of the whole sequence
seq[a: b:c]   # step c (positive → forward, negative → backward)
seq[::-1]     # reverse
seq[::2]      # every other element
seq[-3:]      # last three elements
seq[:-3]      # everything except the last three
```

**grab specific characters in a string** 
- using `[]` &rarr;`print(phrase[2])`yields the third index (lower case r)
- index function allows us to find certain characters (i.e. G) in a string &rarr; `phrase.index("G")`yields `0`as it's the first character. if there are more than on, it returns the first

**popualte lists using expressions inside square brackets**

```python

example1=[x for x in range(9)] 
#list of integers 0 through 8` → [0, 1, 2, 3, 4, 5, 6, 7, 8]

example2=[x for x in range(10) if x%3==0] #→ [0, 3, 6, 9]
```

### list operations

using example list: `s=list('abcddfg')`
- **replace** an element `s[4]='e'` &rarr; change d to e
- **delete** an element `del s[4]` &rarr; delete d
- **concatenate and replace** `s=s+[1, 3, 5]` &rarr; ['a', 'b', 'c', 'd', 'e', 'f', 'g' 1, 3, 5]
<br>

- `len()` counts the number of elements in the list
- **do something for every element in a list** by looping over every element in the list
```python

s=list(range(1,5)) # →[1, 2, 3, 4]
for i in s:
	print(i/2) # →[0.5, 1, 1.5, 2] - each on a new line
```

## Methods

### upper/lower, index, append, insert, copy

*useful operators inside strings:*
  - `\n`add a new line inside the string
  - whatever character comes after `\` is ignored
  - change the case by using the function `.lower`and `.upper` to change case
```python
phrase="Giraffe Academy"
print (phrase.upper())
>>>GIRAFFE ACADEMY
```
- check if the string is upper or lower case using `.isupper`or `.islower`
- you can combine them with each other: (1) transform into upper (2) check if all is upper &rarr; result will be TRUE/FALSE
```python
print(phrase.isupper()) 
>>>FALSE #the text is "Giraffe Academy" not all of it in upper case
prints(phrase.upper().isupper) #transforms all of it into upper case and checks if that was correct
>>>TRUE
```
- `phrase.replace("Giraffe", "Elephant)` &rarr; >>>Elephant Academy

*useful operators inside lists:*
- use this list: `s=list("abcde")` and `t=list(range(1,10,2)`
  
- `s.index('b')`returns **where in a list an element** is &rarr; 1
- for strings can add entire words (using Giraffe Academy example): `print(phrase.index("Acad"))`&rarr; - returns where in string this starts (8)
- `s.append(e)` **appends** an element &rarr; ['a', 'b', 'c', 'd', 'e']
- `s.extend(t)` **adds** another list to the list &rarr; ['a', 'b', 'c', 'd', 'e', 1, 3, 5, 7, 9]
- `s.insert(1, 'a')` **insert** new elements to a list at specific index &rarr; ['a','a', 'b', 'c', 'd', 'e']
- `s.count("a")`**counts** occurance of element
- `s.remove("a")` **removes** element from list &rarr; ['a', 'b', 'c', 'd', 'e']
-  note `del s(0)` allows to **remove by index** of the element. if the element appears twice only the first will be deleted &rarr; [ 'b', 'c', 'd', 'e']
-  `s.clear()` deletes the elements of the list and gives us an **empty list**
-  `s.pop()` **pops the last element** from the list
-  `s.sort()`  sorts the list

- lists can be arguments in functions and methods can also appear in functions
- 
```python
def f(x):
	x.append('!')   # define a function that adds ! to any parameter x. x must be a list

lst =[1, 2, 3]     # define a list 

f(lst)             # pass the list as an argument into the function 
print(lst)         # the list is permanently modified
>>>[1, 2, 3, '!']

```

### reversed() and join()

- `reversed()` gives you the items backwards, output is not printable, needs to be converted
```python
s=list(range(1,5)) # →[1, 2, 3, 4]
revs =reversed(s) #this cannot be printed it creates a reverse iterator object
print(list(revs)) # →[4, 3, 2, 1]
```
- `join()` glues reveresed strings together, only works with string
```python
sstr=list("abcde") # →[a, b, c, d, e]
revsstr =reversed(sstr) # cannot be printed
gluedrevsstr=', '.join(revsstr)
print(gluedrevsstr) # →e, d, c, b, a
```


- *variables do not store lists directly*. they store references to lists
```python
#if you have a list (abcde) and you give it a name (alphabet), 
alphabet=list('abcde')
#if you assign the list to another variable name (i.e. schmalphabet) 
schmalphabet=alphabet
#changes made to either alphabet or schmalphabet refer to the same list
alphabet.append('f')
print(alphabet)
>>>['a', 'b', 'c', 'd', 'e', 'f']
print(schmalphabet)
>>>['a', 'b', 'c', 'd', 'e', 'f']
```
- to avoid permanent changes use copy
```python
schmalphabet = alphabet.copy()
#changes are now made to different lists
alphabet.append('g')
print(alphabet, schmalphabet)
>>>['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>>['a', 'b', 'c', 'd', 'e', 'f']
```
### in and not

in and not allow to check if a element is in a list or not


### tuples
- ordered sequence that does not change
- created in roudn parenthese `t=('a', 'b', 'c')` or `t = tuple("abc")`
- tuples are immutable, cannot change them
- can have a list of tuples (i.e. coordinates) `coordinate=[(2,4), (5,6), (8,9)]`
- data is more safely saved in tuples
- tuple has round brackets and comma between elements, elements can be word and numbers together 
- many of the functions used for list data also work for tuples 
- lists and tuples can be converted using `l=list(mytuple)` and `t=tuple(mylist)`

### dictionaries

- a collection of values (like a list)
- composed of value-key pairs separated by a colon

```python
csuite = {'CEO':'Bob', 'CFO': 'Kate', 'COO': 'Femi', 'CTO' : 'Vijay' } 
print(csuite['CFO'])
>>>Kate

```
- order of value-key pairs does not matter
- same pairs, no matter the order, mean two dictionaries are equal
- dictionaries are good for associating keys with values

if you ask if a value is in a dictionary (`val in dict`) thsi checks if there is a **key**   called  val, 

set a defalut value: 

`dict={}`
`dict.setdefault ('key1,0)

###  keys(), values() and items() Methods

returns lists of the dictionaries keys(, values() or key-value pairs called items())

```
exampledict={1:'a', 2:'b', 3:'c'}

for i in exampledict.values():
	print(i)
for j in exampledict.keys():
	print(j)
for k in exampledict.items():
	print(k)
```


`for i, j in letter.items():     # i  → the **outer** key  (e.g. 'dict1', 'dict2', 'dict3')    # j  → the **inner** dictionary that belongs to that outer key`

When you call `.items()` on a dictionary, Python produces an iterator of **(key, value)** tuples.  
In the case of a _dictionary‑of‑dictionaries_ like yours:

`letter = {     'dict1': {'a': 1, 'b': 2},    'dict2': {'c': 3, 'b': 4},    'dict3': {'a': 5, 'd': 6} }`

`letter.items()` yields:

`('dict1', {'a': 1, 'b': 2}) ('dict2', {'c': 3, 'b': 4}) ('dict3', {'a': 5, 'd': 6})`

So during each loop iteration:

- `i` receives the outer key string (`'dict1'`, `'dict2'`, `'dict3'`).
- `j` receives the corresponding inner dictionary (`{'a': 1, 'b': 2}`, etc.).

Because `j` is itself a dictionary, you can safely call methods like `j.get(number, 0)` to look up a particular inner key (`'a'`, `'b'`, …) and obtain its numeric value (or `0` if that key isn’t present).

### get

in lists you could use the index number list[0] to call an element in the list. 
get() allows you to call the value fro a given key

### sets

sets store unique unordered elements

`print[x,y] for x in` [1, 2, 3] and y in [4, 5, 6]`
`[[1, 4], [1, 5], [1, 6], [2, 4], [2, 5], [2, 6], [3, 4], [3, 5], [3, 6]]`
