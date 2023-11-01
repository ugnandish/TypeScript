<h1>TypeScript</h1>
<p>TypeScript is typed JavaScript. TypeScript adds types to JavaScript to help you speed up the development by catching errors before you even run the JavaScript code.</p>
<p>TypeScript is an open-source programming language that builds on top of JavaScript. It works on any web browser, any OS, and any environment that JavaScript runs.</p>

<h2>Basic Types</h2>
<h3>Type Annotations</h3>
<p>TypeScript uses type annotations to explicitly specify types for identifiers such as variables, functions, objects, etc.</p>
<p>TypeScript uses the syntax <code>: type</code> after an identifier as the type annotation, which <code>type</code> can be any valid type.</p>
<p>Once an identifier is annotated with a type, it can be used as that type only. If the identifier is used as a different type, the TypeScript compiler will issue an error.</p>
<h3>Type annotations in variables and constants</h3>
<p>the type annotation comes after the variable or constant name and is preceded by a colon (<code>:</code>).</p>
<b>syntax</b>

```
let variableName: type;
let variableName: type = value;
const constantName: type = value;
```

<b>Examples</b>
```
let counter: number;
counter = 1;

If you assign a string to the counter variable, you’ll get an error:
let counter: number;
counter = 'Hello'; // compile error 
```

<p>You can both use a type annotation for a variable and initialize it in a single statement like this:</p>

```
let counter: number = 1;
```

<p>In the below example, the name variable gets the string type, the age variable gets the number type, and the active variable gets the boolean type.</p>

```
let name: string = 'John';
let age: number = 25;
let active: boolean = true;
```

<h4>Arrays</h4>
<p>To annotate an array type you use a specific type followed by a square bracket <code>: type[]</code></p>

```
let arrayName: type[];

let names: string[] = ['John', 'Jane', 'Peter', 'David', 'Mary'];
```

<h4>Objects</h4>
<p>To specify a type for an object, you use the object type annotation. For example:</p>
<p>In this example, the person object only accepts an object that has two properties: name with the string type and age with the number type.</p>

```
let person: {
   name: string;
   age: number
};

person = {
   name: 'John',
   age: 25
}; // valid
```

<h4>Function arguments & return types</h4>
<p>The following shows a function annotation with parameter type annotation and return type annotation:</p>
<b>Syntax</b>

```
let greeting : (name: string) => string;
```

```
In this example, you can assign any function that accepts a string and returns a string to the greeting variable:

greeting = function (name: string) {
    return `Hi ${name}`;
};
```

```
The following causes an error because the function that is assigned to the greeting variable doesn’t match its function type.

greeting = function () {
    console.log('Hello');
};

//Error - Type '() => void' is not assignable to type '(name: string) => string'. Type 'void' is not assignable to type 'string'.
```


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

