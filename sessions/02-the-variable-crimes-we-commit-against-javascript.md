# The Variable Crimes We Commit Against JavaScript
## scope
* No `var`/`let`/`const` assigns to `window`/`global`
* Functions create a new scope
  * Child functions have a scope that inherits from the parent scope
* `var` only scopes to functions while `let`/`const` scopes to _blocks_

## types of functions
* function statement (named function)
* function expression

## hoisting
* `var` definitions are hoisted to the top of their scope
  * As `var thing = 5;`, it's split into hoisted definition (`var thing;`) and in-place assignment (`thing = 5`)
* Function statements (named functions) are hoisted to the top of the scope

## closure
(Nowhere near enough detail on this.)

## arrays & objects
* Objects and arrays are dealt with by reference

## es6
* `let`/`const` to array/object makes a constant reference, not a constant array/object
* `let`/`const` scope to _blocks_, including for-loop variables
* It is possible to create an anonymous block
