# Javascript Basics

## Table of Contents
- [Variables and Operators](javascriptbasics.md#variables-and-operators)
- [Data Types and Conditionals](javascriptbasics.md#data-types-and-conditionals)
- [Javascript Developer Tools](javascriptbasics.md#javascript-developer-tools)
- [Function Basics](javascriptbasics.md#function-basics)

# Variables and Operators

### How to run Javascript code?

1. Run via the browser
   - Create HTML file with JS code inside of it
   - Save and open file in web browser
     - Right click on blank page and select "Inspect Element"
     - Select 'Console' tab to view output of our `console.log` statement
     
   HTML code:
   
   ```
      <!DOCTYPE html>
   <html>
   <head>
     <meta charset="UTF-8">
     <title>Page Title</title>
   </head>
   <body>
     <script>
       // Your JavaScript goes here!
       console.log("Hello, World!")
     </script>
   </body>
   </html>
   ```
   
2. Run via external script:
   ```  <script src="javascript.js"></script> ```

### Variables
**Variable:** a "named storage" containers for data in code
   - Ways to create a variable
     1. `var`
     2. `let`
     3. `const`
   - To declare a variable:
     ```let message;```
   - Assign data to variable by using assignment operator `=`
     ```
     let message;
     message = 'Hello'; //store the string 'Hello' in teh variable named message
     ```
   - Show the variable content
     ```
     let message = ' Hello!'
     alert(message);
   - Can declare multiple variables in one line with `,`
     - Use multiline style
### Variable Naming Rules
1. The name must contain only letters, digits, or the symbols `$` and `_`
2. The first character must **not** be a digit
3. When the value is changed, the old data is removed from the variable

### Constants
**Constant:** an unchanging variable, cannot be reassigned
Example:
```
const pageLoadTime = /* time taken by a webpage to load */;
```
- The value of `pageLoadTime` is not known before the page load, so it’s named normally - But it’s still a constant because **it doesn’t change** after the assignment
- Capital-named constants are only used as aliases for “hard-coded” values

### Numbers

| Operator | Description |
|----------|------------------|
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| ** | Exopnentiation |
| / | Division |
| % | Modulus (Remainder) |
| ++ | Increment |
| -- | Decrement |
  
**Operands:** the numbers in an arithmetic operation (What operators are applied to)
   - Unary: has a single operand
   - binary: has two operands

**Operator:** the operations to be performed between the two operands
Javascript numbers can be written with or without decimals.
```
let x = 3.14; // A number with decimals
let y = 3;    // A number without decimals
```
- Javascript numbers are always 64-bit floating point
- Integers are accurate up to 15 digits
- Floating point arithmitic is not always 100% accurate
  - Helps to multiply and divide

### Adding Numbers and Strings

**Concatenation**
- If you add two numbers, the result will be a number:
  
```
   let x = 10;
   let y = 20;
   let z = x + y; // you will get 30
```

- If you add two strings or a a number and a string, the result will be a string
concatenation:

```
   let x = "10";
   let y = "20";
   let z = x + y; // you will get 1020
```

- In other cases, JavaScript will try to convert strings to numbers in all numeric operations:
  
```
let x = "100";
let y = "10";
let z = x / y; // you will get 10
```

**NaN - not a number**
`NaN`: indicates that a number is not a legal number
- Trying to do arithmetic with a non-numberic string

**Infinity**
`Infinituy`: indicates number is outside the largest possible number
- Division by zero

**Hexadecimal**
JS interprets numeric constants as hexadecimal if they are preceded by 0x
- Base 16 and then a-f in each column
- Setting colors in CSS

### Modify-in-place
Used to apply an operator to a variable and store the new result in the same variable
- `+=` adds and stores
- `*=` multiplies and stores

### Increment and Decrement
Can only be applied to variables, NOT values
- Operators `++` and `--` can be placed before or after a variable
  - **Postfix form:** `counter++`
       - Returns the old value (prior to increment)
  - **Prefix form:** `++counter`
       - alert() returns the new incremented value
       - Use if you would like to increase a value and immediately use the result of the operator

### Comma
Allows evaluation of several expressions, with only last expression evaluated and returned as result

### Useful Number Methods
- `.toFixed()`: Round number to a fixed number of decimal places
- `Number()`: Convert string value to number version of same value
  ```
  let myNumber = "74";
   myNumber = Number(myNumber) + 3;
   ```
## Data Types and Conditionals

### Data Types
1. Number
   - Regular numbers
   - Special numeric values: `Infinity`, `-Infinity`, `NaN`
2. BigInt
    - BigInt type was added to the language to represent integers of arbitrary length
    - A BigInt value is created by appending `n` to the end of an integer
3. String
    - Must be surrounded by double quotes
    - Backticks are “extended functionality” quotes
      - They allow embedding of variables and expressions into a string by wrapping them in ${…}
4. Boolean
   - Commonly used to store yes/no values:
      - `True` means "yes, correct"
      - `False` means "no, incorrect"
5. The "null" value
   - Represents "nothing", "empty", or "value unknown"
6. The "undefined" value
   - Represents "value is not assigned"
7. Objects and symbols
   - `object` for more complex data structures
   - 'symbol` used to create unique identifiers for objects
8. The typeof operator
   - Returns the type of operand


### Embedding Javascript

Can wrap javascript variables or expressions inside `${}` and result will be included in the string

```
const name = "Chris";
const greeting = `Hello, ${name}`;
console.log(greeting); // "Hello, Chris"
```

**Concatenation:** You can use the same technique to join together two variables 

```
const one = "Hello, ";
const two = "how are you?";
const joined = `${one}${two}`;
console.log(joined); // "Hello, how are you?"
```

### Mutiline strings
Template literals respect the line breaks in the source code. To have the equivalent output using a normal string, you'd have to include line break characters (`\n`) in the string.


### Javascript String Methods
**JavaScript strings can't be changed directly:** When you use methods to modify a string, it actually creates a new string with the changes, leaving the original string untouched.

#### String length
Returns the length of a string
   ```
   let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
   let length = text.length;
   ```

#### Extracting String Characters
There are 4 methods for extracting string characters:

- The `at(position)` Method
   - The at() method returns the character at a specified index (position) in a string
   - Allows the use of negative indexes
- The `charAt(position)` Method
   - Returns the character at specified index, where 0 is the first character
     
     ```
        let text = "HELLO WORLD";
        let char = text.charAt(0);
      ```
   
- The `charCodeAt(position)` Method
   - Returns the UTF-16 unicode of the character at a given position in a string
- Using property access `[]` like in arrays
   - It makes strings look like arrays (but they are not)
   - If no character is found, `[ ]` returns undefined, while charAt() returns an empty string
   - It is read only: `str[0] = "A"` gives no error (but does not work!)

#### Extracting String Parts
There are 3 methods for extracting a part of a string:

- `slice(start, end)`
   - Extracts a part of string and returns extracted part in a new string
     
     ```
     let text = "Apple, Banana, Kiwi";
     let part = text.slice(7, 13); // returns Banana
      ```
   - If you omit the second parameter, the method will slice out the rest of the string:
   - If a parameter is negative, the position is counted from the end of the string:
- `substring(start, end)`
   - Start and end values less than 0 are treated as 0 in substring()
- `substr(start, length)`
   - Second parameter specifies the **length** of the extracted part
   - If you omit the second parameter, `substr()` will slice out the rest of the string
   - If the first parameter is negative, the position counts from the end of the string
 
     ```
     let str = "Apple, Banana, Kiwi";
     let part = str.substr(7, 6); // Returns Banana
      ```
#### Converting to Upper and Lower Case
- A string is converted to upper case with `toUpperCase()`
- A string is converted to lower case with `toLowerCase()`

#### Javascript String concat
`concat` joins two or more strings

```
let text1 = "Hello";
let text2 = "World!";
let text3 = text1.concat(" ",text2) // Returns "Hello World!"
```

#### Javascript String trim()
This method removes whitespace from both sides of a string
- `trimStart()` removes whitespace from start of a string
- `trimEnd()` removes whitespace only from end of a string

#### Javascript String Padding
- The padStart() method pads a string from the start
   - It pads a string with another string (multiple times) until it reaches a given length
- The padEnd() method pads a string from the end
  - It pads a string with another string (multiple times) until it reaches a given length
- The padEnd() method is a **string method**: to pad a number, convert the number to a string first.


#### Javascript String repeat()
The `repeat()` method returns a string with a number of copies of a string
- Returns a new string, does not change original string
- Syntax: `string.repeat(count)`

#### Replacing String Content
The `replace()` method replaces a specified value with another value in a string:
- Replaces only the first match and is case sensitive
   - To replace all matches, use a **regular expression** with a `g/` flag

     ```
     let text = "Please visit Microsoft and Microsoft!";
     let newText = text.replace(/Microsoft/g, "W3Schools");
      ```
      - Or use replaceAll()
- To replace case insensitive, use **reular expression**(written without quotes) with an `/i` flag

#### Converting a String to an Array
- `split()` method
   - `text.split(",")`    // Split on commas
   - `text.split(" ")`    // Split on spaces
   - `text.split("|")`    // Split on pipe


### Conditionals
- Comparison operators
  - Greater/less than: a > b, a < b
  - Greater/less than or equals: a >= b, a <= b
  - Equals: a == b, please note the double equality sign == means the equality test, while a single one a = b means an assignment
  - Not equals: In maths the notation is ≠, but in JavaScript it’s written as a != b
- Boolean is the result

   ```
   let result = 5 > 4; // assign the result of the comparison
   alert( result ); // true
   ```

#### String Comparison
-Strings are compared letter-by-letter in the “dictionary” order
- If the first character from the first string is greater (or less) than the other string’s, then the first string is greater (or less) than the second, we’re done
- Otherwise, if both strings’ first characters are the same, compare the second characters the same way
- Repeat until the end of either string
- If both strings end at the same length, then they are equal. Otherwise, the longer string is greater
- When values of different types are compared, they get converted to numbers (with the exclusion of a strict equality check).

#### Strict equality
- A regular equality check `==` has a problem.
   - It cannot differentiate 0 from false
   - The same thing happens with an empty string
- Strict equality operator `===` checks the equality without type conversion
- The values null and undefined equal == each other and do not equal any other value
- Be careful when using comparisons like > or < with variables that can occasionally be null/undefined. Checking for null/undefined separately is a good idea.

### If, else, and else if
- Use `if` to specify a block of code to be executed, if a specified condition is true
  
  ```
  if (condition) {
  //  block of code to be executed if the condition is true
   }
   ```

- Use `else` to specify a block of code to be executed, if the same condition is false
  
  ```
  if (condition) {
  //  block of code to be executed if the condition is true
   } else {
  //  block of code to be executed if the condition is false
   }
   ```
  
- Use `else if` to specify a new condition to test, if the first condition is false

  ```
  if (condition1) {
  //  block of code to be executed if condition1 is true
   } else if (condition2) {
  //  block of code to be executed if the condition1 is false and condition2 is true
   } else {
  //  block of code to be executed if the condition1 is false and condition2 is false
   }
  ```
  
- Use `switch` to specify many alternative blocks of code to be executed
  - Take a single expression/value as an input, and then look through several choices until they find one that matches that value, executing the corresponding code that goes along with it
  - choices must be the same type (string/number)
  ```switch (expression) {
     case choice1:
    // run this code
    break;

     case choice2:
    // run this code instead
    break;

     // include as many cases as you like

     default:
    // actually, just run this code
    break;
     }
    ```


### Logical Operators
1. **||(OR):** If any of its arguments are true, it returns true, otherwise it returns false
   - Evaluates from let to right
   - For each operand, converts it to boolean
   - If result is `true`, stops and returns the original value of the operand
   - If all `false`, returns the last operand
2. **&&(AND):** Returns true if both are `true`, otherwise `false`
   - Finds the first falsy value
   - Evaluates left to right
   - Converts all operands to boolean. If result is `false`, stops and returns original value of that operand
   - If all truthy, returns the last operand
3. **!(NOT):** The boolean NOT operator
   - Converts operand to boolean type: `true/false`
   - Returns the inverse value
   - Highest precendence
4. **??(Nullish Coalescing):**



### Javascript Methods to Know
- `document.querySelector`: This is a method provided by JavaScript that allows you to search the HTML document for elements based on a CSS selector.  Think of it like a search function looking for specific elements in your webpage.
- `.addEventListener([type of event],[function])`: This method is used to attach an event listener to the selected element. An event listener is a piece of code that waits for a specific event (action) to occur on that element.


### Ternary Operator (?)
Tests a condition and returns one value/expression if it is `true`, and another if it is `false`

Psuedocode:

```
condition ? run this code : run this code instead
```

Example

```
const greeting = isBirthday
  ? "Happy birthday Mrs. Smith — we hope you have a great day!"
  : "Good morning Mrs. Smith.";
```

If multiple `?`

```
condition1 ? value_if_true1 : (condition2 ? value_if_true2 : value_if_false2)
```


## Javascript Developer Tools 

### Opening DevTools
1. From the `Chrome Menu` > `More Tools` > `Developer Tools`
2. Right-click anywhere on a webpage and select `Inspect`
3. Use the keyboard shortcut `F12` or `Ctrl` + `Shift` + `C` (Mac: `Opt` + `Cmd` + `C`)

## Function Basics
- **Parameters** are items listed between the `()` in the function declaration
- **Function arguments** are actual values passed in function

   ```
   function sum(param1, param2) {
      return param1 + param2;
   }

   sum(1,2);
   ```

### Build-In Browser Functions
- Everytime a text string or array is manipulated
   - Examples: `[myText].replace` (replaces a string), `[myArray].join` (joins an array to a string), `Math.random` (generates a random number)
- `Math.random()`: generates a decimal number between 0 and 1
   - If you want a whole number, multiple function by number
 
### Function vs Methods
- Functions that are part of objects are called methods


### Invoking functions
```
function myFunction() {
  alert("hello");
}

myFunction();
// calls the function once
```

### Function parameters
Some functions require parameters to be specified when you are invoking them — these are values that need to be included inside the function parentheses, which it needs to do its job properly

**Default parameters:** If you're writing a function and want to support optional parameters, you can specify default values by adding = after the name of the parameter, followed by the default value:

```
function hello(name = "Chris") {
  console.log(`Hello ${name}!`);
}

hello("Ari"); // Hello Ari!
hello(); // Hello Chris!
```

### Anonymous functions and arrow functions

**Anonymous functions:** No name function, often seen when a function expects to recieve another function as a parameter

```
(function () {
  alert("hello");
});
```

Example: Instead of defining a separate `logKey()` function, you can pass an anonymous function

```
textBox.addEventListener("keydown", function (event) {
  console.log(`You pressed "${event.key}".`);
});
```

**Arrow functions:** Instead of `function(event)`, you write `(event) =>`

If the function only takes one parameter, you can omit the parentheses around the parameter:

```
textBox.addEventListener("keydown", event => {
  console.log(`You pressed "${event.key}".`);
});
```

### Function Scope and Conflicts

Variables and other things defined inside function are their own separate **scope**.

**Global scope:** outisde of all functions, are accessible from everywhere in the code

Scope:
- When you define a variable inside a function, it's only accessible within that function and any nested functions within it. These variables are not accessible from outside the function's scope
- JavaScript uses lexical scoping, which means the accessibility of a variable is determined by its location in the code, not by the order of execution

Conflicts:
- Conflicts can arise when you have variables with the same name in different scopes. JavaScript prioritizes local scope over global scope
- If you define a variable with the same name inside a function and outside the function, the variable within the function takes precedence. The outer variable is hidden within the function's scope

  
