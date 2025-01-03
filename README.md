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

## Control Flow
### 1. if...else
- Types of Conditional Statements:
1. if...else
2. switch...case
```
// Hour
// If hour is between 6am and 12pm: Good morning!
// If it is between 12pm and 6pm: Good afternoon!
// Otherwise: Good evening!

let hour = 10;
  
if (hour >= 6 && hour < 12)
	console.log("Good Morning!");
else if(hour >= 12 && hour < 18)
	console.log("Good Afternoon");
else
	console.log("Good Evening");
```

### 2. Switch...case
```
let role = 'Moderator';

switch(role){
	case 'guest':
		console.log('Guest User');
		break;
	case 'moderator':
		console.log('Moderator User');
		break;
	default:
		console.log('Unknown User');
}
```

### 3. For
- Types of Loops:
1. For
2. While
3. Do...while
4. For...in
5. For...of
```
for (let i = 0; i < 5; i++){
	console.log('Hello World ', i);
} 

for (let i = 0; i < 5; i++){
	if (i % 2 === 0){
		console.log(i);
	}
}
```

### 4. While
```
let i = 0;
while(i <= 5){
	if (i % 2 !== 0) console.log(i);
	i++;
}
```

### 5. Do...While
```
let i = 9;

do{
	if (i % 2 !== 0) console.log(i);
	i++;
} while(i <= 5);
```

### 6. Infinite Loop
```
let i = 5;
while (i < 7){
	console.log(i);
	i++;
}

while(true){

}

let x = 0;
do {

} while (x < 5);
```

### 7. For...In
```
// for-in
const person = {
name: 'Attraya',
age: 30
};

for (let key in person)
	console.log(key, person[key]);  

const color = ['red', 'blue', 'green'];

for (let index in color)
	console.log(color[index]);
```

### 8. For...of
```
// for-of
const colors = ['red', 'green', 'blue'];

for (let color of colors){
	console.log(color);
}
```

### 9. Break and Continue
```
// break: we jump out of a loop
let i = 0;

while(i<=10){
	if (i === 5) break;
	console.log(i); // 0 1 2 3 4
	i++;
}

// continue: we continue with the next iteration
let j = 0;

while(j <= 10){
	if (j % 2 === 0){
		j++;
		continue;
	}
	console.log(j);
	j++;
}
```

### 10. Exercise: Max of two numbers
```
let number = max(17, 11);
console.log(number);

function max(a, b){
	return (a > b) ? a : b;
}
```

### 11. Exercise: Landscape or Portrait
```
function isLandscape(width, height){
	return (width > height);
}

console.log(isLandscape(800, 600)); // true
```

### 12. Exercise: FizzBuzz
```
console.log(fizzbuzz(true));

// Divisible by 3 => Fizz
// Divisible by 5 => Buzz
// Divisible by both 3 and 5 => FizzBuzz
// Not divisible by 3 or 5 => input
// Not a number => 'Not a number'
function fizzbuzz(input){
	if (typeof input !== 'number'){
		return NaN;
	}
	if (input % 3 === 0 && input % 5 === 0){
		return 'FizzBuzz';
	} else if (input % 3 === 0){
		return 'Fizz';
	} else if (input % 5 === 0){
		return 'Buzz';
	} else {
		return input;
	}
}
```

### 13. Exercise: Demerit Points
```
// Speed Limit = 70
// 5 -> 1 point
// Math.floor(1.3)
// 12 points -> suspended

checkSpeed(130);

function checkSpeed(speed){
	const speedLimit = 70;
	const kmPerPoint = 5;
	if (speed < speedLimit + kmPerPoint) {
		console.log('OK');
		return;
	}
	let points = Math.floor((speed - speedLimit) / kmPerPoint);
	if (points >= 12) {
		console.log('License Suspended');
	} else {
		console.log('Points: ', points)
	}
}
```

### 14. Exercise: Even and Odd Numbers
```
showNumbers(1);

function showNumbers(limit){
	let i = 0;
	while (i <= limit){
		if (i % 2 === 0){
			console.log(i, 'EVEN');
		} else {
			console.log(i, 'ODD');
		}
		i++;
	}
}
```

### 15. Exercise: Count Truthy
```
const array = [1, 2, 3, 0, '', 2, NaN, 67];
console.log(countTruthy(array));

// Falsy:
// undefined
// null
// ''
// false
// 0
// NaN
function countTruthy(array){
	let count = 0;
	for (let value of array){
		if (value){
			count++;
		}
	}
return count;
}
```

### 16. Exercise: String Properties
```
const movie = {
	title: 'a',
	releaseYear: 2018,
	rating: 4.5,
	director: 'b'
}

showProperties(movie);

function showProperties(obj){
	for (let key in obj){
		if (typeof obj[key] === 'string'){
			console.log(key, obj[key]);
		}
	}
}

// title a
// director b
```

### 17. Exercise: Sum of Multiples 3 and 5
```
console.log(sum(10));

function sum(limit){
	let result = 0;
	for (let i = 0; i <= limit; i++){
		if (i % 3 === 0 || i % 5 === 0){
			result += i;
		}
	}
	return result;
}
```

### 18. Exercise: Grade
```
const marks = [80, 80, 50];

// Average = 70

// 0-59: F
// 60-69: D
// 70-79: C
// 80-89: B
// 90-100: A
  
console.log(calculateGrade(marks));

function calculateGrade(marks){

	let sum = 0;
	
	for (let mark of marks){
		sum += mark;
	}
	
	let average = sum / marks.length;

	if (average <= 59 && average >= 0) return 'F';	
	else if (average <= 69 && average >= 60) return 'D';
	else if (average <= 79 && average >= 70) return 'C';
	else if (average <= 89 && average >= 80) return 'B';
	else if (average <= 100 && average >= 90) return 'A';
}
```

### 19. Exercise: Stars
```
showStars(5);

function showStars(rows){
	for (let row = 1; row <= rows; row++){
		let pattern = '';
		for (let i = 0; i < row; i++){
			pattern += '*';
		}
	console.log(pattern);
	}
}

// *
// **
// ***
// ****
// *****
```

### 20. Exercise: Prime Numbers
```
showPrimes(10);

// Prime (whose factors are only 1 and itself)
// Composite
  
// 12 = 1, 2, 3, 4, 6, 12
// Can be divided evenly by its factor

// 11 = 1, 11
// 13 = 1, 13

function showPrimes(limit){
	for (let number = 2; number <= limit; number++){
		if (isPrime(number)) console.log(number);
	}
}

  

function isPrime(number) {
	let isPrime = true;
	for (let factor = 2; factor < number; factor++)
		if (number % factor === 0)
			return false;
	return true;
}

// 2
// 3
// 5
// 7
```
