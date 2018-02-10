# Modern JavaScript
Learning pure javascript/ vanilla javascript.[Newest features in JS] ES2015 or ES6

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Variables and declaration

<hr>

There are 3 possible keywords to define a variable
1. var
2. let
3. const (introduced in ES6)

<strong>Important points [Variables]:</strong><br>
1. Variables can include letters, numbers, _, $
2. Variables cannot start with number
3. Variales starting with $ are ususally used in jQuery or DOM manipulation
4. Variables starting with _ are ususally private variables
5. In case of multiword variables, use camel case(e.g. var firstName), in case of object oriented programming, use pascal case(e.g. var FirstName)
6. let keyword works very similar to var
7. variables defined with const cannot be reassigned. They can be mutated but cannot be reassigned (in case of reference datatypes -> array, objects)


- let gives block scope local variable whereas var provides global scope
- Hence, with let we can limit the scope of a variable

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Datatypes

<hr>

**JavaScript is a loosely typed or dynamic language. That means you don't have to declare the type of variable ahead of time**

1. Primitive Datatypes
2. Reference Datatypes
<br>

<table>
  <tr>
    <td><strong>Primitive Datatypes</strong></td>
    <td><strong>Reference Datatypes</strong></td>
  </tr>
  <tr>
    <td>
      <ul>
         <li>The data is accessed by its value</li>
        <li>Stored directly in the location variable accessess</li>
        <li>Stored on the stack</li>
      </ul>
    </td>
    <td>
     <ul>
        <li>Accessed by reference</li>
        <li>Objects are stored on heap</li>
        <li>A pointer to a location in memory</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <ul>
        <li>String</li>
        <li>Number(includes int, float)</li>
        <li>Boolean</li>
        <li>Null</li>
        <li>Undefined</li>
        <li>Symbols(ES6)</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>Arrays</li>
        <li>Object literals</li>
        <li>Functions</li>
        <li>Dates</li>
      </ul>
    </td>
  </tr>
</table>

<br>

JavaScript is dynamically typed language. That means same variable can hold multiple types. Types are associated with values not variables.

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Array and array methods

<hr>

```
//Create Arrays
const numbers = [43, 56, 33, 23, 44, 36, 5];

//Other way of creating arrays
const numbers2 = new Array(22, 45, 33, 76, 54);

let val;

//Get array length
val = numbers.length;                                     //Output: 7

//Check if it is an array -> check by array object
val = Array.isArray(numbers)                              //Output: true

//Get single value from array
val = numbers[3];                                         // Output: 23

//Insert into array
numbers[2] = 100;                                         //Output:  [43, 56, 100, 33, 23, 44, 36, 5]

//Find index of value
val = numbers.indexOf(36);

/*
* MUTATING ARRAYS
*/


//Add on to the end of array
numbers.push(250);                                      //Output:  [43, 56, 100, 33, 23, 44, 36, 5, 250]

//Add on to the front of array
numbers.unshift(120);                                   //Output:  [120, 43, 56, 100, 33, 23, 44, 36, 5, 250]

//Take off from end
numbers.pop();                                          //Output:  [120, 43, 56, 100, 33, 23, 44, 36, 5]

//Take off from front
numbers.shift();                                         //Output:  [43, 56, 100, 33, 23, 44, 36, 5]

//Splice values splice(i, n) => At position i, remove n elements
numbers.splice(1, 1);                                      //Output:  [43, 100, 33, 23, 44, 36, 5]
numbers.splice(1, 3);                                      //Output:  [43, 44, 36, 5]

//Reverse the array
numbers.reverse();                                        //Output: [5, 36, 44, 43]

//concatenate arrays
numbers.concat(numbers2)                                  // Output: [5, 36, 44, 43, 22, 45, 33, 76, 54]

//Sorting arrays in ascending order -> Use the compare function
numbers.sort(function(x, y){
  return x - y;
})


//Sorting arrays in descending order -> Use the compare function
numbers.sort(function(x, y){
  return y - x;
})

//Find
function under50(num) {
  return num < 50
}

val = numbers.find(under50)

```


<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Template literals/strings (ES6 feature)

<hr>

Backticks are used and to print a variable value, ${variable} is used.


