<h2>Javascript</h2>

<b>Ref</b><br />
https://github.com/sudheerj/javascript-interview-questions#what-are-pwas?

1. Javasctipt developed by Netscape 1995, initially was used in netscape browser,
2. Advantages of JS.
3. Javascript Hoisting.
    Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution. Remember that JavaScript only hoists     declarations, not initialisation. Let's take a simple example of variable hoisting,
        
    ```
    num = 5;
    console.log(num);
    var num;
    ```
4. Strict Mode
5. Self - invoking functions (or) Anonymous functions
    ```
    (function() {
      console.log('Hello World')
    })
    ```
6. Var, let and const
7. Difference between == & ===
8. Difference null & undefined
9. Difference Function declaration & Function expression
10. Closure<br />
  
    A closure is the combination of a function and the lexical environment within which that function was declared. i.e, It is an inner function that has access to the outer or     enclosing function’s variables. The closure has three scope chains<bt />
      1. Own scope where variables defined between its curly brackets
      2. Outer function’s variables
      3. Global variables

12. For-in loop
13. Event bubbling & Event Capturing
14. JS and ECMA
15. Cookie Creation in js
16. Diff b/w getElementsById, querySelector, querySelectorAll
17. Diff b/w Async & differ
18. Diff b/w Shift() & push()
19. new & this Operator
    The new operator is used to construct a user-defined object from a function.
    ```
    function displayName(name) {
      this.name = name
    }
    var obj = new displayName('JS');
    console.log(obj.name)
    ```
19. What is this keyword in JavaScript?
    this refers to the object that is bind to the function at the runtime
    
    <b>Default Binding : </b> This happens when a function is invoked in stand alone.
    ```
    num = 5;
    function pritNo() {
      console.log(this.num);
    }
    ```
    here this resolves to the global object window. So window.num yields 5 here.
    
    <b>Implicit Binding : </b> when the function has a context-object, this resolves to the owning object or containing object.
    ```
    num = 5;
    function pritNo() {
      console.log(this.num);
    }
    var obj = {
      num = 9;
      pritNo : pritNo
    }
    obj.pritNo(); // res is 9
    ```
    
    <b>Explicit binding : </b> By this way we are forcing a function to use an object to resolve the this. This can be achieved by using call and apply.
    
    ```
    function printNum() {
      console.log(this.num)
    }
    var obj = {
      num = 6;
    }
    printNum.call(obj)
    ```
    
    <b>new Binding</b> : The new binding is invoked when the function is invoked with new keyword.
     ```
     function Person (name) {
      this.name = name;
     }
     var person = new Person('Sharan')
     console.log(this.name)
    ```
    
20. Best practices for writing JavaScript Code\n
    a. Always initialize the variables before you use them.
    b. Always use === equals instead of ==.
    c. Wrapping code that could thrown errors at run time and feature-based code in try...catch block.
    d. Don’t pollute global scope and don’t use global variables.
    e. Always use "use strict";.
    f. Use lint tools to validate JavaScript code and avoid any potential risks.
    g. Wrap your code in an anonymous function or Immediately Invoked Function Expressions (IIFE), so that it will affect the global scope.
    h. Give clear name for variables and functions.
    i. Give comments wherever needed so that the other developer understands the code better.

21. ECMA6 Features
    1. arrow function
    2. Template strings
    3. rest and spread operators
    4. Symbols data type
    5. Promises
    6. generators
    7. Multi-line Strings

22. AJAX
23. Callstack in JS : JavaScript’s functions forms a stack of frames. These are called Call Stack.
24. Possible ways to create objects in JavaScript
    ```
      1. Object constructor: var object = new Object();        
      2. Object's create method: var object = Object.create(null);        
      3. Object literal syntax : var object = {};
      4. Function constructor: 
         function Person(name){
           var object = {};
           object.name=name;
           object.age=21;
           return object;
        }
        var object = new Person("Sudheer");
      5. Function constructor with prototype:
      6. ES6 Class syntax: 
          class Person {
           constructor(name) {
              this.name = name;
           }
        }
        var object = new Person("Sudheer");
    ```

