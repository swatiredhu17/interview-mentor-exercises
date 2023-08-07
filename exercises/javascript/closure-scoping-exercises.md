# JS Closures / Scoping exercises

1. 
```
  function outerFunction() {
    var outerVariable = "Hi, ";
    function innerFunction(name) {
    console.log(outerVariable + name);  // What is logged?
  }
    return innerFunction;
  }

  var inner = outerFunction();
  inner("Closure");
 ```

2. 
```
  function outer() {
    var x = 10;
    function inner() {
      console.log(x);  // What is logged?
    }
    return inner;
  }
  var innerFunc = outer();
  innerFunc();
```

3. 
```
  function outer() {
    var x = 10;
    function inner() {
      console.log(x);  // What is logged?
    }
    var x = 20;
    return inner;
  }
  var innerFunc = outer();
  innerFunc();
```

4. 
```
  function outer() {
    var x = 10;
    function inner() {
      var y = 12;
      console.log(x+y); // What is logged?
    }
    return inner;
  }
  var innerFunc = outer();
  innerFunc();
```

5. What’s the result of executing this code and why.
  ```
  function test() {
     console.log(a);
     console.log(foo());
     
     var a = 1;
     function foo() {
        return 2;
     }
  }
  
  test();
  ```

6. What is result?
  ```
  var a = 1; 
  
  function someFunction(number) {
    function otherFunction(input) {
      return a;
    }
    
    a = 5;
    
    return otherFunction;
  }
  
  var firstResult = someFunction(9);
  var result = firstResult(2);
  ```

7. What is the result of the following code? Explain your answer.
  ```
  var fullname = 'John Doe';
  var obj = {
     fullname: 'Colin Ihrig',
     prop: {
        fullname: 'Aurelio De Rosa',
        getFullname: function() {
           return this.fullname;
        }
     }
  };
  
  console.log(obj.prop.getFullname());

  var test = obj.prop.getFullname;
  
  console.log(test());
  ```

8. What will you see in the console for the following example?
  ```
  var a = 1; 
  function b() { 
      a = 10; 
      return; 
      function a() {} 
  } 
  b(); 
  console.log(a);    
  ```