<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Function Declarations and expressions, IIFE, property methods

<hr>


### Function expressions

Putting a function as a variable assignment.
Usually a named variable and anonymous function.
Do not forget to put ; at the end because it is a variable.

```
const square = function(x) {
  return x*x;
};

console.log(square(2));
```

### IIFE - Immediately invokable function expressions

A function you declare and run at the same time.
Make an expression by putting a function inside parenthesis, and do not forget to put () after expression.
It executes immediately after it’s created.

```
(function(){
  console.log('IIFE is running!');
})();
```

```
(function(name){
  console.log('Hello' + name);
})(name);
```

When you use an IIFE you don't pollute the global scope. All variables that you define inside of an IIFE can not be accessed outside of it. This is the main benefit.


### Property methods

We can put functions inside of objects too.
When a function is put inside of an object, it is called method.

```
const todo = {
  add: function() {
    console.log('Add to do');
   },
   edit: function(id) {
    console.log(`Edit todo ${id}`);
   }
}

todo.add();
todo.edit(2);

// You can also define functions for this object outside of it.
todo.delete = function() {
console.log('Delete todo')

todo.delete();

```

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Window Object

<hr>

<ul>
  <li>Window is the global object in client-side javascript. </li>
  <li>Browser is the global environment in client-side javascript whereas your computer machine is the enviornment in server-side javascript.</li>
  
</ul>

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Block scope with let & const

<hr>

<ul> 
  <li>var is a function scope declaration</li>
   <li>Block scope => Anything that is wrapped in curly braces { }</li>
   <li>let & const have block level scope and var has a function scope
</li>
</ul>

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) DOM Manipulation & Events

<hr>

## What is DOM?

<blockquote>Document Object model is a structured representation of an HTML document.</blockquote>

<ul>
  <li>It can be thought of as a tree of nodes/elements(any of the HTML tags) created by the browser</li>
  <li>JavaScript can be used to read/write/manipulate the DOM elements/nodes</li>
  <li>DOM is object oriented that means each node has its own set of properties and methods that we can add, change, remove</li>
  <li>Browser gives us <strong>window</strong> object and inside that we have <strong>document</strong> object.</li>
  <li><strong>Window Object</strong> -> Global object of browser enviornment</li>
  <li><strong>Document Object</strong> -> Property of window object</li>
</ul>  

## Properties of Document Object (Attributes of Document Object)

```
//Get HTML collection from entire document
document.all

//Get head
document.head

// Get doctype
document.doctype

//Get domain -> gives loopback address if you are on localhost
document.domain

//Get contentType
documnt.contentType;

```

```
/*
* Selecting the stuff without using selectors (Not recommended)
*/

// Get all forms on the page
document.forms;

// Get scripts
document.scripts;

// Get links
document.links;

// Get images
document.images;



```


## DOM Selectors 

<blockquote>These are document object methods that allow us to pull the things from DOM and we can do different things with elements</blockquote>

There are two types of DOM Selectors
1. Single element selectors -> Allow us to grab a single element(either by id or class)
2. Multiple element selectors -> Allow us to grab all the elements(by class)

<br>

### DOM Selectors for Single Elements

```
document.getElementById();
document.querySelector();
```


<strong>document.getElementById() -> Selects the element by id</strong>
<table>
   <tr>
      <td><strong>DOM Selector</strong></td>
    <td><strong>Working</strong></td>
  </tr>
  <tr>
    <td>document.getElementById('name-of-id')</td>
    <td>Selects the elements by id</td>
  </tr>
  <tr>
      <td>document.getElementById('name-of-id').id</td>
    <td>Get name of id from selected element by id</td>
  </tr>
   <tr>
      <td>document.getElementById('name-of-id').className</td>
    <td>Get name of class from selected element by id</td>
  </tr>
   <tr>
      <td>document.getElementById('name-of-id').style.CSS_PROPERTY</td>
    <td>Change styling (Used specifically for dynamic functionalities)</td>
  </tr>
   <tr>
      <td>document.getElementById('name-of-id').textContent</td>
    <td>Change Content</td>
  </tr>
  <tr>
      <td>document.getElementById('name-of-id').innerText</td>
    <td>Change Content</td>
  </tr>
  <tr>
      <td>document.getElementById('name-of-id').innerHTML</td>
    <td>To innsert HTML when working with DOM, if you want to fetch from some API</td>
  </tr>
