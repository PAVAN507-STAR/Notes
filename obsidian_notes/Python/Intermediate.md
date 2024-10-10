###### Collections
- `collections` a library use to count the frequency of a alphabet in a string using `Counter()`  function which comes with some inbuilt functions like `most_common(n)` which returns nth most common of the given string.This library is used to work on repetition of something in a string an alphabet or a substring.
- `Counter(str)` returns a dictionary with every unique element as key  and no of times it occurred as its value.Slicing can be done on it to know how many times a specific character has appeared in the string.
- `list(Counter.elements())` returns the every element of the string  individually and they are converted to a list as to use them properly.
- `namedtuple` from collections library is used to define a specific data type similar to a structure.The syntax is `namedtuple('name','values/fields')` .For example used to create a data type that can store a point's 2 dimensional location.
- The values of a named tuple can be accessed by `name.value` 