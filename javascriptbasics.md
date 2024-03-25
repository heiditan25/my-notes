# Javascript Basics

## Table of Contents
- [Variables and Operators](javascriptbasics.md#variables-and-operators)
- [Data Types and Conditionals](javascriptbasics.md#data-types-and-conditionals)

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
- 

