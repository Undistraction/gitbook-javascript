# Key Functional Techniques

## Map

Array.prototype.map allows you to iterate over an array and perform an action on each item, returning the result from each iteration. The array returned from the function will be the same length as the array it was called on.

```
const a = [1, 2, 3];

const b = a.map((x) => x * 2);

b // [2, 4, 6]
```

## Filter

Array.prototype.filter allows you to iterate over an array and decide which items should be included in a new array.

```
const a = [1, 2, 3, 5];

// value is even
const b = a.filter((x) => x % 2 == 0);

b // [2, 4]
```

## Reduce

Array.prototype.reduce allows you to iterate over an array, passing a function that takes the value returned from the last iteration and the current item and return a single value that will be passed into the next iteration. The function ultimately returns a single value accumulated from all the values.

```
const a = ['A', 'B', 'C'];

const b = a.reduce((x, y) => x + y);

b; // ABC
```

If using object properties for comparison, the object itself can be accumulated rather than the value of the property, allowing the array to be reduced to an object rather than a derived value:

```
const a = [{value: 6}, {value: 2}, {value: 4}];
const b = a.reduce((x, y) => y.value > x.value ? y : x );

b; // {value: 6}
```

Reduce can also be used to accumulate values onto an initial object. In this way an array of values can be build into a single object:

```
var a = [
  {value: 100, id:'a'},
  {value: 200, id:'b'},
  {value: 300, id:'c'}
]

var b = a.reduce(function(ac, cu) {
  ac[cu.id] = cu.value;
  return ac;
}, {});

b // {a:100, b:200, c:300}
```

## Some

Array.prototpe.some allows you to check each item in an array, with the function returning true as soon as an item is found that matches your criterior or false if none do.

```
const a = [1, 2, 3, 4, 5, 6];

// Divisible by three and not three itself
const b = a.some((x) => x / 3 !== 1 && x % 3 == 0);

b // true

const c = [1, 2, 3, 4, 5];

// Divisible by three and not three itself
const d = c.some((x) => x / 3 !== 1 && x % 3 == 0);

d // false
```