</table>  



<strong>document.querySelector() -> Selects the element by anything (Works like jQuery) [More Powerful]</strong>
<table>
   <tr>
      <td><strong>DOM Selector</strong></td>
    <td><strong>Working</strong></td>
  </tr>
  <tr>
    <td>document.querySelector('#name-of-id')</td>
    <td>Selects the elements by id</td>
  </tr>
  <tr>
      <td>document.querySelector('.name-of-class')</td>
    <td>Selects the elements by class</td>
  </tr>
   <tr>
      <td>document.querySelector('h1')</td>
    <td>Get the element itself, selects first h1 element(in case of multiple h1 elements) (Because it is a single element)</td>
  </tr>
   <tr>
      <td>document.querySelector('element').style.CSS_PROPERTY<</td>
    <td>Change style</td>
  </tr>
   <tr>
      <td>document.querySelector('element').textContent</td>
    <td>Change Content</td>
  </tr>
  <tr>
      <td>document.querySelector('element').innerText</td>
    <td>Change Content</td>
  </tr>
  
</table>

<br>
### DOM Selectors for Multiple Elements

<blockquote>Return either HTML Collection or node list which are not arrays but are similar to arrays</blockquote>

```
document.getElementsByClassName('class-name') [Use of plural -> Elements]   GLOBAL SCOPE
document.querySelector('html-element').getElementsByClassName('class-name')  
document.getElementsByTagName('tag')
document.querySelectorAll('any kind of css selector')
```

<strong>Converting HTML collection into array</strong>

```
Array.from(HTML_COLLECTION)
```

<br>

### Traversing the DOM

<blockquote>Dealing with the parents and children of whatever node we select</blockquote>

```
//Get child nodes -> Gives NodeList of all child nodes
.childNodes

// Get children element nodes -> returns HTMLCollection
.children


//Get parentNode
.parentNode
.parentElement

```

```
NodeTypes

1 - Element
2 - Attribute (deprecated)
3 - Text node
8 - Comment
9 - Document itself
10 - DOCTYPE
```
<br>

### Creating elements or DOM elements from scratch

```
// Create element
const li = document.createElement('li');

// Add a class
li.className = 'collection-item';

// Add id
li.id = 'new-item';

// Add attribute
li.setAttribute('title', 'New Item');

// Create text node and append
// Creating textnode -> document.createTextNode('some-text')

li.appendChild(document.createTextNode('Hello World'));

// OUTPUT
<li class="collection-item" id="new-item" title="New Item">Hello World</li>


//Append li as a child to ul (Consider that ul has a class-> ul.collection)
document.querySelector('ul.collection').appendChild(li)
```

<br>

### Removing and replacing elements in DOM

<blockquote>How to remove elements from DOM, how to replace eleemts in DOM, how to work with classes and attributes</blockquote>

<strong>REPLACE ELEMENT</strong>

```
/*
Replace heading h1 by h2
*/


// Create element
const newHeading = document.createElement('h2');

// Add id
newHeading.id = 'task-title';

// New text node
newHeading.appendChild(document.createTextNode('NEW HEADING'));

// Get the old hading
const oldHeading = document.getElementById('task-title');

// Now fetch the parent of old heading, suppose that class of the parent element is card-action
const cardAction = document.querySelector('.card-action');

// Replace
cardAction.replaceChild(newHeading, oldHeading);

```
<br>
<strong>REMOVE ELEMENT</strong>

```
const lis = document.querySelectorAll('li');
const list = document.querySelector('ul');

// Remove list item
lis[0].remove();      // Removes the first list item

// Remove child elements
list.removeChild(lis[3]);

```

<br>
<strong> CLASSES AND ATTRIBUTES</strong>

```
// Get attributes
.getAttribute('name-of-attribute');

// Set attribute
.setAttribute('name-of-attribute', 'Value you have to set');
```
<br>

### Event Listeners and the Event Object

<blockquote>Basically used for interaction with UI, webpage</blockquote>

<strong>Adding event listeners</strong>

