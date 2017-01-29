`undefined`

In JavaScript, the absence of a value is written as `undefined`, and it means there is no value. Undefined is a value type, which means it is `===` to itself.

```JavaScript
  undefined === undefined
  //=> true
```
Any function that has no expression after the `return` keyword returns `undefined`.

```JavaScript
  var isUndefined = function() {
    return
  }
  
  undefined === isUndefined()
  //=> true
```
JavaScript assigns `undefined` to arguments[1] of a functions if you pass too few parameters. For example, if a function expects 3 parameters and you pass in 1 argument, the other 2 parameters will be assigned `undefined`. 

[1] [Argument vs Parameter](https://stackoverflow.com/questions/3176310/difference-between-parameter-and-argument#3176321)
