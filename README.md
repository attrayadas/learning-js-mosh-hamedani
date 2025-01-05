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

## Objects
### 1. Basics
- Objects are collection of key-value pairs
```
// Object-oriented Programming (OOP)
const circle = {
	radius: 1,
	location: {
		x: 1,
		y: 1
	},
	isVisible: true,
	draw: function(){
		console.log('draw');
	}
}

circle.draw();
```

### 2. Factory Functions
```
// Factory Function
function createCircle(radius){
	return {	
		radius,		
		draw() {
			console.log('draw');
		}
	};
}

const circle1 = createCircle(1);
console.log(circle1); // { radius: 1, draw: [Function: draw] }

const circle2 = createCircle(4);
console.log(circle2); // { radius: 4, draw: [Function: draw] }
```

### 3. Constructor Functions
- We need to use Pascal Notation: OneTwoThreeFour
```
// Constructor Function
function Circle(radius){
	this.radius = radius;
	this.draw = function(){
		console.log('draw');
	}
}

const circle = new Circle(1);
console.log(circle);
```

### 4. Dynamic Nature of Objects
- Once we create an object, we can always add new properties or methods or remove existing ones.
```
const circle = {
	radius: 1
};

circle.color = 'blue';
circle.draw = function(){
	console.log('draw');
}

  

delete circle.radius;
delete circle.draw;

console.log(circle); // { color: 'blue' }
```

### 5. Constructor Property
- Every object has a constructor property and that references the function that was used to create an object
```
let x = {};
// Internally it's let x = new Object();

new String(); // '', "", `` -> cleaner and simpler than using constructor
new Boolean(); // true, false
new Number(); // 1, 2, 3
```

### 6. Functions are Objects
// Need to revisit

### 7. Value vs Reference Types
- In JavaScript we have two categories of types:
1. Value Types (primitives): eg- Number, String, Boolean, Symbol, undefined, null
2. Reference Types (object): eg- Object, Function, Array
- Primitives are copied by their value
- Objects are copied by their reference
```
// Primitive Types
let x = 10;
let y = x;

x = 20;

console.log(x); // 20
console.log(y); // 10

// Reference Types
let a = {value : 10}
let b = a;

a.value = 20;

console.log(a); // 20i
console.log(b); // 20
```

### 8. Enumerating Properties of an Object
- For...of loop can only be used in iterables like arrays and maps
```
const circle = {
	radius: 1,
	draw() {
		console.log("draw");
	},
};

for (let key in circle) {
	console.log(key, circle[key]);
}
// radius 1
// draw [Function: draw]


// for (let key of circle){ // error: circle is not iterable
//   console.log(key);
// }

  
for (let key of Object.keys(circle)) {
	console.log(key);
}

// radius
// draw

for (let entry of Object.entries(circle)) {
	console.log(entry);
}
// [ 'radius', 1 ]
// [ 'draw', [Function: draw] ]

if ('radius' in circle) console.log('yes'); // yes
```

### 9. Cloning an Object
- We can use `Object.assign(target, source)` to clone object
```
const circle = {
	radius: 1,
	draw() {
		console.log('draw');
	}
};

// 1st way to clone
const another = {};

for (let key in circle){
	another[key] = circle[key];
}
// another['radius'] = circle['radius'];

console.log(another); // { radius: 1, draw: [Function: draw] }
 
// 2nd way to clone
const anotherAnother = Object.assign({}, circle); // can
console.log(anotherAnother);

// 3rd way to clone
const anotherAnotherAnother = {...circle};
console.log(anotherAnotherAnother);
```

### 10. Garbage Collection
- Garbage Collector: It is to find the variables or constants that are no longer used and then deallocate the memory
- Memory allocation and deallocation happens automatically in JavaScript

### 11. Math
```
console.log(Math.E);
console.log(Math.random()); // gives random number between 0 to 1
console.log(Math.round(1.8)); // 2
console.log(Math.max(1, 2, 3, 67, 87, 2)); // 87
console.log(Math.min(1, 2, 3, 54)); // 1
```

### 12. String
```
// String primitive
const message = 'This is my first message ';

// String object
const another = new String('hi');

console.log(typeof message); // string
console.log(typeof another); // object

// JS engine internally wraps primitive with a string object

console.log(message.length); // 24
console.log(message[0]); // T
console.log(message.includes('my')); // true
console.log(message.startsWith('This')); // true
console.log(message.indexOf('m')); // 8
console.log(message.replace('first', 'second')); // This is my second message // It dosen't modify the original one
console.log(message); // This is my first message
console.log(message.toUpperCase()); // THIS IS MY FIRST MESSAGE
console.log(message.trim()); // This is my first message
console.log(message.split(' ')); // [ 'This', 'is', 'my', 'first', 'message', '' ]
```