```
// First we have to select
document.querySelector(OBJECT).addEventListener('ACTUAL EVENT', function(){
  console.log('Hello');
});

// To prevent default behavior,pass event object in function() and prevent the default behavior by calling preventDefault()
document.querySelector(OBJECT).addEventListener('ACTUAL EVENT', function(e){
  console.log('Hello');
  
  e.preventDefault();
});

// OR we can use named function instead of unamed function
document.querySelector('.some class name').addEventListener('click', onClick);

function onClick(e) {
  console.log('Clicked');
  
  // Event target element
  e.target;
  e.target.id;
  e.target.className;
  e.target.classList;
  
  e.target.innerText = 'Hello World';
  
  e.type;
  e.timeStamp;
  
  // co-ordinates of an event relative to window
  e.clientY;
  
  e.offsetX;
  
  // Event type
}

```

### Event Bubbling and Delegation

<strong>Event Bubbling:</strong>
It is bubbling up of events through the DOM.
When an event happens on a particular element of a DOM, it will bubble up through its parents.

<strong>Event Delegation</strong>
It is the opposite of event bubbling.
It is where we put event listener on one of the parents and then we use logic inside event handler to target the element that we actually want (for that particular event).
<br>
<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) LocalStorage and SessionStorage

<hr>

<blockquote>What you set as a value, has to be a string.</blockquote>

<table>
  <tr>
    <td>Object to String conversion</td>
    <td>Stringification</td>
  </tr>
  <tr>
    <td>String to object conversion</td>
    <td>Parsing</td>
  </tr>
</table>

Difference between localStorage and sessionStorage is the localStorage will stay until you manually clear out through settings or through a program and sessionStorage will go away/leave once you close the browser or when the session ends. 

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Objected Oriented JavaScript - ES5 & ES2015

<hr>

### Constructor and 'this' keyword
- To create multiple instances of certain of of objects, you need a constrcutor
- *this* keyword refers to current instance of object
- When *this* is in the global scope, it pretends to Window object

### Prototypes - ES5
- Each object in JS has a prototype and prototype is an object itself
- All objects inherit their properties and methods from prototype

### Prototypal Inheritance - ES5
- One object type inherit from another object type

### Creating objects using Object.create -ES5
- Objects can be created using Object.create() and you can pass the prototype inside Object.create(). You can add properties to these objects and with these object you can also access the method of a prototype. This doesn't involve constructors and inheriting prototypes

<hr>

```
With ES6, we can use classes
```

### ES6 Classes
- ES6 is compatible with all modern browsers
- We can create classes with ES6
- We can perform inheritance in ES6. We can extend existing class using extends keyword i.e. we can create subclasses. 

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Asynchronous JavaScript, AJAX, Fetch API

<hr>

### Ways to handle async code is 
- Callbacks
- Promises
- Async/Await

### AJAX
- AJAX stands for Asynchronous JavaScript and XML
- It is a technology that is used to send and receive data from client and server asynchronously and it is done behind the scenes, without the webpage being explicitly reloaded
- Server can return data is XML/JSON format. Nowadays, JSON is extensively used in the place of XML in AJAX. AJAX can also work with plain text

### XmlHttpRequest (XHR) object
- Core technology in AJAX
- It is provided by the browsers JS environment
- Its methods transfer data between client and server
- It can be used with other protocols other than HTTP
- It can work with XML, JSON, plain text

### API
- API is Application Programming Interface
- Contract provided by one piece of software to another
- API consists of structured request and response

### REST APIs
- REST stands for Representational State Transfer
- It is an architecture style for desiging networked applications
- REST API relies on stateless, client server protocol, almost always HTTP
- It treats server objects as resources that can be created or destroyed. Example of server side objects could be a blog post which is stored in the database

### HTTP Requests

