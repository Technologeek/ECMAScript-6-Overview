> Work In Progress

# ECMAScript-6-Overview
This Page is not a in-depth guide but a quick reference document.I've tried to keep it as simple as possible.
### Some useful links to get started with understanding ECMAScript
[What is ECMAScript?](https://www.eventedmind.com/classes/es2015-ee192682/what-is-ecmascript-30df1288)

[ECMAScript Compatibility table](https://kangax.github.io/compat-table/es6/)

[ECMAScript 6 Tutorial](http://ccoenraets.github.io/es6-tutorial/)
### Overview of ECMAScript Features
#####  *New keywords constant and let*
- #### **Constants**
##### Immutable Variables- Variables which cannot be re-assigned new content.However,the content in which the constant is defined can still be altered.
```javascript
constant value = 27;
value = 30; //Doesn't change the value
console.log(value);
//
constant Obj = {
  value = 30;
}
Obj.value = 35; //Changes the value
console.log(Obj);
```
- #### **let** (Used for Block-Scoping )
##### let could be used just like var, except it supports block-scoping
```javascript
if(true_condition){
let age = 30;
}
console.log(age); //Throws ReferenceError: age is not defined
//
if(true_condition){
let age = 30;
console.log(age); //Returns 30
}
```
- #### **Arrow Functions** (coolest feature yet!)
```javascript
//General Function
function fx(){
console.log("Hello")
}
fx();

//Arrow'izing it as ES6 standards
var fx = () => console.log("Hello");
fx();

//If function returns something,
var fx = () => "Hello";
console.log(fx());

//Works great with arguments too!
var fx = (a,b) => a+b;
console.log(fx(3,5)); //Returns 8
```
- #### **Default Parameters**
##### Simple way of declaring default paramters inside the functions.
```javascript
//Traditional way
function IsEqualTo(number1,number2) {
return number1 == number2;
}
console.log(IsEqualTo(10,10)); //Logs true

//Doing this Es6 way (giving values for default parameters)
var IsEqualTo = (number1=10,number2=12) =>number1 == number2;
console.log(IsEqualTo()); //Logs false

//You can play around by passing values for different parameters
var IsEqualTo = (number1,number2=12) => number1 == number2;
console.log(IsEqualTo(12)); //Logs True
```

- #### **Rest Parameter**
According to the definition from  ECMAScript 6 

> Aggregation of remaining arguments into single parameter of variadic functions.

Bouncer ? Let me simplify that!
##### Rest Paramter allows you to pass dynamic values as arguments.

```javascript
//Function to add numbers in an pre-defined array
var numbers = [12,13,14,15];
function addNumbers(numberArray){
  var result = 0;
  for(var i = 0; i<numberArray.length; i++){
     result+=numberArray[i];
  }
  return result;
}
console.log(addNumbers(numbers)); //Logs 54, but hey don't you wish there was a easier way to pass dynamic values as arguments instead of the predefined array ? With ES6,you can!

//Let's write the same function using Rest Parameter or (...) opeartor! (Yes,three dots!)
function addNumbers(...numberArray){
  var result = 0;
  for(var i = 0;i<numberArray.length;i++){
     result+=numberArray[i];
  }
  return result;
}
console.log(addNumbers(15,16,17,18)); //Logs 66
console.log(addNumbers(12,136,1,13)); //Logs 162 
```
#### Extended Parameter Handling
> Spreading of elements of an iterable collection (like an array or even a string) into both literal elements and individual function parameters.

In short words,spread operator is opposite of rest parameter.Quite self-explianatory if you read [this page.](http://es6-features.org/#SpreadOperator)

- #### **Template Literals**
##### Also known as template strings,provides a better way of handling in-string manipulations.Though it may sound complicated but it actually isn't.

> Template string uses `` literal around the content.I don't know the official name for it,but let's call it the back-tick for now.

```javascript
//Traditional way
var employee = { name: "Foo" };
var emp_details = { days: 30, dept: "Admin", salary: 420 };
//Printing employee details with the given data
var details = "Hello " + employee.name + ",\n" + "your salary for 30 days is " +
(emp_details.days * emp_details.salary) + " rupees" ;
console.log(details); //Logs "Hello Foo, your salary for 30 days is 12600 rupees"

//Using Template String 
var employee = { name: "Foo" }
var emp_details = { days: 30, dept: "Admin", salary: 420 }
//Check the back-tick before "Hello" and after "rupees"
var details = `Hello ${employee.name},your salary for 30 days is ${emp_details.days * emp_details.salary} rupees`
console.log(details); //Logs "Hello Foo, your salary for 30 days is 12600 rupees"
```
>Less messey right ? If you're used to server side processing languages like SASS you would know how convinient it is to use interpolation that is "${ }" for slotting values into other values.