### 13. Template Literals
```
const another = `Hello
'there'!`;

console.log(another);

const name = 'Attraya';
const mail =
`Hey ${name} ${2 + 3},

Thanks for joining my mailing list!

Regards`;

console.log(mail);
```

### 14. Date
```
const now = new Date();
const date1 = new Date('May 11 2028 09:00');
const date2 = new Date(2018, 4, 11, 9); // Month starts with 0, 0 -> January

console.log(now); // 2025-01-04T18:19:30.470Z
console.log(date1); // 2028-05-11T03:30:00.000Z
console.log(date2.getDate()); // 11
```

### 15. Exercise: Address Object
```
// street
// city
// zipCode
// showAddress(address)

const address = {
	street: 'Washington St.',
	city: 'New York',
	zipCode: '100076'
}

function showAddress(address){
	for (let element in address){
		console.log(element, address[element]);
	}
}

showAddress(address);
```

### 16. Exercise: Factory and Constructor Function
```
// Create object of address using both Factory and Constructor function

// Factory Function
function createAddress(street, city, zipCode){
	return {
		street,
		city,
		zipCode
	};
}

// Constructor Function
function Address(street, city, zipCode){
	this.street = street;
	this.city = city;
	this.zipCode = zipCode;
}

let address1 = createAddress('Gachibowli', 'Hyderabad', '500032');
console.log(address1); // { street: 'Gachibowli', city: 'Hyderabad', zipCode: '500032' }

let address2 = new Address('Brigade Road', 'Bangalore', '706539');
console.log(address2);
// Address {
// street: 'Brigade Road',
// city: 'Bangalore',
// zipCode: '706539'
// }
```

### 17. Exercise: Object Equality
```
function Address(street, city, zipCode){
	this.street = street;
	this.city = city;
	this.zipCode = zipCode;
}

let address1 = new Address('a', 'b', 'c');
let address2 = new Address('a', 'b', 'c');

function areEqual(address1, address2){
	return address1.street === address2.street && address1.city === address2.city && address1.zipCode === address2.zipCode;
};

function areSame(address1, address2){
	return address1 === address2;
};

console.log(areEqual(address1, address2));
console.log(areSame(address1, address2));
```

### 18. Exercise: Blog Post Object
```
// title
// body
// author
// views
// comments
// (author, body)
// isLive

const post ={
	title: 'a',
	body: 'b',
	author: 'c',
	views: 10,
	comments: [
		{author: 'a', body: 'b'},
		{author: 'c', body: 'd'},
	],
	isLive: true
}

console.log(post);
```
### 19. Exercise: Constructor Functions
```
function Post(title, body, author){
	this.title = title;
	this.body = body;
	this.author = author;
	this.views = 0;
	this.comments = [],
	this.isLive = false
}

let post = new Post('A', 'B', 'Attraya');

console.log(post);
```

### 20. Price Range Objects
```
let priceRanges = [
{ label: '$', toolTip: 'Inexpensive', minPerPerson: 0, maxPerPerson: 10 },
{ label: '$$', toolTip: 'Moderate', minPerPerson: 11, maxPerPerson: 20 },
{ label: '$$$', toolTip: 'Expensive', minPerPerson: 21, maxPerPerson: 50 },
];
```

## Arrays
### 1. Introduction
- We will learn doing these operations on Arrays:
	1. Adding new elements
	2. Finding elements
	3. Removing elements
	4. Splitting arrays
	5. Combining arrays

### 2. Adding Elements
```
const numbers = [3, 4];

// To add element in the end
numbers.push(10, 11);

// To add element in the beginning
numbers.unshift(1, 2);

// To add element in the middle
numbers.splice(2, 0, 'a', 'b');

console.log(numbers); // [ 1, 2, 'a', 'b', 3, 4, 10, 11 ]
```

### 3. Finding Elements (Primitives)
```
const numbers = [1, 2, 3, 4, 1, 5];

// Returns -1 if element doesn't exists
console.log(numbers.indexOf('a')); // -1

console.log(numbers.indexOf(1)); // 0
console.log(numbers.indexOf(1, 2)); // 4 -> search 1, finds from index 2

// Type of element matters
console.log(numbers.indexOf('1')); // -1

console.log(numbers.lastIndexOf(1)); // 4

// To check if an element exists
console.log(numbers.indexOf(1) !== -1); // true

// New method to check if element exists
console.log(numbers.includes(1)); // 1
```

