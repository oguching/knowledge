Lexical scope is the name given to scope in JavaScript. Scope describes level of access. If you live in a house,
you have immediate access to everything in that house. In JavaScript, each function has its own scope. Only code
inside a function can access that function's scoped variables.

Lexical scope rules say that code in one scope can access variables of either that scope or any scope outside of it.
In the code below, `TAX_RATE` is accessible inside the function `calculateFinalPurchaseAmount` because of lexical scope.

```JavaScript
  const TAX_RATE = 0.08
  
  function calculateFinalPurchaseAmount(amt) {
	// calculate the new amount with the tax
  	amt = amt + (amt * TAX_RATE)

	  // return the new amount
	  return amt;
}
```
