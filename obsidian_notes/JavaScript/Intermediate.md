# String Manipulation Methods in JS
- `str.length`-> returns the length of string.
- `str.indexOf(substr)`-> returns the index of first occurrence of substring in the string.
- `str.lastIndexOf(substr)` -> returns the index of last occurrence of substring in the string.
- `str.slice(start,end)`->returns the part of string starting from start and upto end excluding the end index.
- `str.substr(start,len of str to return from start)` -> returns a substring of length specified from the stat.This function is deprecated now.
- `str.replace(substring,replacement string)` -> replaces substring with replacement string in string and returns the modified string but does not actually affect the original string.
- `str.split(delimiter)`-> delimiter refers to the value at which we want to split the string.
- `str.trim()`->trims ou the extra spaces.
- `str.toUpper();str.toLower()` -> converts the string to Upper case and Lower case respectively.
# Numeric  and List methods in JS
 - `parseInt(str)` -> converts a string into number and works even if something gibberish is present after the number like "42px" or "42pxhfjhfs" but not before or in the middle.
 - `parseFloat(str)` -> converts a string to float type and works similar to parseInt and both of these functions are **global function**.
 - Array is created by `[]` which is nothing but a list.
 - `arr.push(x)` -> pushes element x to end of array 
 - `arr.pop()` -> pops the end element of an array and returns the popped element.
 - `arr.shift()`->removes the element from front and returns it.
 - `arr.unshift(x)` -> adds the element at the front of the array.
 - `arr.concat(arr2)` -. returns a combined array of array and array2.
 - `arr.forEach(function)` -> takes each and every element of the array and performs the passed function on them. It works on the principle of callback which refers to passing a function as a parameter to another function where we can call it indirectly.
# Classes in JS
 - **Classes** are used or created so that the object/group of functions can be reused again.It's like creating a blue print of an object but the object is actually created when u call it i.e an instance of class is created as object every time we call it.
 - `Class name{...}` -> creates a class with name.
 - `constructor(paramters)` -> lets u pass the parameters directly to the class to use them in the class scope.
 - To use the parameter somewhere else in the class store the value in `this.varname=parameter;`
 - `static function(){ }` -> creates a unique type function that can be called directly on the class itself rather than calling it on the object or instance of class.
# JSON(JavaScript Object Notation) 
- `JSON.parse(str)` -> converts the string to object and returns the object.
- `JSON.stringfiy(obj)` -> converts the object to string format.
# Objects in JS
- `Object.keys(object)` => returns an array of keys.All the **Object** methods and the class **Object**  is a global class.
- `Object.values(object)` => returns an array of values.
- `Object.entries(object)` => returns a array of arrays where each array is an element/entry of the object containing both **[key,value]**
- `obj.hasOwnProperty("property")` => returns true if the property is present in keys array.
- `Object.assign({},object,{new property: value});` => adds a new {key,value} to the object.
# Synchronous and Asynchronous functions,Promises,Callbacks  in JS
 - ![[Pasted image 20240527155439.png]]
 - To make a function synchronous and make the thread kinda of sleep we can use **busy waiting** method.
 - `setTimeout();fs.readFile()` => are asynchronous functions in nature.Where **setTimeout** is a **web api**.
 - **Callback** work on the principle of queue i.e FIFO principle the first came callback gets executed first.
 - **Promise** is still a call back but syntactically sugar coated(better).
 - `Promise(function(xfunc){ xfunc();};`=> syntax to create a basic promise.Where **xfunc** refers to **resolve** function.
 - `promise.all([p1,p2,p3..]).then(value)`
 - `fs.readFile(filename,encoding,function(err,data){})` => is used to read data from file.
 - To use `fs` => use `const fs=require("fs");` 
