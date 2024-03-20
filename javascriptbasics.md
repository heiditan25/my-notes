# Javascript Basics

## Variables and Operators

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
  
**Operands:** the numbers in an arithmetic operation
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

### Useful Number Methods
- `.toFixed()`: Round number to a fized number of decimal places
- `Number()`: Convert string value to number version of same value
  ```
  let myNumber = "74";
   myNumber = Number(myNumber) + 3;
   ```


  

