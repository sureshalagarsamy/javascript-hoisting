# JavaScript Hoisting

Consider the following code:


```javascript
var myvar = 'my value'; 
alert(myvar); // my value
```

of course the alert will display “my value” Let’s next create an immediate function, which alerts the same value.

```javascript
var myvar = 'my value'; 
  
(function() { 
  alert(myvar); // my value 
})();
```

All right,again the output will be the same “my value”.

Now let's see some tricky code

  var myvar = 'my value'; 

```javascript
(function() { 
  alert(myvar); // undefined 
  var myvar = 'local value'; 
})();
```

Huh? Why is the alert now displaying undefined?

##### Variable Declarations are Hoisted

Within its current scope, regardless of where a variable is declared, it will be, behind the scenes, hoisted to the top. However, only the declaration will be hoisted. If the variable is also initialized, the current value, at the top of the scope, will initially be set to undefined.

* Declaration
```javascript
var suresh; // the declaration
```
* Initialization

```javascript
suresh = 'Developer'; // the initialization
```
Now that we understand the terminology, Consider the following code

```javascript
(function() { 
  var a = 'a'; 
  // lines of code 
  var b = 'b'; 
  // more lines of code 
  var c= 'c';
  // final lines of scripting 
})();
```
Behind the scenes, all the above variable declarations will be hoisted to the top.

>Declare all variables at the top.

```javascript
(function() { 
  var a, b, c; // variables declared 
  a = 'a'; 
  // lines of code 
  b = 'b'; // initialized 
  // more lines of code 
  c= 'c'; // initialized 
  // final lines of scripting 
})();
```

<b>It should now make perfect sense why 'myvar' is alerting 'undefined'.</b>


