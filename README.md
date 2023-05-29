# Javascript Interview Questions And Answers

Most targeted up-to-date JavaScript interview questions and answers list

# Table of Contents

1. [What is a closure in JavaScript? Provide an example.](#1-what-is-a-closure-in-javascript-provide-an-example)
2. [What is the difference between null and undefined in JavaScript? Provide examples.](#2-what-is-the-difference-between-null-and-undefined-in-javascript-provide-examples)
3. [What is the this keyword in JavaScript? Provide examples of its different uses.](#3-what-is-the-this-keyword-in-javascript-provide-examples-of-its-different-uses)
4. [What are Promises in JavaScript? Provide an example of using Promises.](#4-what-are-promises-in-javascript-provide-an-example-of-using-promises)
5. [What is the difference between == and === operators in JavaScript? Provide examples.](#5-what-is-the-difference-between--and--operators-in-javascript-provide-examples)
6. [Explain event delegation in JavaScript. Provide an example.](#6-explain-event-delegation-in-javascript-provide-an-example)
7. [What are higher-order functions in JavaScript? Provide an example.](#7-what-are-higher-order-functions-in-javascript-provide-an-example)
8. [What is the difference between let, const, and var in JavaScript? Provide examples.](#8-what-is-the-difference-between-let-const-and-var-in-javascript-provide-examples)
9. [What is the concept of prototypal inheritance in JavaScript? Provide an example.](#9-what-is-the-concept-of-prototypal-inheritance-in-javascript-provide-an-example)
10. [Explain the concept of event bubbling and event capturing in JavaScript. Provide an example.](#10-explain-the-concept-of-event-bubbling-and-event-capturing-in-javascript-provide-an-example)
11. [How does JavaScript handle asynchronous operations? Provide an example using setTimeout.](#11-how-does-javascript-handle-asynchronous-operations-provide-an-example-using-settimeout)
12. [What is the typeof operator in JavaScript? Provide examples.](#12-what-is-the-typeof-operator-in-javascript-provide-examples)
- [Whats more?](#whats-more)
- [Contributing](#contributing)
- [License](#license)

## 1. What is a closure in JavaScript? Provide an example.

```javascript
function outerFunction() {
  var outerVariable = 'I am outside!';

  function innerFunction() {
    console.log(outerVariable);
  }

  return innerFunction;
}

var closure = outerFunction();
closure(); // Output: I am outside!
```

## 2. What is the difference between null and undefined in JavaScript? Provide examples.

```javascript
var nullVariable = null;
console.log(nullVariable); // Output: null

var undefinedVariable;
console.log(undefinedVariable); // Output: undefined
```

## 3. What is the this keyword in JavaScript? Provide examples of its different uses.

```javascript
// Implicit binding
var person = {
  name: 'John',
  sayHello: function() {
    console.log('Hello, ' + this.name);
  }
};
person.sayHello(); // Output: Hello, John

// Explicit binding
function greet() {
  console.log('Hello, ' + this.name);
}

var person1 = { name: 'John' };
greet.call(person1); // Output: Hello, John

// Arrow functions
var greetArrow = () => {
  console.log('Hello, ' + this.name);
};

var person2 = { name: 'Jane' };
greetArrow.call(person2); // Output: Hello, undefined
```

## 4. What are Promises in JavaScript? Provide an example of using Promises.

```javascript
function fetchData() {
  return new Promise(function(resolve, reject) {
    setTimeout(function() {
      resolve('Data fetched successfully!');
    }, 2000);
  });
}

fetchData().then(function(data) {
  console.log(data); // Output: Data fetched successfully!
});
```

## 5. What is the difference between == and === operators in JavaScript? Provide examples.

```javascript
console.log(1 == '1'); // Output: true (loose equality)
console.log(1 === '1'); // Output: false (strict equality)
```

## 6. Explain event delegation in JavaScript. Provide an example.

```javascript
// HTML
<ul id="list">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

// JavaScript
document.getElementById('list').addEventListener('click', function(event) {
  if (event.target.tagName === 'LI') {
    console.log('Clicked on', event.target.textContent);
  }
});
```

## 7. What are higher-order functions in JavaScript? Provide an example.

```javascript
function doOperation(operation) {
  return function(a, b) {
    return operation(a, b);
  };
}

var sum = doOperation(function(a, b) {
  return a + b;
});

console.log(sum(2, 3)); // Output: 5
```

## 8. What is the difference between let, const, and var in JavaScript? Provide examples.

```javascript
let variable1 = 'Value 1'; // Block-scoped variable
const variable2 = 'Value 2'; // Block-scoped constant
var variable3 = 'Value 3'; // Function-scoped variable

variable1 = 'New Value 1';
variable2 = 'New Value 2'; // Error: Assignment to constant variable
variable3 = 'New Value 3';

console.log(variable1); // Output: New Value 1
console.log(variable2);
console.log(variable3); // Output: New Value 3
```

## 9. What is the concept of prototypal inheritance in JavaScript? Provide an example.

```javascript
function Vehicle(make, model) {
  this.make = make;
  this.model = model;
}

Vehicle.prototype.getDetails = function() {
  return this.make + ' ' + this.model;
};

var car = new Vehicle('Toyota', 'Camry');
console.log(car.getDetails()); // Output: Toyota Camry
```

## 10. Explain the concept of event bubbling and event capturing in JavaScript. Provide an example.

```javascript
// HTML
<div id="parent">
  <div id="child">
    Click me
  </div>
</div>

// JavaScript
document.getElementById('parent').addEventListener('click', function() {
  console.log('Parent clicked');
}, true); // Use capture phase

document.getElementById('child').addEventListener('click', function() {
  console.log('Child clicked');
}, false); // Use bubbling phase

// Output: Child clicked, Parent clicked
```

## 11. How does JavaScript handle asynchronous operations? Provide an example using setTimeout.

```javascript
console.log('Start');

setTimeout(function() {
  console.log('Async operation executed');
}, 2000);

console.log('End');

// Output:
// Start
// End
// Async operation executed (after 2 seconds)
```

## 12. What is the typeof operator in JavaScript? Provide examples.

```javascript
console.log(typeof 42); // Output: number
console.log(typeof 'Hello'); // Output: string
console.log(typeof true); // Output: boolean
console.log(typeof undefined); // Output: undefined
console.log(typeof null); // Output: object
console.log(typeof {}); // Output: object
console.log(typeof []); // Output: object
console.log(typeof function() {}); // Output: function
```

## What's more?
<a href="https://interviewplus.ai/developers-and-programmers/javascript/questions">A comprehensive list of questions and answers</a>

## Contributing
We welcome contributions from our users to help make this resource as comprehensive and useful as possible. If you have been recently interviewed and encountered a question that is not currently covered on our website, feel free to suggest it as a new question. Your contributions will be added to our platform, and we will make sure to credit you for your contributions. We appreciate your help in making our platform a valuable tool for all job seekers.

## License
MIT License