25. What is a prototype chain : Prototype chaining is used to build new types of objects based on existing ones. It is similar to inheritance in a class based language.
26. Difference b/w call, Apply & Bind
    
    <b>Call</b> : The call() method invokes a function with a given this value and arguments provided one by one
    ```
    var employee1 = {firstName: 'John', lastName: 'Rodson'};
    function invite(greeting1, greeting2) {
      console.log(greeting1 + ' ' + this.firstName + ' ' + this.lastName+ ', '+ greeting2);
    }
    invite.call(employee1, 'Hello', 'How are you?'); // Hello John Rodson, How are you?
    ```
    
    <b>Apply</b> : The Apply() method invokes a function with a given this value and arguments provided in Array
    ```
    var employee1 = {firstName: 'John', lastName: 'Rodson'};
    function invite(greeting1, greeting2) {
      console.log(greeting1 + ' ' + this.firstName + ' ' + this.lastName+ ', '+ greeting2);
    }
    invite.apply(employee1, ['Hello', 'How are you?']); // Hello John Rodson, How are you?
    ```
    
    <b>bind</b> : returns a new function, allowing you to pass any number of arguments
    ```
    var employee1 = {firstName: 'John', lastName: 'Rodson'};
    function invite(greeting1, greeting2) {
      console.log(greeting1 + ' ' + this.firstName + ' ' + this.lastName+ ', '+ greeting2);
    }
    var callEmp1 = employee1.bind(employee1);
    callEmp1('hi', 'how are yu');
    
27. What is JSON.
28. array slice method : The slice() method returns the selected elements in an array as a new array object
    ```
    let arrayIntegers = [1, 2, 3, 4, 5];
    let arrayIntegers1 = arrayIntegers.slice(0,2); // returns [1,2]
    ```
30. array splice method : The splice() method is used either adds/removes items to/from an array, and then returns the removed item. The first argument specifies the array           position for insertion or deletion whereas the optional second argument indicates the number of elements to be deleted 
31. Diff b/w slice & splice
32. Diff b/w Object & map
    a. The keys of an Object are Strings and Symbols, whereas they can be any value for a Map, including functions, objects, and any primitive.
    b. The keys in Map are ordered while keys added to Object are not. Thus, when iterating over it, a Map object returns keys in order of insertion.
    c. You can get the size of a Map easily with the size property, while the number of properties in an Object must be determined manually.
    d. A Map is an iterable and can thus be directly iterated, whereas iterating over an Object requires obtaining its keys in some fashion and iterating over them.a.
    
33.  What are lambda or arrow functions
34.  What is a first class function.
35.  What is a first order function.
36.  What is a higher order function
37.  What is a unary function.
38.  What is a pure function
39.  How do you redeclare variables in switch block without an error
     ```
     let counter = 1;
      switch(x) {
      case 0: {
        let name;
        break;
      }
      case 1: {
        let name; // No SyntaxError for redeclaration.
        break;
      }
      }
     ```
40. What is the Temporal Dead Zone
41. What is IIFE(Immediately Invoked Function Expression) : Primary reason to use this is, data privacy,  
42. What are classes in ES6.
43. What is a service worker<br />
    A Service worker is basically a script (JavaScript file) that runs in the background, separate from a web page and provides features that don't need a web page or user           interaction. Some of the major features<br />
    1. Rich offline experiences(offline first web application development)
    2. periodic background syncs
    3. push notifications
    4. intercept and handle network requests
    5. programmatically managing a cache of responses<br />
44. What is web storage
45. What is a Cookie <br /> 
    A cookie is a piece of data that is stored on your computer to be accessed by your browser<br />
    Cookies are used to remember information about the user profile(such as username). It basically involves two steps,<br />
      1. When a user visits a web page, the user profile can be stored in a cookie.
      2. Next time the user visits the page, the cookie remembers the user profile.
46. What is a promise.
47. Why do we need Promise.
48. What is Calback
49. Why do we need callback.
50. What is callback hell.
51. What are server-sent events : server push technology enabling a browser to receive automatic updates from a server via HTTP connection without resorting to polling
    ```
    if(typeof(EventSource) !== "undefined") {
      var source = new EventSource("sse_generator.js");
      source.onmessage = function(event) {
        document.getElementById("output").innerHTML += event.data + "<br>";
      };
    }
    ```
52. What is promise chaining
53. What is promise.all
54. Promise.race() method 
55. What is the purpose of double exclamation
56. What is the purpose of the delete operator
57. What is eval
58. What is the difference between window and document
59. How do you access history in javascript
60. How do you find operating system details : navigator.platform
61. Difference b/w document load and DOMContentLoaded events 
62. What is same-origin policy : The same-origin policy is a policy that prevents JavaScript from making requests across domain boundaries
63. What is the use of Void(0) :  is used to prevent the page from refreshing 
64. What is the use of preventDefault method : The preventDefault() method cancels the event if it is cancelable, meaning that the default action or behaviour that belongs to       the event will not occur
65. What are PWAs
66. What is the purpose of clearTimeout method
67. Difference b/w setTimeout() & setInterval().
68. How do you redirect new page in javascript : windows.location.href
69. How do you check whether a string contains a substring : string.includes('substring'), indexOf, regEx
70. How do you make first letter of the string in an uppercase : string.charAt(0).toUpperCase()
71. How do you display the current date in javascript
    ```
    var mydate = new Date();
    var currentMonth = mydate.getMonth() + 1;
    var time = mydate.getHours() + ":" + mydate.getMinutes() + ":" + mydate.getSeconds();
    console.log(mydate.getDate() + "/" + currentMonth + "/" + mydate.getFullYear() + " " + time);
    ```
72. What is the way to find the number of parameters expected by a function : function.length() -> gives the no of parameters expected by the function
73. What is a polyfill : A polyfill is a piece of JS code used to provide modern functionality on older browsers that do not natively support it
74. How do you generate random integers : Math.floor(Math.random() * 10) + 1;     // returns a random integer from 1 to 10
75. What is tree shaking
76. What is a freeze method<br />
    The freeze() method is used to freeze an object. Freezing an object does not allow adding new properties to an object,prevents from removing and prevents changing the           enumerability, configurability, or writability of existing properties , obj.isFrozen() is used to check the weather object is froze or not <br />
    ```
    const obj = {
      prop: 100
    };

    Object.freeze(obj);
    obj.prop = 200; // Throws an error in strict mode

    console.log(obj.prop); //100
    ```
77. What is a rest parameter : Rest parameter is an improved way to handle function parameters which allows us to represent an indefinite number of arguments as an array. and        The rest parameter should be the last argument
    ```
    function total(…args){
    let sum = 0;
    for(let i of args){
    sum+=i;
    }
    return sum;
    }
    console.log(fun(1,2)); //3
    console.log(fun(1,2,3)); //6
    ```
78. How do you copy properties from one object to other : Object.assign(target, ...sources)
79. Object.seal() : used to seal an object, by preventing new properties from being added to it and marking all existing properties as non-configurable. But values of present properties can still be changed. Object.isSealed() method is used to determine if an object is sealed or not.
80. What are the differences between Obfuscation and Encryption<br /><br /><br />


<h2>Node.Js</h2>

1. 
