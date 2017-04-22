`NaN` is a type of value in JavaScript. It stands for Not a Number and can be quite a pain to work with and causes weird, wonderful bugs.

`NaN` is the only value in JavaScript that does not equal to itself.Num

```JavaScript 
  NaN === NaN  //=> false
  NaN == NaN   //=> false
  
  // NaN is a number type
  typeof NaN //=> Number
  
  Number.isNaN(NaN)  //=> true
```