- **Creating a New Promise** =>new Promise creates a new promise object.The promise constructor takes an executor function as its argument. This executor function is called immediately by the Promise implementation, passing resolve and reject functions to it.
- **Executor Function:** The executor function contains the asynchronous operation (in this case, fs.readFile).resolve and reject are functions that change the state of the promise:**resolve(value)**: Marks the promise as fulfilled and passes value to the fullfillment handler. **.reject(reason)**: Marks the promise as rejected and passes reason (an error) to the rejection handler
- .In this case the handler is `function.then(fullfillment handler function )` =>this is used to handle data returned when the promise is fullfilled.
- `.catch(onRejected)`=>**Purpose:** Specifically handles the rejection of a promise. It is a shorthand for .then(null, onRejected).**Arguments**:onRejected: A function that is called when the promise is rejected. It receives the error reason as an argument.
- `.finally(onFinally)`=> **Purpose:** Executes a function when the promise is settled (either fulfilled or rejected). It allows you to run cleanup or finalisation code regardless of the promise's outcome.**Arguments**:onFinally: A function that is called when the promise is settled. It does not receive any arguments.
- ![[Pasted image 20240527193933.png]]
- `async function name(){ let value=await function() // async in nature;}` =>this on a high level convert the `Promise {data}` to just `data` .This internally or in the background does the same work as promises and callbacks but it's more cleaner and readable.So it's more preferable to use.
- `Node.js` => is a runtime which means it can run javascript.
# Creating a HTTP server in JS
- On a high level http is a protocol that let's frontend communicate with the backend and vice versa.
- ![[Pasted image 20240528233139.png]]
- ![[Pasted image 20240528233232.png]]
- ![[Pasted image 20240528233930.png]
- ![[Pasted image 20240528233943.png]]
- ![[Pasted image 20240528234133.png]]
- Methods in http protocol generally are **GET,POST,PUT,DELETE**.
- Common **status codes** in http: 
- **200** => everything is ok.
- **404** => Page or route not found.
- **403** => authentication issues.
- **500** => internal server error.
- To create http server we use **express** library.To use the we use `require("express");`
- `express()` => returns a object(app) which can be used to call http methods.
- `app.get()`
- **HTTP** => Hyper Text Transfer Protocol.
# Express 
- To create a basic http server using express first initialise an instance of the express `const express = require("express"); const app = express()`
- To pass the parameter to the backend pass the parameter at the end of route using  **?parameter=value** 
- `app.get(route,range of functions(req,res,next){ code };` => sends data from backend to frontend.
- where **next** transfers the control from present to next function if range of functions are given.The **last function** we need not mention next parameter.
- functions that has access to server side information like req,res,next are called **middleware functions**.In middle ware functions at the end we need to use `next()` => to makesure flow of computing does not stop.
- If you want to perform a middle ware function in all the http protocols then use `app.use(middleware)`.
- In **app.get()** we can use a function called `res.send(data)` => to send something as a response to frontend when ever someone tries to use **get()**.
- `app.listen(port)` => specifies which port the http server can occupy  or run on .
- `req.query.x` => refers to the frontend sending a request to backend with some query which can be stored in another variable to use in some other functions.
- `arr.map(function)`=> applies the function to each and every element in the array.
- `arr.filter(function)` => filters the values of array based on the function and returns a new array.**Note** => u can only filter the values and return some of them based on condition but not alter the values.
- `arr.find(condition)`=>returns the first element that satisfies the condition in the array.
- To pass the **header parameter** values go to headers section and in that pass parameters and values
- In `app.get("route/:name")` => the value can be accessed by `req.params.name` which will give the values passed after **route/value**.For example route/pavan means i gave the name parameter a value = pavan that i can access with req.params.name
- To use **global catches middleware** use `app.use(func(err,req,res,next));` => here extra parameter is used **err** => error which automatically considers this middleware as global catches without specifically mentioning it.It is used to display error message a bit more neatly.It's also called **error handling middleware**
- **get** => query/parameter is used to pass data
- **post**=> body is used to pass data
- **tokens/cookies**(sensitive information) => passed by headers.
# Zod
- It is a library used to validate data.Schema is created and then input is matched against the created schema and returns **sucess:true,data=[]** or **success;false,expected:dtype,given:dtype** 
- `schema.safeParse(input)` => validates the input against the schema.
- `zod.coerce.dtype()` => creates a schema which converts input to other data type when parsed with an input.`schema.parse(input)
# JWT
- `jwt.sign(payload,secret key)` => returns a token/signature for the given data
- `jwt.verify(token,key)` => verifies if the password is correct and then returns original data.
- **JWT VS SESSION**![[Pasted image 20240607224423.png]]
- `fetch(url)` => an async function that returns the data in the form of promise.
- `Promise.json()` => converts the promise to json format this is also async function and returns the json formatted data.
- ![[Pasted image 20240611194014.png]]
# Mongoose
- Mongoose is a js  library to use mongoDB and it also adds the feature to apply or use schema on the input data
- `mongoose.connect(url)` => connects to the MongoDB
-  `mongoose.model(name,{schema})` => creates a model type of the expected input.
- Example:
```javascript
const mongoose = require("mongoose");
mongoose.connect(
  "mongodb+srv://pavan317b:bmr7oPeC1e40YXiW@cluster0.bzstrz0.mongodb.net/cluster",
);

// creates the model or schema class for the data input like what it's expecting //
const cat = mongoose.model("cat", {
  name: String,
  email: String,
  password: String,
});

// create a new instance of the model to store data//
const kitty = new cat({
  name: "pavan",
  email: "pavan317.b@gmail.com",
  password: "pavan123",
});

//sends the data over to the DB// 
kitty.save().then(() => console.log("Data successfully saved"));
```
- `new modelclass()` => creates a new instance of the model to store data.
- `instance.save()`=> sends the data over to the DB.This is an optional asynchronous function so we can call `.then()` or `await` or just call the functions works too. 
- `instance.findOne({parameter:value})` => checks through the DB if someone is already present with same value for that parameter and returns the first  **entire object** or user it matches with.This is an **asynchronous** function so need to use await or .then()
# DOM
- ![[Pasted image 20240612185245.png]]
- ![[Pasted image 20240612185314.png]]
- ![[Pasted image 20240612185337.png]]
- When a browser compiles or parses a html document it creates a DOM tree and then use it to display the content
```HTML
- <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form id="LoginForm" action="/action_page.php">
        First name: <input type="text" name="fname" value="Donald"><br>
        Last name: <input type="text" name="lname" value="Trump"><br>
        <input type="submit" value="Submit">
    </form>
    <p>Click the "Try it" button to display the number of elements in the form.</p>
    <button onclick="myFunction()">Try it</button>
    <p id="displayspace"></p>
    <script>
        function myFunction() {
            var x = document.getElementById("LoginForm").elements.length;
            var y = document.getElementById("LoginForm").elements[0].value;
            document.getElementById("displayspace").innerHTML = "The number of elements in the form is " + x + " and the first element is " + y;
        }
    </script>
</body>
</html>
```

- `document.createElement("tag")` => creates the html element of specified tag
- `document.body.appendChild(element)` => appends the element to the body.
- `element.innerText=value` assigns the given value as text to the element
- `document.querySelectorAll(value)` =>access the all elements with the value selector we use this generally inorder to edit the styles property of that elemet.
```HTML
- <script>
  function myFunction() {
    var x=document.getElementById("login").elements.length;
    var y=document.getElementById("login").elements[0].value;
    document.getElementById("displayspace").innerHTML="Found"+x+"elements in the form."+"first name entered is: "+y;
    const p=document.createElement("p")
    p.innerHTML="iam arbaz ahmed"
    document.body.appendChild(p)
    const di=document.createElement("div")
    di.innerHTML=p+"iam arbb"
    document.body.appendChild(di)
    
  }
  var paragraph=document.querySelectorAll('p')
  paragraph.forEach(paragraph=>paragraph.style.backgroundColor="red")
</script>
```
 