# Typescript notes

### Destructuring Arrays - let [a, b, c] = anArray

```
let anArray: string[] = ['a', 'b', 'c'];
let [a, b, c] = anArray;
let [a, b] = anArray; //only first 2

```

### Destructuring objects -  let { aField, bField, cField } = anObject

```
let anObject = {
  aField: 'value a',
  bField: 'value b',
  cField: 'value c'
};

let var1: string = anObject.aField;
let var2: string = anObject.bField;
let var3: string = anObject.cField;

//OR use object destructuring - same field names
let { aField, bField, cField } = anObject

//OR with different fieldNames
let { aField: newAField, bField: newBField, cField: newCField } = anObject
console.log(newAField);


//rest parameter - rest of the parameters
function someFunction([arr1, arr2, ...restOfTheArray]: arr[]){
}
someFunction(['a', 'b', 'c', 'd']);

```

### Spread operator - arrays and function parameter (...)

```
// arrays
let anArray = [4, 3, 2];
let anotherArray = [ 82, 23, ...anArray];

//function
let yetAnotherArray = [1,5,6] ;
anotherArray.push(...yetAnotherArray); // array's push function is push(...items)
```

### Tuples
