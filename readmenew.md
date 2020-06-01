# 1. Avoid Global Variables
- Minimize the use of global variables.
- This includes all data types, objects, and functions.
- Global variables and functions can be overwritten by other scripts.
- Use local variables instead, and learn how to use closures.

# 2. Always Declare Local Variables
- All variables used in a function should be declared as local variables.
- Local variables must be declared with the var keyword or the let keyword, otherwise they will become global variables.
 # 3.Declarations on Top
 > It is a good coding practice to put all declarations at the top of each script or function.
 
*This will:*
- Give cleaner code
- Provide a single place to look for local variables
- Make it easier to avoid unwanted (implied) global variables
- Reduce the possibility of unwanted re-declarations
``` js
// Declare at the beginning
var firstName, lastName, price, discount, fullPrice;

// Use later
firstName = "John";
lastName = "Doe";

price = 19.90;
discount = 0.10;

fullPrice = price + discount;
```
# 4. Initialize Variables
>It is a good coding practice to initialize variables when you declare them

*This will:*
- Give cleaner code
- Provide a single place to initialize variables
- Avoid undefined values
 
``` js
// Declare and initiate at the beginning
var firstName = "",
lastName = "",
price = 0,
discount = 0,
fullPrice = 0,
myArray = [],
myObject = {};
```
# 5.Never Declare Number, String, or Boolean Objects
>Always treat numbers, strings, or booleans as primitive values. Not as objects.
Declaring these types as objects, slows down execution speed, and produces nasty side effects:

**Example**
```js
var x = "John";             
var y = new String("John");
(x === y) // is false because x is a string and y is an object.
```
# 6. Don't Use new Object()
- Use `{}` instead of `new Object()`
- Use `""` instead of `new String()`
- Use `0` instead of `new Number()`
- Use `false` instead of `new Boolean()`
- Use `[]` instead of `new Array()`
- Use `/()/` instead of `new RegExp()`
- Use `function (){}` instead of `new Function()`
**Example**
```js
var x1 = {};           // new object
var x2 = "";           // new primitive string
var x3 = 0;            // new primitive number
var x4 = false;        // new primitive boolean
var x5 = [];           // new array object
var x6 = /()/;         // new regexp object
var x7 = function(){}; // new function object
```
# 7. Beware of Automatic Type Conversions
>Beware that numbers can accidentally be converted to strings or NaN (Not a Number).
JavaScript is loosely typed. A variable can contain different data types, and a variable can change its data type:

***Example***
```js
var x = "Hello";     // typeof x is a string
x = 5;               // changes typeof x to a number
```
# 8. Use === Comparison
- The == comparison operator always converts (to matching types) before comparison.
- The === operator forces comparison of values and type:

***Example***
```js
0 == "";        // true
1 == "1";       // true
1 == true;      // true

0 === "";       // false
1 === "1";      // false
1 === true;     // false
```
# 9. Use Parameter Defaults
>If a function is called with a missing argument, the value of the missing argument is set to `undefined`.
Undefined values can break your code. It is a good habit to assign default values to arguments.
```js
Example
function myFunction(x, y) {
  if (y === undefined) {
    y = 0;
  }
}
```
# 10. Avoid Using eval()
>The `eval()` function is used to run text as code. In almost all cases, it should not be necessary to use it.
Because it allows arbitrary code to be run, it also represents a security problem.