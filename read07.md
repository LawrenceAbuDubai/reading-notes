# Functions

In JavaScript, functions are one of the most basic building components. In JavaScript, a function is comparable to a procedure—a series of instructions that performs a task or calculates a value—but a process must accept some input and return an output with some evident relationship between the input and the output to qualify as a function. You must define a function someplace in the scope from which you want to call it before you may use it.

Defining functions
Function declarations
A function definition (also called a function declaration, or function statement) consists of the function keyword, followed by:

The name of the function.
A list of parameters to the function, enclosed in parentheses and separated by commas.
The JavaScript statements that define the function, enclosed in curly brackets, {...}.
For example, the following code defines a simple function named square:

function square(number) {
  return number * number;
}
Copy to Clipboard
The function square takes one parameter, called number. The function consists of one statement that says to return the parameter of the function (that is, number) multiplied by itself. The statement return specifies the value returned by the function:

return number * number;
Copy to Clipboard
Primitive parameters (such as a number) are passed to functions by value; the value is passed to the function, but if the function changes the value of the parameter, this change is not reflected globally or in the calling function.

If you pass an object (i.e., a non-primitive value, such as Array or a user-defined object) as a parameter and the function changes the object's properties, that change is visible outside the function, as shown in the following example:

function myFunc(theObject) {
  theObject.make = 'Toyota';
}

var mycar = {make: 'Honda', model: 'Accord', year: 1998};
var x, y;

x = mycar.make; // x gets the value "Honda"

myFunc(mycar);
y = mycar.make; // y gets the value "Toyota"
                // (the make property was changed by the function)
Copy to Clipboard
Function expressions
While the function declaration above is syntactically a statement, functions can also be created by a function expression.

Such a function can be anonymous; it does not have to have a name. For example, the function square could have been defined as:

const square = function(number) { return number * number }
var x = square(4) // x gets the value 16
Copy to Clipboard
However, a name can be provided with a function expression. Providing a name allows the function to refer to itself, and also makes it easier to identify the function in a debugger's stack traces:

const factorial = function fac(n) { return n < 2 ? 1 : n * fac(n - 1) }

console.log(factorial(3))
Copy to Clipboard
Function expressions are convenient when passing a function as an argument to another function. The following example shows a map function that should receive a function as first argument and an array as second argument:

function map(f, a) {
  let result = []; // Create a new Array
  let i; // Declare variable
  for (i = 0; i != a.length; i++)
    result[i] = f(a[i]);
  return result;
}
Copy to Clipboard
In the following code, the function receives a function defined by a function expression and executes it for every element of the array received as a second argument:

function map(f, a) {
  let result = []; // Create a new Array
  let i; // Declare variable
  for (i = 0; i != a.length; i++)
    result[i] = f(a[i]);
  return result;
}
const f = function(x) {
   return x * x * x;
}
let numbers = [0, 1, 2, 5, 10];
let cube = map(f,numbers);
console.log(cube);
Copy to Clipboard
Function returns: [0, 1, 8, 125, 1000].

In JavaScript, a function can be defined based on a condition. For example, the following function definition defines myFunc only if num equals 0:

var myFunc;
if (num === 0) {
  myFunc = function(theObject) {
    theObject.make = 'Toyota';
  }
}
Copy to Clipboard
In addition to defining functions as described here, you can also use the Function constructor to create functions from a string at runtime, much like eval().

A method is a function that is a property of an object. Read more about objects and methods in Working with objects.

Calling functions
Defining a function does not execute it. Defining it names the function and specifies what to do when the function is called.

Calling the function actually performs the specified actions with the indicated parameters. For example, if you define the function square, you could call it as follows:

square(5);
Copy to Clipboard
The preceding statement calls the function with an argument of 5. The function executes its statements and returns the value 25.

Functions must be in scope when they are called, but the function declaration can be hoisted (appear below the call in the code), as in this example:

console.log(square(5));
/* ... */
function square(n) { return n * n }
Copy to Clipboard
The scope of a function is the function in which it is declared (or the entire program, if it is declared at the top level).

Note: This works only when defining the function using the above syntax (i.e., function funcName(){}). The code below will not work.

This means that function hoisting only works with function declarations—not with function expressions.

console.log(square)    // square is hoisted with an initial value undefined.
console.log(square(5)) // Uncaught TypeError: square is not a function
const square = function(n) {
  return n * n;
}
Copy to Clipboard
The arguments of a function are not limited to strings and numbers. You can pass whole objects to a function. The showProps() function (defined in Working with objects) is an example of a function that takes an object as an argument.

A function can call itself. For example, here is a function that computes factorials recursively:

function factorial(n) {
  if ((n === 0) || (n === 1))
    return 1;
  else
    return (n * factorial(n - 1));
}
Copy to Clipboard
You could then compute the factorials of 1 through 5 as follows:

var a, b, c, d, e;
a = factorial(1); // a gets the value 1
b = factorial(2); // b gets the value 2
c = factorial(3); // c gets the value 6
d = factorial(4); // d gets the value 24
e = factorial(5); // e gets the value 120
Copy to Clipboard
There are other ways to call functions. There are often cases where a function needs to be called dynamically, or the number of arguments to a function vary, or in which the context of the function call needs to be set to a specific object determined at runtime.

It turns out that functions are themselves objects—and in turn, these objects have methods. (See the Function object.) One of these, the apply() method, can be used to achieve this goal.