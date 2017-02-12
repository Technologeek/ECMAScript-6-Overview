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

