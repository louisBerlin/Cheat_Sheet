# JavaScript - TypeScript 

> 2024

___
### Console.log()   
___
```javascript
console.log("test^^")
```

___
### Variable declaration   
___
```javascript
var variable = 10
const variable2 = 10
let variable4 = 10

```

___
### Variable -> daten type 
___

```javascript
Syntax -> let <variableName>: <type> = <intitial value>;
const number = 42
const string = "hello"
const boolean = true
const object = {key : "value"}
const nullExample = null
let undefinedExample
undefinedExample = "string"
const list = ["hello","hello"]
```


___
### Arithmetic operator 
___

```javascript

const addition = 5+2
const substraktion = 5-2
const multi = 5*2
const div = 20/2
```

___
### Comparison
___
```javascript

const isEqual = 5 === "5" // false (strict)
const isEqual = 5 == "5" // true (loose equality)
const isLessThan = 10 < 20 // true
const isGreaterThan = 14 > 10  // true
```

___
### Logic operator
___
```javascript

const andOperator = true && true // true
const orOperator = true || false // true
const notOperator = !true // false
```

___
### Other operator (?)
___
```javascript

let x = 10
x = x+5
x += 5

x -= 5
```
___
### If & Else
___
```javascript

let condition = true

if(condition){
    console.log("richrig")
} else {
    console.log("false")
}
```
___
### Switch
___
```javascript

let option = "B"

switch(option) {
    case "A":
        console.log("option A")
        break
    case "B":
        console.log("option B")
        break
    default:
        console.log("Das ist nicht erlaubt")
}
```
___
### For
___
```javascript

for(let i = 0; i < 5; i++){
    console.log("for loop i = "+i)
}
```

___
### Wihle
___
```javascript

let j   = 0
while(j>3){
    console.log("while loop j = "+j)
    j++
}
```

---
### Function
---

```javascript

function functionName ()  {
}

function f():string  {
    return "hello"
}
```

___
### Function -> map
___

```javascript
// Create an array of numbers. Use the '.map' function to double all the numbers in the array.

const listnumber = [1,2,3,4]
console.log(listnumber.map((n: number) => {return n * 2}))
```

___
### Function -> filter
___

```javascript
//Create an array of words. Use the '.filter' function to select only the words that are longer than 5 letters.

const listString = ["un","deux","trois","quatre"]
console.log(    listString.filter((s : string)=> s.length>5)         )
```

___
### Function -> reduce
___

```javascript
//Create an array of numbers. Use the '.reduce' function to calculate the sum of all the numbers in the array.

const listnumber2 = [1,2,3,4]
console.log(listnumber2.reduce(myFunc))

function myFunc(total:number, num:number) {
    return total + num;
}
```

___
### Function -> some
___

```javascript
//Create an array of numbers. Use the '.some' function to check if at least one number is greater than 10.

const listnumber3 = [3,9,400,3]
console.log(listnumber3.some(GreaterThen10))

function GreaterThen10(n:number) {
    return n > 10;
}
```

___
### Type
___

```javascript
type Student  = {
    firstName:string,
    lastName:string,
    age:number,
    grades:number[]
};

const student : Student  = {
    firstName: "John",
    lastName: "Doe",
    age: 25,
    grades: [1,2,3,4,4]
}
```


