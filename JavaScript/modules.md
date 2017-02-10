Modules help us break code into smaller, relatively self-contained pieces that make a project more managable.

Exports:  
```JavaScript
  exports.area = function (width) { 
    return width * width; 
  };
  exports.perimeter = function (width) { 
    return 4 * width; 
  };
```

module.exports:
```JavaScript
 module.exports = {
  area: function(width) {
    return width * width;
  },
       
  perimeter: function(width) {
    return 4 * width;
  }
};
```
