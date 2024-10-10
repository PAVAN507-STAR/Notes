
- To connect javascript file to html we use `<script src=filepath></script>`
- Try to place js connection just  above body ending tag as js takes time to run with this the website don't look laggy
- `console.log()` -> used to print something to console
- JS is a general purpose language according to ECMA 262
-  ![[Pasted image 20240805180335.png]]
- Variables can be defined in 3ways => `let name,const name,var name`
- `const` -> used to define constant variables
- `var` also does the same as let but it's not recommended to use according to the latest documentations
- Data type of variables can be changed in JS (Dynamically typed)
- Dynamically typed=> no need to specify data type before variable name
- Array's or list are considered as object 
- `let name={key:value,key:value}` is used to define an object in JS(similar to dictionary in python)
- `function name(parameters){code; return }` -> is used to create a function in JS(function is a data type in JS)
```Javascript
function sqr(a){
	return a*a;
}
console.log(sqr(3));
result = sqr(3)
console.log(sqr)
```
- Default parameter can be passed in which if no parameter passed -> default value used.
- `==` checks only if values are same and `===` checks if both value and data type are same.Both return a boolean value
- Concept of scope for variables that if a variable is local variable then it cannot be used in another or outside that function.(Global scope,Local scope,block scope)
- In function a parameter is allocated only when it's passed a value(basically calling it unless it's a default valued parameter)
- `variable=function(){}` is called as *anynomous function* as there is no name.This cannot be called before intilization like normal functions
- Arrow function can be used(or recommended) when only one statement is present in body and if u need to return something the return statement is not necessary and also {} as in the below code
```javascript
sum1 = (a,b)==>{return a+b;}
sum 2 = (a,b) ==> a+b;
```
- Objects,arrays and functions comes under **non-primitive** datatypes and the rest comes under **primitive** datatypes
- Primitive data types are allocated memory during compile time in Stack as memory is already known
- Non-Primitive data types are allocated memory during run time in heap dynamically as memory required is not known during compile time
- In Non primitive variable name is used as reference to some point in heap
- Equality operator between two objects variables return false even if the data is same as the variables store references which is always distinct. ![[Pasted image 20240806181856.png]]
- Arrays indexing works same as python and instead of `**in arr**` we use `of arr`
- `arr.unshift(elements)` => used to insert some elements to array at the front.
- `arr.push(elements)` => used to insert elements at the end.
- `arr.splice(index,how many elements to delete,value)` => is used to insert  or delete element at random
- `arr.shift()` => removes element from start
- `arr.pop()` => removes element from end

*Object & Constructors=>*
- An object is combination of many properties and property is made of key and value
- `let user ={rollno:value,name:value,..,adress;value` => eg of object
- Property -value in an object can be primitive and non primitive data type 
- To delete a property from an object use `delete object.property` 
- 
- Constructor is used to create  multiple objects with say same skeleton or structure like for 1000 employees data in a company.
```JavaScript
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
- The `this` keyword points or refers to the object from which the method was called.(like a parent & child stuff in python oops)
- `new` keyword is used to create a new instance of a function or object or constructor function(kind of a new datatype)

*Prototypes*
- `object.prototype.method/property` => is used to create a method in the prototype of the  object without having to write in the object itself and in this case the instances that are created also don't get  a copy seperately for each of them for any method created like this as the compiler pulls this from prototype directly.
- All javascript objects inherit their properties from protoypes(basically the parent of an object or like the base from which it was made).If a value/method/function is not found in object then the compiler checks for it in it's prototype.
```JavaScript
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

