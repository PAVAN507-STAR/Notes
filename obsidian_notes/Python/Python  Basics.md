# Basic Functions
- `input()` function returns the data entered by the user.
- `print()` prints the output to console and returns a null value
- `print(value+variable)` can be used to add 2 values of same data type and print the result.This can be done with strings too.
- `print(*objects,sep='',end='\n',flush=False)` we can change the end of print statement from \n to something else and `sep` refers to separator i.e the default value to use to separate two variables while printing.
- In above `sep,flush etc..` are named parameters and all objects are numbered parameters.
- In order to use double quotes inside print use `\string\` 
- We can use fstring in python to print different datatypes at a time using `print(f"hello,{name}")`.
- `round(number,round upto digits(optional))` is used to round the numbers.
- We can use `print(f"{z:,}")` to add commas to a number
- `print(f"{z:.nf}")` to round a number z to n numbers.
- 
# String Functions
-  `str.strip()` to remove white spaces in a string from both left and right.
- `str.capitalize()` to capitalise the entire string
- `str.title()` capitalise only the first title
- `str.split(separator)` to split the string into different parts using the separator.
- `str.count(value)` returns the frequency of value in string
- `str.index(value)` returns the in
- 
- dex of first occurrence of value in string
- `str.endswith(value)` returns true if the string ends with the specified value and `str.startswith().
- `str.rindex(value)` return last occurrence of value in string.
- Refer for more string functions [https://www.w3schools.com/python/python_ref_string.asp]() 
 




# Functions
- `def name(parameters):code` general syntax for declaration of a function
- It is a good practice to use a main function where other functions are being called.
- A function can have a `return value` statement to return a value to caller function.

# Conditionals
- `if condition:code` executes code when the condition is true
- `elif condition:code` executes code when the condition is true.This is used to when there is different code for different values of a condition.
- `else:code` executes when all the if and elif's are all false
- `or`  or `|` used in conditions to check if one of the condition is true
- `and` or `&`  `used to check when two or more conditions are true.
- Python has bool datatype consisting of either `True` or `False`
- `match variable/expression:case value1:code` works similar to switch in C or C++ matches the variables value to any one of the cases and executes the respective code and for the default case use  `case _:code

- `while condition:code` executes the code as long as the condition is true.
- `for i in range(n):code` executes the code for  n times.
- When u use a variable like i just for sake of iterating of program that we do not use anywhere else it can be replaced by `_` unde
# Lists and Dictionaries
- A list is a collection of elements or values of same data type is denoted by `[]`
- `l.append(element)`  to append an element into a list
- `l.sort()` to sort the list
- `l.pop()` to an element from end of the list.
- `l.count()` returns no of elements in list
- `l.reverse()` reverse the order of elements in list
- `l.insert(pos,element)` to insert an element at a specific location
- `l.index(element)` returns the index of first occurrence of the element 
- A dictionary is used to store a key and value at a time i.e different values for different elements.It is denoted by `{}`
- Example: `a = {"harry":"griffindor","draco":"slytherin","hermoine":"griffindor"}`
- A list of dictionaries can be used.
- A tuple `()` is a immutable list i.e the data cannot be changed in a tuple

# Exception Handling
- This is used to handle general syntax,value,..etc different types of errors.
- The general syntax is `try:code except errorname:code else:code` .This just tries the code in the try section and if any of the specified expect error occurs then the corresponding code is executed and if no error specified is occurs then else code gets executed.
- 

# Libraries
- `random` is used to for generating random numbers,choices..etc
- `random.randint(start,end)` is used to generate random numbers
- `random.choice(list)` returns a random value from given list
- `random.shuffle(list)` shuffles the order of list
- `statistics` library is used to perform operations like mean,mode,average on data sets.
- `sys` is used to perform operations on system level like command line arguments or exiting the program etc
- `sys.argv[]` is used to get the command line arguments passed by user.
- `requests` is used to handle website HTTP request functions
- `json` is used to read or edit a json file while reading data from a website which is generally in json format 

# Regex
- It is used to use regex expression in python .Mainly used to  find patterns in a string used as `import re`
- Some basic parameters and special characters usage in regex
![[2024-02-11T19:10:24,183573221+05:30.png]]
![[2024-02-11T19:11:15,609306727+05:30.png]]![[2024-02-11T19:11:33,437032538+05:30.png]]

- `re.search(pattern,string,flags=0)`   is used to search for a pattern in a string if necessary one can use one of above special characters for advanced search patterns.
- To search for a pattern with a dot (.)  use  `\.` in pattern in `re.search(r"pattern",string,flags=0)` to tell compiler to treat the symbols as characters and not anything special.Here r refers to raw string.
- `re.match(pattern,string,flags=0)`  similar to search but  matches the start of the string by default
- `re.fullmatch(patter,string,flags=0)` similar to match but also matches the end of string by default.


 

# Object Oriented Programming 
- `class`  keyword is used to !make or create a class in python. `class name:`
- An object is instance of a class.
- A class has instance variables or attributes 
- A class can have several functions in it.
- `def __init__(self,parameters)` is used to initialise an object after using a object.
- To pass the values directly to class we use `self.parameter =value` in `__init__` function.
- The `self` parameter is used to pass the reference of the object created to the functions i.e if two instances of same class were  created so when calling a method in a class the reference of the object is passed as self to the function or method.
- We can create `self.variable =value` even though it is not passed as parameter in a class.
- A class can inherit the properties of another class by  `class name(class2):` here the name class can use all the functions present in the class 2.
- The inherited class's function can accessed by `super().function()` 
- Variables created in the class directly can be accessed by class name rather than the object or instance name.These are called class attributes.
- A class method is used to return something from the class attributes.`@classmethod` is a decorator used to specify that a method is a class method.
- `def name(cls):return cls.attribute` is the general syntax for defining class methods.
- A class method can be called on the class itself rather than instance or object.
- `@staticmethod` and all the other decorators can be called on class directly.
- 
