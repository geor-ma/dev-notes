# Typescript notes

### Destructuring Arrays

```
let anArray: string[] = ['a', 'b', 'c'];
let [a, b, c] = anArray;
let [a, b] = anArray; //only first 2

```

### Destructuring objects

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

```
