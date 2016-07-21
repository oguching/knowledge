# Currying

Currying is where a function expects a certain amount of arguments and if provided with less, 
it returns another function that is awaiting the remaining arguments. Only once it receives all 
expected arguments does a result get returned. If provided with the expected amount of arguments 
all at once it works as normal and returns a result.

```JavaScript
const curry = require('lodash/fp/curry');

const greet = curry((greeting, name) => `${greeting}, ${name}!`);

// Passing both arguments allows the function to work as normal
greet('Hello', 'Simon'); // Hello, Simon!

// Passing fewer however, returns another function
const sayBye = greet('See ya');

// And once it receives all its arguments, it returns a value
sayBye('John'); // See ya, John!;
```

References:
* https://simonsmith.io/dipping-a-toe-into-functional-js-with-lodash-fp/#a-delicious-curry
