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
