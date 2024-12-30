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
