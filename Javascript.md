# Javascript Notes 

MDN Docs
https://developer.mozilla.org
https://www.w3schools.com
FreeCodeCamp
https://javascript.info

https://www.freecodecamp.org/news/10-javascript-libraries-you-should-try/

https://en.wikipedia.org/wiki/List_of_JavaScript_libraries

https://en.m.wikipedia.org/wiki/Comparison_of_JavaScript-based_web_frameworks

https://www.freecodecamp.org/news/learn-javascript-free-js-courses-for-beginners/#learn-javascript-full-course-for-beginners

https://www.freecodecamp.org/news/how-to-use-javascript-collections-map-and-set/

https://www.freecodecamp.org/news/javascript-projects-for-beginners/#how-to-create-a-video-background

https://www.geeksforgeeks.org/top-10-javascript-frameworks-to-learn-in-2021/

Keywords
Block Scopes 

XmlHttpRequest  & Fetch API
Async and Defer attribute for script loading ( asset loading )
Js APIs 
 
Data types & their conversions
Number
number for numbers of any kind: integer or floating-point, integers are limited by ±(253-1).
BigInt ( n )
bigint for integer numbers of arbitrary length
String
string for strings. A string may have zero or more characters, there’s no separate single-character type
Null
null for unknown values – a standalone type that has a single value null.
Undefined
undefined for unassigned values – a standalone type that has a single value undefined.
Boolean
boolean for true/false.
Objects
object for more complex data structures.
Symbols
symbol for unique identifiers.

For getting Number type from string type 
parsesInt()
parseFloat()

Typeof operator
typeof operator allows us to see which type is stored in a variable.

Variables
Variables and variables hoisting 
let vs var vs const 
var 
             functionally scoped
             var variable is hoisted 
             var variable can be redeclared 
let/const 
             block scoped
             let/const varaible is not hoisted 
             let/const varaible can't be redeclared 
             const variable can be reassigned as well 
             but we can modify properties of objects 
             declared with const

let variable = null || " value "
|| returns the first truthy value.
?? returns the first defined value.
Null coalescing 
?? returns the first argument if it’s not null/undefined. Otherwise, the second one.
​let user;
alert(user ?? "Anonymous"); // Anonymous (user not defined)

let variable = null ?? " value "
  
Maths functions 

Date Functions  
https://www.freecodecamp.org/news/javascript-date-format-how-to-format-a-date-in-js/
To create a new Date object call new Date() with one of the following arguments:

new Date()
Without arguments – create a Date object for the current date and time:

let now = new Date();
alert( now ); // shows current date/time

getFullYear()
getMonth() 
getDate()
getHours(), getMinutes(), getSeconds(), getMilliseconds()
getDay()
getTime()

Loops 
for 
for / in 
for / of 
​while
​do while 
do {
  // loop body
} while (condn);

break , continue

Conditionals
If - else 
If - elseif - else 
Switch 
let a = 2 + 2;
switch (a) {
  case 3:
    alert( 'Too small' );
    break;
  case 4:
    alert( 'Exactly!' );
    break;
  case 5:
    alert( 'Too big' );
    break;
  default:
    alert( "I don't know such values" );
}
​Ternary operator ( condn ? Good : Bad ; )

let age = prompt('age?', 18);
let msg = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';
alert( msg );

Error Handling 
try{} 
catch() {} 
finally{} 
throw
Error Object

Objects
An object is created with curly braces {} and a list of properties. A property is a key-value pair where the key must be a string and the value can be of any type.

 Regular JS object always treats the key as a string. Even when you pass it a primitive or object, it internally converts the key into a string.

let user = new Object();
// "object constructor" syntax
let user = {}; 
 // "object literal" syntax

let user = {     // an object
  name: "John",  
// by key "name" store value "John"
  age: 30       
 // by key "age" store value 30
};

delete // operator
delete user.age;

For .. in
To walk over all keys of an object, there exists a special form of the loop: for..in.

for (key in object) {
  // runs the body for each key among object properties
}
Object.values(obj)
Object.keys(obj)
Object.entries(obj)