### 4. Finding Elements (Reference Types)
```
const courses = [
	{ id: 1, name: 'a'},
	{ id: 2, name: 'b'},
];


// includes method doesn't work here, as it checks for reference

const course = courses.find(function(course) {
	return course.name === 'b';
});

const courseNotFound = courses.find(function(course) {
	return course.name === 'abc';
});

const courseIndex = courses.findIndex(function(course) {
	return course.name === 'a';
});

  
console.log(course); // { id: 2, name: 'b' }
console.log(courseNotFound); // undefined -> gives undefined if not found
console.log(courseIndex); // 0
```

### 5. Arrow Functions
```
const courses = [
	{ id: 1, name: 'a'},
	{ id: 2, name: 'b'},
];

// Old way
const course = courses.find(function(course) {
	return course.name === 'b';
});

// New way (used when we pass function as a parameter)
const course1 = courses.find(course => course.name === 'a');

console.log(course1); // { id: 1, name: 'a' }
```

### 6. Removing Elements
```
const numbers = [1, 2, 3, 4, 5, 6];

// Removing element from the end
const last = numbers.pop();
console.log(last); // 6
console.log(numbers); // [ 1, 2, 3, 4, 5 ]

// Removing element from the beginning
const first = numbers.shift();
console.log(first); // 1
console.log(numbers); // [ 2, 3 , 4, 5 ]

// Removing element from the middle
numbers.splice(2, 1);
console.log(numbers); // [ 2, 3, 5 ]
```

### 7. Emptying an Array
```
// 1st way
let numbers = [1, 2, 3, 4];
let another = numbers;

numbers = []; // SECOND BEST SOLUTION

console.log(numbers); // []
console.log(another); // [ 1, 2, 3, 4 ]

// 2nd way
let numbers1 = [1, 2, 3, 4];
numbers1.length = 0; // BEST SOLUTION

console.log(numbers1); // []

// 3rd way
let numbers2 = [1, 2, 3, 4];
numbers2.splice(0, numbers2.length);
  
console.log(numbers2); // []

// 4th way
let numbers3 = [1, 2, 3, 4];
while(numbers3.length >= 0){
	numbers3.pop();
}

console.log(numbers3); // []
```

### 8. Combining and Slicing Arrays
```
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = first.concat(second); // Both arays are unaffected
console.log(combined); // [ 1, 2, 3, 4, 5, 6 ]

const sliced = combined.slice(2, 4);
console.log(sliced); // [3, 4]
```

### 9. The Spread Operator
```
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = [...first, ...second];
const combined2 = [...first, 'a', ...second, 'b'];

console.log(combined); // [ 1, 2, 3, 4, 5, 6 ]
console.log(combined2); // [ 1, 2, 3, 'a', 4, 5, 6, 'b' ]
```

### 10. Iterating an array
```
const numbers= [1, 2, 3, 4, 5, 6, 7];

for (let number of numbers)
	console.log(number);
  
numbers.forEach(number => console.log(number)); // prints the elements

numbers.forEach((number, index) => console.log(number, index)); // prints the elements and its index
```

### 11. Joining Arrays
```
const numbers = [1, 2, 3];
let joined = numbers.join('-');
console.log(joined); // 1-2-3

const message = 'This is my first message';
let parts = message.split(' ');
console.log(parts); // [ 'This', 'is', 'my', 'first', 'message' ]

const combined = parts.join('-');
console.log(combined); // This-is-my-first-message
```

### 12. Sorting Arrays
```
const numbers = [2, 3, 1];
numbers.sort();

console.log(numbers); // [ 1, 2, 3 ]
  
numbers.reverse();
console.log(numbers); // [ 3, 2, 1 ]

const courses = [
	{ id: 1, name: 'Node.js'},
	{ id: 2, name: 'JavaScript'},
]

courses.sort((a, b) => {
	// a < b => -1
	// a > b -> 1
	// a === b => 0
	const nameA = a.name.toUpperCase; // required to maintain uniformity
	const nameB = b.name.toUpperCase;
	
	if (nameA.name < nameB.name) return -1;
	if (nameA.name > nameB.name) return 1;
	return 0;
});

console.log(courses); // [ { id: 1, name: 'Node.js' }, { id: 2, name: 'JavaScript' } ]
```