<table>
    <tr>
      <td><strong>GET</strong></td>
      <td>Retrieve data from the specified resource</td>
    </tr>
    <tr>
      <td><strong>POST</strong></td>
      <td>Submit data to be processed to a specified resource</td>
    </tr>
    <tr>
      <td><strong>PUT</strong></td>
      <td>Update a specified resource</td>
    </tr>
    <tr>
      <td><strong>DELETE</strong></td>
      <td>Delete a specified resource</td>
    </tr>
    <tr>
      <td><strong>HEAD</strong></td>
      <td>Same as GET but does not return body</td>
    </tr>
    <tr>
      <td><strong>OPTIONS</strong></td>
      <td>Returns the supported HTTP methods</td>
    </tr>
    <tr>
      <td><strong>PATCH</strong></td>
      <td>Update partial resources</td>
    </tr>
  </table>
  
  ### API Endpoints
  
  API endpoints are the URLs that are used to access certain things
  
  
  ### Callback functions
  
  - Callback is a function that is passed in as a parameter to another function and run(or **called**) inside function body
  - We can have synchronous and asynchronous callbacks
  
  ### ES6 Promises
  
  - They are alternative to callbacks.Alternative way of handling asynchronous operations.
  - When you get a response from a promise, you have to use .then()
  - If there is some kind of error, then we can do .catch()

### Async/Await in ES7 or ES2016

  - We add a keyword *async* at the begining of a function and that makes a function to return a promise
  
  ```
  async function myFunction(){
    const promise = new Promise((resolve, reject) => {
      setTimeout(() => resolve('Hello'), 1000);
    });
    
    const res = await promise; // Wait until promise is resolved
    
    return res;
  }
  
  myFunc() {
    .then(res => console.log(res));
  }
  ```
  
  
  ```
  async function getUsers() {
    // Await response of the fetch call, fetch call returns a promise
    const response = await fetch('https://jsonplaceholder.typicode.com/users');
    
    // Only proceed once the promise is resolved
    const data = await response.json();
    
    // Only proceeed when second promise is resolved
    return data;
  
  }
  
  getUsers().then(users => console.log(users));
  ```

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Error handling and regular expressions

<hr>

### Error handling with Try..Catch

- Try block lets you write some code and test for errors and Catch block lets ys handle that error if there is any.
- We can also throw our own error.

### Regular Expressions

- Regular Expression is basically used to describe pattern of characters
- It is commonly used for
  - Pattern Searching 
  - Pattern Matching
  - Validation
  - Pulling information out of body of text or body of characters
- We can use flags in regular expression
  - flag i is used to make a regular expression case insensitive
  - flag g is used for global search (searches all instances of the word)
 
### Different functions in JavaScript that are used to evaluate the Regular Expressions

1. **exec()** => returns the result in an array if there is a match, otherwise it returns null
2. **test()** => returns true if there is a match otherwise it returns false
3. **match()** => returns result array or null
4. **search()** => returns the index of first match, otherwise returns -1
5. **replace()** => returns new string with some or all matches of a pattern

### Metacharacter Symbols

- Use of symbol ^ before => Must start with
- Use of Symbol $ after => Must end with
- Use of symbol . => Matches any ONE character
- Use of symbol * => Matches any character 0 or more
- Use of Symbol ? => Optional character. It is put after the optional character
- Use of symbol / => EScape character

```
/^h/ => Must start with h (Case sensitive)
/^h/i => Must start with h (Case insensitive)
/n$/ => Must end with n
/^hello$/i => Must begin with h and end with o
/h.llo/i; =>  Matches any ONE character
/h*llo/i; =>  Matches any character 0 or more
/gre?a?yi* => This means e is optional and a is optional

To use ? as a literal, we need to use escape character, i.e. prefix the literal with back slash \ (example if I want =>  grey?)
/gre?a?y\?/


```

### Character Sets and Quantifiers

```
Brackets [] => Character sets
Braces {} => Quantifiers
Parentheses () => Grouping

```

### Shorthand Character Classes

If we we want to search for a word character or digit or white space character shorthand character classes can be used

```
/\w/       // Word character - Alphanumeric(any letter or number) or underscore
/\w+/      // + => one or more
/\W/       // Non-word character
/\d/       // Match any digit
/\d+/      // Match any digit 0 or more times
/\D/       // Match any non-digit
/\s/       // Match whitespace character
/\S/       // Match non whitespace character
/\b/       // word boundary


```

### Assertions

Similar to conditions<br>

```
/x(?=y)/    // Match x only if it is followed by y
/x(?!y)/            // Match x only if it is not followed by y

```

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Other new features in ES2015+

