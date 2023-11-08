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
<b>syntax</b>

```
let arrayName: type[];
```

```
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

<h3>Number</h3>
<p>All numbers in TypeScript are either floating-point values or big integers. The floating-point numbers have the type <code>number</code> while the big integers get the type <code>bigint</code></p>

```
let price: number;

Or you can initialize the price variable to a number:

let price = 9.95;
```

<p>As in JavaScript, TypeScript supports the number literals for decimal, hexadecimal, binary, and octal literals:</p>

<h4>Decimal numbers</h4>

```
let counter: number = 0;
let x: number = 1.00, 
    y: number = 2.00;
```    

<h4>Binary Numbers</h4>
<p>The binary number uses a leading zero followed by a lowercase or uppercase letter “B” e.g., <code>0b</code> or <code>0B</code> :</p>

```
let bin = 0b100;
let anotherBin: number = 0B010;
```

<p>Note that the digit after <code>0b</code> or <code>0B</code> must be <code>0</code> or <code>1</code></p>

<h4>Octal Numbers</h4>
<p>An octal number uses a leading zero followed by the letter <code>o</code> (since ES2015) <code>0o</code>. The digits after <code>0o</code> are numbers in the range <code>0</code> through <code>7</code>:</p>

```
let octal: number = 0o10;
```

<h4>Hexadecimal numbers</h4>
<p>Hexadecimal numbers use a leading zero followed by a lowercase or uppercase letter <code>X</code> (<code>0x</code> or <code>0X</code>). The digits after the <code>0x</code> must be in the range (<code>0123456789ABCDEF</code>). For example:</p>

```
let hexadecimal: number = 0XA;
```

<h4>Big Integers</h4>
<p>The big integers represent the whole numbers larger than 253 – 1. A Big integer literal has the <code>n</code> character at the end of an integer literal like this:</p>

```
let big: bigint = 9007199254740991n;
```

<h3>String</h3>
<p>TypeScript uses double quotes <code>(")</code> or single quotes <code>(')</code> to surround string literals:</p>

```
let firstName: string = 'John';
let title: string = "Web Developer";
```

<p>TypeScript also supports template strings that use the backtick (`) to surround characters.</p>
<p>The template strings allow you to create multi-line strings and provide the string interpolation features.</p>

```
let description = `This TypeScript string can 
span multiple 
lines
`;
```

<p>String interpolations allow you to embed the variables into the string</p>

```
let firstName: string = `Nandish`;
let title: string = `Web Developer`;
let profile: string = `I'm ${firstName}. 
I'm a ${title}`;

console.log(profile);

I'm Nandish. 
I'm a Web Developer.
```

<h3>Boolean</h3>
<p>The TypeScript boolean type has two values: <code>true</code> and <code>false</code>. The boolean type is one of the <code>primitive</code> types in TypeScript.</p>
<p>we can declare a boolean variable using the boolean keyword</p>

```
let pending: boolean;
pending = true;
// after a while
// ..
pending = false;
```

<p><b>Boolean operator:</b> AND, OR, NOT </p>

```
// NOT operator
const pending: boolean = true;
const notPending = !pending; // false
console.log(notPending); // false

const hasError: boolean = false;
const completed: boolean = true;

// AND operator
let result = completed && hasError; 
console.log(result); // false

// OR operator
result = completed || hasError; 
console.log(result); // true
```

<p>Type annotations for boolean</p>

```
let completed: boolean = true;
```

<p>we can annotate boolean parameters or return the type of a function using the boolean keyword:</p>

```
function changeStatus(status: boolean): boolean {
   //...
}
```
<p>JavaScript has the <code>Boolean</code> type that refers to the non-primitive boxed object. The <code>Boolean</code> type has the letter <code>B</code> in uppercase, which is different from the <code>boolean</code> type.</p>

<h3>object Type</h3>
<p>The TypeScript object type represents all values that are not in primitive types.</p>
<p>The following are primitive types in TypeScript:</p>
<ul>
   <li>number</li>
   <li>bigint</li>
   <li>string</li>
   <li>boolean</li>
   <li>null</li>
   <li>undefined</li>
   <li>symbol</li>
</ul>

```
let employee: object;

employee = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    jobTitle: 'Web Developer'
};

console.log(employee);

{
  firstName: 'John',       
  lastName: 'Doe',
  age: 25,
  jobTitle: 'Web Developer'
}
```

<p>If you reassign a primitive value to the <code>employee</code> object, you’ll get an error :</p>

```
employee = "Jane";

Error:
error TS2322: Type '"Jane"' is not assignable to type 'object'.
```

<p>The <code>employee</code> object is an <code>object</code> type with a fixed list of properties. If you attempt to access a property that doesn’t exist on the <code>employee</code> object, you’ll get an error:</p>

```
console.log(employee.hireDate);

Error:
error TS2339: Property 'hireDate' does not exist on type 'object'.
```

<code>Note that the above statement works perfectly fine in JavaScript and returns undefined instead.</code>

<p>To explicitly specify properties of the <code>employee</code> object, you first use the following syntax to declare the <code>employee</code> object:</p>

```
let employee: {
    firstName: string;
    lastName: string;
    age: number;
    jobTitle: string;
};
```

<p>And then you assign the <code>employee</code> object to a literal object with the described properties:</p>

```
employee = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    jobTitle: 'Web Developer'
};
```

<p>Or you can combine both syntaxes in the same statement like this:</p>

```
let employee: {
    firstName: string;
    lastName: string;
    age: number;
    jobTitle: string;
} = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    jobTitle: 'Web Developer'
};
```
<strong>object vs. Object</strong>
<p>TypeScript has another type called <code>Object</code> with the letter <code>O</code> in uppercase. It’s important to understand the differences between them.</p>
<p>The <code>object</code> type represents all non-primitive values while the <code>Object</code> type describes the functionality of all objects.</p>
<p>For example, the <code>Object</code> type has the <code>toString()</code> and <code>valueOf()</code> methods that can be accessible by any object.</p>

<b>The empty type {}</b>
<p>TypeScript has another type called empty type denoted by <code>{}</code>, which is quite similar to the object type.</p>
<p>The empty type <code>{}</code> describes an object that has no property on its own. If you try to access a property on such object, TypeScript will issue a compile-time error:</p>

```
let vacant: {};
vacant.firstName = 'John';

Error:
error TS2339: Property 'firstName' does not exist on type '{}'.
```

<p>But you can access all properties and methods declared on the <code>Object</code> type, which is available on the object via prototype chain:</p>

```
let vacant: {} = {};
console.log(vacant.toString());

output:
[object Object]
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

