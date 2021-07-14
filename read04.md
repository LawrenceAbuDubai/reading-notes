# JavaScript intro 

JavaScript (JS) is a first-class compiled programming language that is lightweight, interpreted, or just-in-time compiled. While JavaScript is best known as a scripting language for Web pages, it is also used in a variety of non-browser settings, including Node.js, Apache CouchDB, and Adobe Acrobat. JavaScript is a single-threaded, prototype-based, dynamic language that supports object-oriented, imperative, and declarative (e.g. functional programming) programming styles. More information on JavaScript can be found here.

This section focuses on the JavaScript language as a whole, rather than the bits that are particular to Web pages or other host environments. Please visit Web APIs and DOM for information on API specifics to Web pages.

The ECMAScript Language Specification (ECMA-262) and the ECMAScript Internationalization API specification are the JavaScript standards (ECMA-402). The documentation for JavaScript on MDN is based on the most recent draft versions of ECMA-262 and ECMA-402. In addition, descriptions and examples in MDN articles may employ some of the new ECMAScript features that have already been deployed in browsers.

JavaScript is not to be confused with the Java programming language. Oracle's trademarks or registered trademarks in the United States and other countries include "Java" and "JavaScript." The two programming languages, on the other hand, have completely distinct syntax, semantics, and applications.

## Input Output in plain JavaScript

We saw how to alter the DOM to display anything in the first article, and then how to handle user events in the second. This time, we'll look at how to obtain user input and mix it with the other two to make a simple page that can impress you.


<html>
<head>
  <title>Hello World</title>
</head>
<body>
 
First name: <input id="first_name">
Last name: <input id="last_name">
<button id="say">Say hi!</button>
 
<hr>
<div id="result"></div>
 
<script>
function say_hi() {
    var fname = document.getElementById('first_name').value;
    var lname = document.getElementById('last_name').value;
 
    var html = 'Hello <b>' + fname + '</b> ' + lname;
 
    document.getElementById('result').innerHTML = html;
}
 
document.getElementById('say').addEventListener('click', say_hi);
</script>
 
</body>
</html>

## JavaScript Variables

Variables
Variables are containers for storing data (values).

In this example, x, y, and z, are variables, declared with the var keyword:

var x = 5;

var y = 6;

var z = x + y;

From the example above, you can expect:

+ x stores the value 5
+ y stores the value 6
+ z stores the value 11

### Much Like Algebra

var price1 = 5;
var price2 = 6;
var total = price1 + price2;

In programming, just like in algebra, we use variables (like price1) to hold values.

In programming, just like in algebra, we use variables in expressions (total = price1 + price2).

From the example above, you can calculate the total to be 11.

JavaScript Identifiers
All JavaScript variables must be identified with unique names.

These unique names are called identifiers.

Identifiers can be short names (like x and y) or more descriptive names (age, sum, totalVolume).

The general rules for constructing names for variables (unique identifiers) are:

+ Names can contain letters, digits, underscores, and dollar signs.
+ Names must begin with a letter
+ Names can also begin with $ and _ (but we will not use it in this tutorial)
+ Names are case sensitive (y and Y are different variables)
+ Reserved words (like JavaScript keywords) cannot be used as names

