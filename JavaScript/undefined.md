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
