# history-of-ecmascript
Examples of new code previously impossible or difficult made possible with additions to ECMAScript in 2015 and beyond

## Running the examples
These examples are meant to be run in Node.js (where a folder contains no HTML files) or in a browser (where a folder contains HTML files).

## ES6 aka ES2015
### Concepts and Types
#### Iterators/Iterables
See [iterators.js](interfaces/iterators.js) for more examples.
#### Generators
See [generators.js](interfaces/iterators.js) for more examples.
#### BigInt
See [bigints.js](types/bigInts.js) for more examples.
#### Map
See [maps.js](types/maps.js) for more examples.
#### WeakMap
See [weakMaps.js](types/weakMaps.js) for more examples.
#### Set
See [sets.js](types/sets.js) for more examples.
#### WeakSet
See [weakSets.js](types/weakSets.js) for more examples.
#### Symbol
See [symbols.js](types/symbols.js) for more examples.
### Syntax Additions
#### Arrow Functions
Arrow functions in ES2015 are reminiscent of lambda expressions in .NET, if only in form. 
Old way:
```
[1,2,3,4].map(function(item) {
    return item * 2;
}); // [2,4,6,8]
```
With arrow functions:
```
[1,2,3,4].map(item => item * 2); // [2,4,6,8]
```
You can see how much more concise the code can be.
See [arrows.js](syntax/arrows.js) for more examples.

#### `for .. of` Loops
While on the subject of iteration, a new type of of loop was added, `for .. of`, which iterates over an [iterable](#iteratorsiterables) object.
Old way 1 (using normal indexed `for` loop)
```
var array = [1,2,3,4];
for (var i = 0, z = array.length; i < z; i++) {
    console.log(array[i]);
}
/*
logs:
1
2
3
4
*/
```
Old way 2 (using protected `for .. in` loop)
```
var array = [1,2,3,4];
for (var i in array) {
    // the following filter is needed so that properties like `length` are not enumerated also
    if (array.hasOwnProperty(i)) {
        console.log(array[i]);
    }
}
/*
logs:
1
2
3
4
*/
```
New way
```
const array = [1,2,3,4];
for (let item of array) {
    console.log(item);
}
/*
logs:
1
2
3
4
*/
```
See [for-of.js](syntax/for-of.js) for more examples.
