# ModernJavaScript
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

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Function Declarations, function expressions, IIFE - Immediately invokable function expressions, property methods

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
Make an expression by putting a function inside parenthesis, and do not forget to put () after expression

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