<hr>

### Iterators and Generators

- Iterators and generators are used to iterate through something
- You can call part of a return, pause it and then call next return
- Iterators are advanced loops that can be paused and generators are the functions that can be paused and return multiple values called yield values
- Syntax for Generator =>

```
  function* functionName() {
  
 }
 
 ```
 
 ### Symbols
 
 - Primitive data types in JavaScript
 - Every symbol is unique. Main purpose is uniqueness. They are used for object property identifiers
 - We can create unique object keys using Symbols
 - Symbols are not enumerable in for..in loop
 - Symbols are ignored by JSON.stringify()
 
 ### Destructuring
 
 - Gives easy way to assign variables and extract variables from arrays and objects
 
 ### Maps
 
 - Object structure that holds key-value pair and any type (object/obejct reference type/primitive) can be used as a KEY or VALUE
 
 
 ### Sets
 
 - Store unique values of any type
 
 <hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) JavaScript Patterns

<hr>

### What are JavaScript Patterns?

- Pattern is a re-usable solution that can be applied to occuring problems in software design.
- Pattern can be thought of as a programming templates or specific way for writing codes
- Situations vary significantly. Factory pattern and prototype pattern are used for object creation. The module pattern and its variations are used for overall structure. MVC is complete software design pattern.

<br>

**JavaScript Patterns**

<table>
  <tr>
    <td><strong>Patterns<strong></td>
    <td><strong>Description<strong></td>
  </tr>
  <tr>
    <td>Module</td>
    <td>Used for overall structure, it breaks the code into modules so that we can have private and public variables and functions</td>
  </tr>
  <tr>
    <td>Reavling Module Pattern</td>
    <td>Used for overall structure, it breaks the code into modules so that we can have private and public variables and functions</td>
  </tr>
  <tr>
    <td>Singleton</td>
    <td>Variation of Module pattern, where we can create an instance of an object</td>
  </tr>
  <tr>
    <td>Factory</td>
    <td>This pattern is used to create many objects</td>
  </tr>
  <tr>
    <td>Observer</td>
    <td>This pattern allows us to subscribe and unsubscribe to events</td>
  </tr>
  <tr>
    <td>Mediator</td>
    <td>It has central mediator</td>
  </tr>
  <tr>
    <td>State</td>
    <td>This pattern allows us to have certain state in the application and we can change the state</td>
  </tr>
</table>


<br>

ES6 has introduced actual modules in the JavaScript => we can use separate files to export modules which are nothing but custom pieces of code and import them to new file. But that is not still supported in modern browser. So in order to work that, we have to use compiler like babel along with module loader like webpack.

<br>

### Module Pattern

- Module pattern allows us to break the parts of the code into self-contained modules with private properties and methods
- Module is going to be IIFE (It runs right away)

```
// Basic structure or blueprint for module pattern

(function() {
    // Declare private variables and functions which will not be accessible outside of the module

    return {
        // Declare public variables and functions which will be accessible outside of the module
    }
})();

```


### Revealing Module Pattern

- This is very similar to Module pattern
- Main difference is instead of returning our own public function, we map an object literal to the private funcions you want to reveal from your module.

### Singleton Pattern

- Singleton pattern is the manifestation of module pattern
- Singleton object is an immediate annonymous function and it can only return one instance of an object at a time
- Like module pattern, it maintains the private reference, that nothing can be accessed from outside

### Factory Pattern / Factory Method

- It is used to create multiple objects
- It is a way of creating of interafce for creating objects but we can let subclasses to decide which classes to instantiate
- Factory pattern is used in applications to manage, maintain, manipulate collection of objects that are different but have same characteristics
- This pattern is good when you have different objects but they share lot of properties and methods

### Observer Pattern

- This is the behavioral pattern allows us to subscribe and unsubscribe to certain events or certain functionalities
- It can be used to notify DOM if certain elements are needed to be updated
- AngularJS relies heavily on this pattern through event management with scope

### Mediator Pattern

- This is the behavioral pattern and idea is to have a mediator which is an interface for communicating with callees which are mediated objects

### State Pattern

- This is also bheavioral pattern. The state can be changed throughout our script.


