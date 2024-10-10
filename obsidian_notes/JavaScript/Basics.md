# Basics about JS
- ![[Pasted image 20240521002313.png]]
- JS single threaded nature![[Pasted image 20240521003517.png]]
# variables , printing ,if else,for loop,lists,str in JS
- `let ` / `var`(not preferred much)/`const`(cannot change the value of var throughout the runtime of the program) -> all the three keywords can be used to create variables the syntax is `keyword varname=value;`
- To print something to screen `console.log(value)` is used.
- Value can be mixture of different datatypes too for printing(**boolean is a default data type in JS).
- `if/else(condition){code block};` to implement if else condition.
- `for(initialisation;condition;updation){code block};` -> syntax to create a for loop
- `[]`-> creates an array of elements.To find the **length** of array use `arrayname.length` 
- `list.includes(item)`-> checks if an item is present in the list or not.
- `str.replace(/\s+/g, "")` -> is used to remove white spaces in a string.
- Example:

```javascript
let str = "This is a string with spaces";
let result = str.replace(/\s+/g, '');
console.log(result); // Output: "Thisisastringwithspaces"
```

Here's a breakdown of how this works:

- `replace(/\s+/g, '')`: The `replace` method is used to replace occurrences of a pattern with a specified replacement.
- `/\s+/g`: This is a regular expression where:
  - `\s` matches any whitespace character (spaces, tabs, etc.).
  - `+` means one or more occurrences of the preceding element.
  - `g` is a flag that stands for "global", meaning the pattern should be applied to the entire string, not just the first occurrence.
- `''`: The replacement string, which is an empty string in this case, effectively removes the matched spaces.

- **Objects** => 

1. **Creating Objects**
Object Literals
You can create objects using object literals, which are the most common way to create objects.

```javascript
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 30,
    greet: function() {
        console.log("Hello, " + this.firstName);
    }
};
```
- `this` -> creates the instance of the current object.It can be used within the object something similar to recu
- 
- rsion.
Using the `new Object()` Syntax
Another way to create objects is by using the `new Object()` syntax, although it is less common.

```javascript
let car = new Object();
car.make = "Toyota";
car.model = "Camry";
car.year = 2021;
```

### 2. **Accessing and Modifying Object Properties**

#### Dot Notation
```javascript
console.log(person.firstName); // Accessing
person.age = 31; // Modifying
```

#### Bracket Notation
```javascript
console.log(person["lastName"]); // Accessing
person["age"] = 32; // Modifying
```

### 3. **Adding and Removing Properties**

#### Adding Properties
```javascript
person.gender = "male";
```

#### Removing Properties
```javascript
delete person.age;
```

### 4. **Methods**
Objects can have methods, which are functions stored as properties.

```javascript
let person = {
    firstName: "John",
    lastName: "Doe",
    greet: function() {
        console.log("Hello, " + this.firstName);
    }
};

person.greet(); // Output: Hello, John
```

### 5. **`this` Keyword**
The `this` keyword refers to the object from which the method was called.

```javascript
let dog = {
    name: "Buddy",
    speak: function() {
        console.log(this.name + " says woof!");
    }
};

dog.speak(); // Output: Buddy says woof!
```

### 6. **Object Constructors**
You can create **multiple objects of the same type** using constructor functions.
- The name of the function should start with upper case

```javascript
function Person(firstName, lastName, age) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
}

let person1 = new Person("Alice", "Smith", 25);
let person2 = new Person("Bob", "Brown", 30);

console.log(person1.firstName); // Output: Alice
console.log(person2.firstName); // Output: Bob
```

### 7. **ES6 Classes**
ES6 introduced classes as a syntactical sugar over the existing prototype-based inheritance.

```javascript
class Person {
    constructor(firstName, lastName, age) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
    }

    greet() {
        console.log("Hello, " + this.firstName);
    }
}

let person1 = new Person("Alice", "Smith", 25);
person1.greet(); // Output: Hello, Alice
```

### 8. **Prototypes**
All JavaScript objects inherit properties and methods from a prototype.

```javascript
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}

Person.prototype.greet = function() {
    console.log("Hello, " + this.firstName);
};

let person1 = new Person("Alice", "Smith");
person1.greet(); // Output: Hello, Alice
```

### 9. **Object Methods**

`Object.keys()`
Returns an array of a given object's property names.

```javascript
let keys = Object.keys(person);
console.log(keys); // Output: ["firstName", "lastName", "age"]
```

 `Object.values()`
Returns an array of a given object's values.

```javascript
let values = Object.values(person);
console.log(values); // Output: ["John", "Doe", 30]
```

 `Object.entries()`
Returns an array of a given object's own enumerable property [key, value] pairs.

```javascript
let entries = Object.entries(person);
console.log(entries); // Output: [["firstName", "John"], ["lastName", "Doe"], ["age", 30]]
```

 `Object.assign()`