Arrays [ ] 
​Creation 
​Slicing 
​inserting , pushing ( push() or rest operator )
​removing , poping 
​removing multiple elements using splice()
​concatenating ( concat() , spread operator )
​merging arrays 
​copying arrays ( [ ...rest ] , Array.from() )
​array Methods 
​chaining array Methods 
​objects to arrays 
​arrays to objects 
Array Methods 
https://www.freecodecamp.org/news/the-javascript-array-handbook/
Filter 
Map
Find 
​Foreach 
​Sum
​Every
​Reduce 
​Includes 
Objects { }
Arrays vs Sets 
Objects vs Maps 

Maps & Sets
https://www.freecodecamp.org/news/how-to-use-javascript-collections-map-and-set/

Maps 
Map is a collection of keyed data items, just like an Object. But the main difference is that Map allows keys of any type.

Methods and properties are:

new Map() – creates the map.
map.set(key, value) – stores the value by the key.
map.get(key) – returns the value by the key, undefined if key doesn’t exist in map.
map.has(key) – returns true if the key exists, false otherwise.
map.delete(key) – removes the value by the key.
map.clear() – removes everything from the map.
map.size – returns the current element count

let m = new Map();

m.set('1', 'str1');   // a string key
m.set(1, 'num1');     // a numeric key
m.set(true, 'bool1'); // a boolean key

// remember the regular Object? it would convert keys to string
// Map keeps the type, so these two are different:
alert( map.get(1)   ); // 'num1'
alert( map.get('1') ); // 'str1'
alert( map.size ); // 3

const newmap = new Map([
  ['name', 'freeCodeCamp'],
  ['type', 'blog'],
  ['writer', 'Tapas Adhikary'],
]);

Iteration over Map
map.keys() – returns an iterable for keys,
map.values() – returns an iterable for values,
map.entries() – returns an iterable for entries [key, value], it’s used by default in for..of

m.forEach((val , key) => {
   console.log(` ${key} : ${val}` )
})

for(const [key, value] of m) {
  console.log(`${key} is ${value} years old!`);
}

Object to Map
const address = {
  'Tapas': 'Bangalore',
  'James': 'Huston',
  'Selva': 'Srilanka'
};
const map1 = new Map(Object.entries(address));

Map to Object 
Object.fromEntries(map)

let m = new Map();
m.set('banana', 1);
m.set('orange', 2);
m.set('meat', 4);

let obj = Object.fromEntries(m.entries()); 
// make a plain object 

// obj = { banana: 1, orange: 2, meat: 4 }
alert(obj.orange); // 2

Map to Array
Using Array.from(map):
console.log(Array.from(map));
Using the spread operator:
console.log([...map]);

Sets
A Set is a special type collection – “set of values” (without keys), where each value may occur only once.
Its main methods are:

new Set(iterable) – creates the set, and if an iterable object is provided (usually an array), copies values from it into the set.
set.add(value) – adds a value, returns the set itself.
set.delete(value) – removes the value, returns true if value existed at the moment of the call, otherwise false.
set.has(value) – returns true if the value exists in the set, otherwise false.
set.clear() – removes everything from the set.
set.size – is the elements count.

let s = new Set();

let john = { name: "John" };
let pete = { name: "Pete" };
let mary = { name: "Mary" };

s.add(john);
s.add(pete);
s.add(mary);
s.add(john);

// set keeps only unique values
alert( s.size ); // 3

const h = new Set([360, 567, 101]);

// Get the SetIterator using the `values()` method
console.log(h.values())
console.log(h.keys())
// returns values only since there is no keys in Set
console.log(h.entries())

h.forEach((val) => {
   console.log(val);
});

for(const value of h) {
   console.log(value);
 }

Set to Array 
let arr = [...h]
log(arr)

Functions
https://www.freecodecamp.org/news/javascript-function-iife-parameters-code-blocks-explained/
function show() {
  alert( 'Hello!' );
}
Parameters
Default Values 
function show(from, text = "no text given") {
  alert( from + ": " + text );
}
show("Ann"); // Ann: no text given

