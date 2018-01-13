# Modern JavaScript
Learning pure javascript/ vanilla javascript.[Newest features in JS] ES2015 or ES6

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Variables and declaration

<hr>

There are 3 possible keywords to define a variable
1. var
2. let
3. cont (introduced in ES6)

<strong>Important points [Variables]:</strong><br>
1. Variables can include letters, numbers, _, $
2. Variables cannot start with number
3. Variales starting with $ are ususally used in jQuery or DOM manipulation
4. Variables starting with _ are ususally private variables
5. In case of multiword variables, use camel case(e.g. var firstName), in case of object oriented programming, use pascal case(e.g. var FirstName)
6. let keyword works very similar to var
7. variables defined with const cannot be reassigned. They can be mutated but cannot be reassigned (in case of reference datatypes -> array, objects)

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Datatypes

<hr>

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

### Prototypes
- Each object in JS has a prototype and prototype is an object itself
- All objects inherit their properties and methods from prototype

### Prototypal Inheritance
- One object type inherit from another object type