Copies the values of all enumerable own properties from one or more source objects to a target object.

```javascript
let target = { a: 1 };
let source = { b: 2, c: 3 };
let returnedTarget = Object.assign(target, source);

console.log(returnedTarget); // Output: { a: 1, b: 2, c: 3 }
```

`Object.freeze()`
Freezes an object, preventing new properties from being added and existing properties from being removed or modified.

```javascript
let obj = { prop: 42 };
Object.freeze(obj);
obj.prop = 33; // Throws an error in strict mode
console.log(obj.prop); // Output: 42
```

Understanding and mastering objects in JavaScript is crucial for effective programming in the language. They form the backbone of most JavaScript applications, enabling complex data structures and interactions.

# Prototypes in JS
- Every object in JavaScript has a prototype property, which is a reference to another object.
- When trying to access a property or method on an object, JavaScript first looks for it directly on the object itself. If it doesn’t find it, it looks at the object’s prototype, then at the prototype’s prototype, and so on, until it reaches the end of the prototype chain (usually `Object.prototype`).
- `console.log(person1.__proto__ === Person.prototype); // Output: true` or `console.log(Object.getPrototypeOf(person1) === Person.prototype); // Output: true` used to check the  prototype of the object.
- To **modify a prototype** ->
  Modifying the prototype of a constructor function or an existing object allows you to add or change methods and properties for all instances created from that constructor function or that inherit from that object. Here are several ways to modify prototypes in JavaScript:
  You can add methods to a constructor function's prototype to ensure that all instances of that constructor function have access to the method.
```javascript
function Person(name) {
    this.name = name;
}

// Adding a method to the Person prototype
Person.prototype.greet = function() {
    console.log("Hello, " + this.name);
};

let person1 = new Person("Alice");
let person2 = new Person("Bob");

person1.greet(); // Output: Hello, Alice
person2.greet(); // Output: Hello, Bob
```

# Functions in  JS and some useful inbuilt functions.
- `function(keyword) name(parametes){ block of code; return statement;}` -> syntax to write a function in JS.A function takes inputs and executes a block of code when called and returns an output.
- A function can also take another function as input.
- To **delay a function call** we can use `setTimeout(functionname,timetodelay)`
- 
- To call a function repeatedly **after every given interval** use -> `setInterval(functionname,intervaltime)`
- `list.forEach(var for list item =>{a function });` -> this lets u apply a function on each item of list. 
- **Arrow Function `=>`**: The arrow function syntax `(transaction => { ... })` is a concise way to define a function in JavaScript. Inside the curly braces `{ ... }`, you can write the logic that should be executed for each transaction.
- - `Object.keys(object)` is a method that returns an array of a given object's own enumerable property names (keys).
# Date class in JS and some useful methods in it.
- In JavaScript, the `Date` class is used to work with dates and times. It provides methods for creating, manipulating, and formatting dates and times. Here's an overview of how the `Date` class works:

1. **Creating Date Objects**:
   You can create a new `Date` object using one of several constructors. Some common ways to create `Date` objects include:

   ```javascript
   // Create a Date object representing the current date and time
   let currentDate = new Date();

   // Create a Date object for a specific date and time (year, month, day, hour, minute, second)
   let specificDate = new Date(2024, 4, 27, 12, 30, 0);
   
   // Create a Date object by passing a string representing a date
   let dateString = new Date('2024-05-27');
   ```

2. **Getting Date and Time Components**:
   Once you have a `Date` object, you can get various components of the date and time, such as the year, month, day, hour, minute, and second, using the `get` methods:

   ```javascript
   let year = currentDate.getFullYear();
   let month = currentDate.getMonth(); // Note: Month is zero-based (0 for January, 1 for February, etc.)
   let day = currentDate.getDate();
   let hour = currentDate.getHours();
   let minute = currentDate.getMinutes();
   let second = currentDate.getSeconds();
   ```

3. **Manipulating Dates**:
   You can also manipulate dates by setting different components of the date and time using the corresponding `set` methods:

   ```javascript
   currentDate.setFullYear(2025);
   currentDate.setMonth(6); // Sets the month to July (zero-based index)
   ```

4. **Formatting Dates**:
   The `Date` class provides methods to format dates into strings according to various formats:

   ```javascript
   let formattedDate = currentDate.toDateString(); // Converts the date to a string format like "Wed May 27 2024"
   ```

5. **Working with Timestamps**:
   A timestamp represents the number of milliseconds since the Unix Epoch (January 1, 1970, 00:00:00 UTC). You can get the timestamp of a `Date` object using the `getTime()` method:

   ```javascript
   let timestamp = currentDate.getTime();
   ```

The `Date` class is a fundamental part of working with dates and times in JavaScript and is commonly used in web development for tasks such as handling event scheduling, time-based calculations, and displaying dates to users.