### 13. Testing the Elements of an Array
- `every()`: checks to see if every element in a given array matches the given criteria.
- `some()`: checks to see if we have at least one element that matches the given criteria.
```
const numbers = [2, -3, 1];

const allPositive = numbers.every(a => a >= 0); // checks for every element
console.log(allPositive); // false

const atleastOneNegative = numbers.some(a => a < 0); // checks for any element
console.log(atleastOneNegative); // true
```

### 14. Filtering an Array
```
const numbers = [2, -3, 1];
let positiveNum = numbers.filter(number => number >= 0);

console.log(positiveNum);
```

### 15. Mapping an Array
```
const numbers = [2, -3, 1];

let multipleOf5 = numbers.map(num => num * 5);

let items = numbers
				.filter(n => n >= 0)
				.map(n => '<li>' + n + '</li>')
				.join('');

let objectMap = numbers.map(n => ({value : n}) );

console.log(multipleOf5); // [ 10, -15, 5 ]
console.log(items); // <li>2</li><li>1</li>
console.log(objectMap); // [ { value: 2 }, { value: -3 }, { value: 1 } ]
```

### 16. Reducing an Array
```
const numbers = [2, -3, 1, 10, 76];

const sum = numbers.reduce((accumulator, currentValue) => {
	return accumulator + currentValue;
}, 0);


const multiple = numbers.reduce((accumulator, currentValue) => {
	return accumulator * currentValue;
}, 1);

console.log(sum); // 86
console.log(multiple); // -4560
```

### 17. Exercise: Array from Range
```
const numbers = arrayFromRange(-10, 4);

console.log(numbers);  

function arrayFromRange(min, max) {
	let result = [];
	for (let i = min; i <= max; i++)
		result.push(i);
	return result;
}
```

### 18. Exercise: Includes
```
const numbers = [1, 2, 3, 4, 34];

function includes(numbers, searchElement) {
	for (let num of numbers)
		if (searchElement === num) return true;
	return false;
}

console.log(includes(numbers, 34));
```

### 19. Exercise: Except
```
const numbers = [1, 2, 3, 4, 1, 1];

const output = except(numbers, [1, 2]);

console.log(output); // [3, 4]

function except(array, excluded){
	const output = [];
	for (let element of array){
		if (!excluded.includes(element))
			output.push(element);
	}
	return output;
}
```

### 20. Exercise: an Element
```
const numbers = [1, 2, 3, 4];

const output = move(numbers, 1, 1);

console.log(output);

function move(array, index, offset){
	const position = index + offset;
	if (position >= array.length || position < 0) {
		console.error('Invalid offset...');
		return;
	}
	const output = [...array];
	const element = output.splice(index, 1)[0];
	output.splice(position, 0, element);
	return output;
}
```

### 21. Exercise: Count Occurrences
```
const numbers = [1, 2, 3, 4, 78, 1, 1, 78];

const count = countOccurrencesV2(numbers, 4);

console.log(count);

// One approach
function countOccurrences(array, searchElement){
	let result = 0;
	for (let elem of array){
		if (searchElement === elem)
		result++;
	}
	return result;
}

// Another approach with reduce funtion
function countOccurrencesV2(array, searchElement){
	return array.reduce((accumulator, current) => {
		const occurance = (current === searchElement) ? 1 : 0;
		return accumulator + occurance;
	}, 0)
}
```

### 22. Exercise: Get Max
```
const numbers = [1, 2, 3, 4, 78, 1, 1, 78];

const max = getMaxV2(numbers);  

console.log(max);

function getMax(array){
	return array.reverse()[0];
}

function getMaxV2(array){
	if (array.length === 0) return undefined;
	return array.reduce((a, b) => (a > b) ? a : b);
}
```

### 23. Exercise: Movies
```
const movies = [
	{ title: 'a', year: 2018, rating: 4.5 },
	{ title: 'b', year: 2018, rating: 4.7 },
	{ title: 'c', year: 2018, rating: 3 },
	{ title: 'd', year: 2017, rating: 4.5 },
]

// All the movies in 2018 with rating > 4
// Sort them by their rating
// Descending order
// Pick their title
const result = movies
					.filter(m => m.year === 2018 && m.rating > 4)
					.sort((a, b) => b.rating - a.rating)
					.map(m => m.title);

console.log(result);
```
