<h1>TypeScript Basics & Basic Types</h1>

<h4>JS Example 1</h4>

```
function add(n1, n2) {
  return n1+n2;
}
const number1 = 5;
const number2 = 2.8;
const result = add(number1, number2); 
console.log(result);
```

```
output: 7.8
```

<h4>JS Example 2</h4>

```
function add(n1, n2) {
  return n1+n2;
}
const number1 = '5';
const number2 = 2.8;
const result = add(number1, number2); 
console.log(result);
```

```
output: 52.8
```

<h4>TypeScript Example</h4>
<p>The core primitive types in typescript are all lowercase. "string", "number"</p>

<h4>Example</h4>

```
function add(n1:number, n2:number) {
  return n1+n2;
}
const number1 = '5';
const number2 = 2.8;
const result = add(number1, number2); 
console.log(result);
```

```
output: 7.8
```

<h4>Example</h4>

```
function add(n1:number, n2:number) {
  return n1+n2;
}
const number1 = '5';
const number2 = 2.8;
const result = add(number1, number2);
console.log(result);
```

```
output: getting error because number1 is a string
```

<h4>Example</h4>

```
function add(n1:number, n2:number) {
  if(typeof n1 !== 'number' || typeof n1 !== 'number') {
    throw new error('Incorrect Input');
  }
  return n1+n2;  
}
const number1 = '5';
const number2 = 2.8;
const result = add(number1, number2);
console.log(result);
```

```
output: getting error because number1 is a string
```