*Call Backs and Functions* 
- A function passed as an argument to another function is called call back function.(The one passed as argument which is executed some time in the future)
- A function is called as first class object i.e it can be stored in var,passed as an argument,returned from another function(due to closure i.e all the data of a function and it's surroundings are stored in heap which makes this possible in JS)
```JavaScript
function a(x){
return x*x
}
function b(a,x){                       /*here the a func works as a callback*/
let r = a(x);
return r+10
}
```

*Filter,reudce,map,find,findIndex,forEach*
- All of these methods take a callback function as input.
- `arr.filter(func)` => is used to store the pass each and every of an array through a function(filter only not modify) and all the returned values are stored in a new array.
- If the return statement in single then use arrow(==>)function 
- `arr.map(func)` => this can be used to modify each & every element of an array with the help of some function and filtering works but it returns an array of boolean values as of whether the value passed the filter or not
- `arr.forEach((element,index)==>callback function)` => used to iterate an array 
- `arr.find(ele==> ele===x)` => is used to search for an element in array.
- `arr.findIndex(func)` => is used to find the index of a element in array.
- `arr.reduce(func)` =>  is used to reduce an array to single element i.e use cases include max,min,sum of an array.Reduce works by doing a single operation sequentially or continously on all elements of array.(a[0]+a[1]+a[2]..) carrying the result for next one
```JavaScript
  let arr=[1,2,3,4]
  let s=arr.reduce((s,e)=>s+e) /*element is added to the sum*/
  console.log(s)      /*Output:10*/
```

*Export & Import*
- `export variable /{variables}`=> used to make variables ready to be imported
- `import {variables} from filepath`=> to import variables from a file
- `export default var` => is used to export and the diff is the importing file can use any name for var unlike before `import x from file` like this.

*Unpacking*
- `let [a,b,c..]=array`=> unpacks array elements to a,b,c..
- `let {x,y}=dict` => use x,y(only keys in obj) the values of x & y are assigned to those

*Promises*
- A promise in JS is used to implement asynchronous operations.They are basically used to save time used by some heavy tasks kind of deligating task to some others.Like when one is happening the rest of program continues it work and when all the other stuff done the thing returned by promise is accepted.
- A promise can be created by ` new Promsie((fullfilled,rejected)=>{fucntion code}` we need to pass both `fullfill(msg)` & `rejected(msg)` in the function code.
- A promise can be accepted by `prminstance.then().catch()` => `.then()`  is used to receive  in case of promise being fullfilled and `.catch()` is used to case of promise being rejected.
- Chain of promises is possible and they can be accepted by chain of `.then().then()...` 
- ![[Pasted image 20240810234138.png]]
- `fetch(website)` => returns json data in the form of a  promise .
- `.json()` => parses the promise to JSON

*DOM(Data Object Model)*
- ![[Pasted image 20240811163212.png]]
- DOM is used to render the  html elements on the screen 
- Every browser contains a css parser which applies css styles to website on a high level by taking elements from DOM
- Every browser also contains a JS engine works with the help of DOM
- `document.head` => is used to access the head of a html page in JS(in which html page the js file was included/linked)
- `document.body`=> to access the body of the document
- `document.getElementById(id)` => is used to access an element by id
- `document.getElementsByTagName(tag)`=> to access all the elements with a tagname
- `document.querySelector(id/class/tag)`=>("#" for id),("." for class) used to access elements by any of 3.It returns only the first match
- `document.querySelectorAll()`=> used to access all matches
- The text of selected elements can be changed by `element.textContent` property and the css properties can be changed by accessing `style` property 
```JavaScript
let heading = document.querySelector(".heading")
heading.textContent = "hello"

heading.style.color = "red"
heading.style.backgroundColor="black"
```
- Elements can be made interactive using `element.addEventListener(event,function)`
- There are many events like click,mouseover ...etc
- Elements attribute can also be modified.like `img.src` or something else
- `.innerHTML` => is used to add elements to the html elements like div,body,head we can directly write html inside of " "
```JavaScript
let div = document.querySelector(".main")
div.innerHTML = '<h2>heading2</h2>'
```
- `document.create(tagname)` => creates a new element of that tag in the document.
- `.appendChild(element)` => is used to append some elements to some other element as a child
- 