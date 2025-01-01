# Learning JavaScript by Mosh Hamedani
## Basics
### 1. Variables
- var is not a good practice anymore, use let
- By default, variables that we declare in JS is undefined
- Rules of variable names: 
	- Cannot be a reserved keyboard
	- Should be meaningful
	- Cannot start with a number (1name)
	- Cannot contain a space or hyphen (-)
	- They are case-sensitive
```
	let firstName = 'Attraya';
	let lastName = 'Das';
```

### 2. Constants
- Value of a constant cannot change
- We cannot reassign a constant
```
const interestRate = 12;
interestRate = 10;
console.log(interestRate);

This will give: TypeError: Assignment to constant variable.
```

### 3. Primitive Type
- In JS we have two categories of type:
	1. Primitive/ Value Types
	2. Reference Types
- Primitives / Value Types:
	1. String
	2. Number
	3. Boolean
	4. undefined
	5. null
```
let name = 'Attraya'; // String Literal
let age = 25; // Number Literal
let isApproved = true; // Boolean Literal
let firstName = undefined; // If not initialized, its undefined as default
let selectedColor = null; // Used when we expicitely clear the value of the variable
```

### 4. Dynamic Typing
- JS is a dynamic language (not a static language)
- The type of variable can be changed in the runtime
- Unlike static languages, the type of the variables will be determined at runtime based on the value we assign to them
- In JS, we don't have diferent type of numbers (13 and 12.9 are of type number)
- We can use ``` type of``` to check the variable type
```
let name = 'Attraya';
let age = 25;
let price = 22.9;
let isApproved = true;
let firstName = undefined;
let selectedColor = null;

console.log(typeof name); // string
console.log(typeof age); // number
console.log(typeof price); // number
console.log(typeof isApproved); // boolean
console.log(typeof firstName); // undefined
console.log(typeof selectedColor); // object
```

### 5. Objects
- Reference Types:
	1. Object
	2. Array
	3. Function
- When we're dealing with multiple related variables, we can put these variables inside of an object
```
let person = {
name: 'Mosh',
age: 30
};

// Dot Notation
person.name = 'Attraya'

// Bracket Notation
let selection = 'name'
person[selection] = 'Mary';

console.log(person.name);
```

### 6. Arrays
```
let selectedColor = ['red', 'blue', 'green'];
selectedColor[3] = 'magenta';
selectedColor[4] = 1;

console.log(selectedColor);
console.log(selectedColor[0]);
console.log(selectedColor.length); // Returns number of element in Arrays
```

### 7. Functions
```
function greet(){
	console.log('Hello World');
}

function anotherGreet(name){
	console.log('Hello '+name);
}

function anotherAnotherFunction(firstName, lastName){
	console.log('Hello ' + firstName + ' ' + lastName);
}

greet(); // Hello World
anotherGreet('Attraya'); // Hello Attraya
anotherAnotherFunction('Attraya', 'Das'); // Hello Attraya Das
```

### 8. Types of Functions
```
// Performing a task
function greet(){
	console.log('Hello World');
}

// Calculating a value
function square(number){
	return number * number;
}

console.log(square(2)); // 4
```

## Operators
### 1. JavaScript Operators
- We use operators along with our variables and constants to create expressions. And using these expressions we can implement logic and algorithms.
- We have different types of operators in JS:
	1. Arithmetic
	2. Assignment
	3. Comparison
	4. Logical
	5. Bitwise

### 2. Arithmetic Operators
```
let x = 10;
let y = 3;

console.log(x + y); // 13
console.log(x - y); // 7
console.log(x * y); // 30
console.log(x / y); // 3.3333333333333335
console.log(x % y); // 1
console.log(x ** y); // x to the power y -> 1000

// Increment (++)
console.log(x++); // 10
console.log(x); // 11

// Decrement (--)
console.log(--y); // 2
```

### 3. Assignment Operators
```
let x = 10;

// Both are same
x++;
x = x + 1;

// Both are same
x = x + 5;
x += 5;

// Both are same
x = x * 3;
x *= 3;
```

### 4. Comparison Operators
```
let x = 1;

// Relational
console.log(x > 0); // true
console.log(x >= 0); // true
console.log(x < 1); // false
console.log(x <= 1); // true

// Equality
console.log(x === 1); // true
console.log(x !== 1); // false
```

### 5. Equality Operators
- The strict equality operator ensures that both values have the same type and the same value.
- The loose equality operator doesn't care about the types matching, if the types don't match, it will convert the type of what we have on the right side to match what we have on the left side. And then it will only check if the values are equal.
- We should use String Equality as it's more precise and accurate
```
// Strict Equality (Type + Value)
console.log(1 === 1); // true
console.log(1 === '1'); // false

// Lose Equality (Value)
console.log(1 == 1); // true
console.log(1 == '1'); // true
console.log(1 == true); // true
console.log(0 == false); // true
```

### 6. Ternary Operators
```
// If a customer has more than 100 points,
// they are a 'gold' customer, otherwise,
// they are a 'silver' customer.

let points = 110;
let type = points > 100 ? 'gold' : 'silver';

console.log(type); // gold
```

### 7. Logical Operators with Booleans
```
// Logical AND (&&)
// Returns TRUE if both operands are TRUE
console.log(true && false); // false

let highIncome = true;
let goodCreditScore = true;
let eligibleForLoan = highIncome && goodCreditScore;

console.log(eligibleForLoan); // true  

// Logical OR (||)
// Returns TRUE if one of the operands is TRUE
console.log(true || false); // true

// NOT (!)
console.log(!true); // false
```

### 8. Logical Operators with Non-Booleans
- Falsy Values (false):
1. undefined
2. null
3. 0
4. false
5. ''
6. NaN
- Anuthing that is not Falsy, it is Truthy 
```
console.log(false || true); // true
console.log(false || 'Attraya'); // Attraya
console.log(false || 1); // 1
console.log (false || 1 || 2); // 1 // Short-circuiting: It dosen't check for the third position

// Real time usecase
let userColor = '';
let defaultColor = 'blue';
let currentColor = userColor || defaultColor;
console.log(currentColor); // blue
```

### 9. BitWise Operators
```
// 1 -> 00000001
// 2 -> 00000010
// R -> 00000011 // OR
// R -> 00000000 // AND

console.log(1 | 2); // Bitwise OR -> 3
console.log(1 & 2); // Bitwise AND -> 0
```

### 10. Operator Precedence
- We can use brackets to determine the precedence
```
let x = 2 + 3 * 4;
let y = (2 + 3) * 4;

console.log(x); // 14
console.log(y); // 20
```

### 11. Swapping Variables
```
let a = 'red';
let b = 'blue';

let c = b;
b = a;
a = c;

console.log(a);
console.log(b);
```