Return
A function with an empty return or without it returns undefined

Arrow Functions
() => // Single statement 
() => { }
(param1, param2 , ....) => { 
 // Code 
}
Returning 
Arrays
Objects
​Maps
​Sets
Primitive Data Types 

JSON
JSON.stringify()
JSON.parse()


Js Browser APIs 
FileReader Api
Media recorder
StreamRecorder
Geolocation Api
https://www.freecodecamp.org/news/how-to-get-user-location-with-javascript-geolocation-api/
Intersection Observer 
Mutation Api
Fetch Api 

let res = await fetch(url);

if (res.ok) { 
   // if HTTP-status is 200-299
  // get the res body (the method explained below)
  let json = await res.json();
} else {
  alert("HTTP-Error: " + res.status);
}

​Notification Api

Service workers 
Blobs
Classes and inheritance 
DOM Object ( window object )
BOM

DOM Access
document.getElementById()
document.getElementsByTagname()
document.getElementsByClassname()
document.querySelector()
document.querySelectorAll()

DOM Traversal
.parentNode
.childNodes // a collection – a special array-like iterable object.
.firetChild  , .lastChild  , .nextSibling , .previousSibling , .nodeName
parentElement, children, firstElementChild, lastElementChild, previousElementSibling, nextElementSibling. 

DOM manipulation
.innerHTML
.innerText
.textContent
document.createElement()

Attributes
.hasAttribute(name) , .getAttribute(name).
.setAttribute(name,value)  , .removeAttribute(name)

Old
.appendChild() 
.insertBefore(node, nextSibling) 
insertAfter()
.replaceChild(node, oldChild) 
removeChild(node) 

Adding Elements
.append() // adds element within the element at the end
.prepend()  // adds element within the element at the beginning 
.after()  // adds element outside the element at the end
.before()  // adds element outside the element at the beginning 
.insertAdjacentHTML(where, html)
beforebegin" – insert html immediately before elem,
"afterbegin" – insert html into elem, at the beginning,
"beforeend" – insert html into elem, at the end,
"afterend" – insert html immediately after elem
. insertAfter entreat (where, html)
.insertAdjacentElement(where, html)

.replacewith()
.remove()
.cloneNode()
The call elem.cloneNode(true) creates a “deep” clone of the element – with all attributes and subelements. If we call elem.cloneNode(false), then the clone is made without child elements.
​
CSS
.className
.classList // returns array 
.classList.add/remove("class") 
.classList.toggle("class") 
.classList.contains("class") 
.style
.style.removeProperty()
getComputedStyle(element, [pseudo])
element

Prompt() , Confirm() , Alert()
setInterval() and setTimeout()
Closures 
Lexical Scoping 
Regex 

Storage 
document.cookies 
LocalStorage
SessionStorage
IndexedDB

ES6
Arrow Functions , Anonymous Functions and IIFE
And default attributes 
Destructing arrays and objects 
Spread and rest operator 
Promises and callbacks and async/await
Iterators and Generators
Maps and Sets
Template Literals ( ` ` )

ES2020 
BigInt
Optional Chaining

ES2021

DOM Events
DOMContentloaded
Load
Beforeunload
Unload
Onload
Onerror

Event Propagation Model
Bubbling 
Capturing 
Event Delegation 
e.target
e.currentTarget 
e.type
e.preventDefault()
e.stopPropagation()
event.target to get the element that was the target of the event (that is, the innermost element). If we wanted to access the element that handled this event ,  we could use event.currentTarget.

Import / Export modules 
AJAX 

jQuery 
https://jquery.com
https://www.w3schools.com/jquery/default.asp


Nodejs and Express ( Backend )
https://nodejs.org/en
https://expressjs.com/en/starter/installing.html

MongoDB or Redis OR MySQL

Frontend
React
Reactjs.org
Bootstrap 
https://getbootstrap.com/
https://getbootstrap.com/docs/5.1/examples/


Unit Testing framework ( Jest , Mocha , vitest ) 
Cypress
