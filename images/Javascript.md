### Comments

```javascript
// Line comment
/*
Multi-line comment
*/	
```

### Data Types and Variables

```javascript
/*Data types are
• undefined	• null	• Boolean	• string	• symbol	• number	• object
*/
var myVariable = 10;

//Global Variables
var aGlobalVariable;

function hereIsAFunction(){
	hereIsAnotherGlobalVariable = 5; //Variables created without var wil be global
    var thisIsALocalVariable = 10;
}

//let variables
let name = "Harry";
let name = "Pringle"; //Throws an error as let doesnt allow objects to be changed

//const variables (READ only variables)
const pets = ["dog", "cat", "Pelican"];
//This will throw an error when an attmept to change it is made. E.g.
pets = ["dog", "Warthog", "Pelican"]
//HOWEVER you can change indivdual items, E.g.
pets[2] = "Banshee"; //pets = ["dog", "Warthog", "Banshee"]
//This can be prevented by using freezing the object
Object.freeze(pets); //Now nothing can change pets

```

### Use Strict

```javascript
//By inserting:
"use strict";
//into your code it will catch bad coding habits. Such as missing out var when declaring a variable
```



### Objects / JSON

```javascript
var human = {
	"name": "Jolly Boy John",
	"hobbies": ["Eating chocolate bananas","Wearing grandmas knickers on his head"],
	"age": 16,
	"profession": "WOODEN PALLETS!"
};
//humansName = "Jolly boy John"
var humansName = human.name; 
human["name"];

//Eg2
var dogs = {
  Fido: "Mutt", Hunter: "Doberman", Snoopie: "Beagle"
};
var myDog = "Hunter";
var myBreed = dogs[myDog];
console.log(myBreed); // "Doberman"

//Updating values in an Object
var patient = {
    "name": "Buluga"
    "issue": "Obese"
    "condition": "critical"
};
patient.condition = "stable" //or
patent["condition"] = "stable"

//Adding new properties
patient.surname = "Whale" //or
patient["surname"] = "Whale"

//Deleting properties
delete patient.issue;

//Checking if a property exists
patient.hasOwnProperty("condition"); //True

//Accessing nested objects
var kitchenStock = {
  "cupboard": {
    "drawer": "rice"
  },
  "fridge": {
    "top shelf": { 
      "leftSide": "cheese",
      "rightSide": "yoghurt"
    },
    "bottom drawer": "apples"
  }
};

kitchenStock.fridge["top drawer"].rightSide; // "yoghurt"
ourStorage.cupboard.drawer; // "rice"

//Accessing nested arrays
var zooAnimals = [
  {
    animalType: "monkey",
    diet: [
      "bananas",
      "nits",
      "chocolate-cake"
    ]
  },
  {
    animalType: "hippo",
    diet: [
      "grass",
      "bark",
      "ferns"
    ]
  }
];
zooAnimals[0].diet[1]; // "nits"
zooAnimals[1].diet[0]; // "grass"
```



### Basic Arithmetic

```javascript
\\Addition
a + b;
a++;
a+=5;
\\Subtraction
a-b;
a--;
a-=5;
\\Multiplication
a*b;
a*=5
\\Division
a/b;
a/=5;
\\Modulus
a%b; \\(15%2 == 1)
```

### Strings

```javascript
myString = "This is a string"
myString += "!" \\ "This is a string!"

\\Length
"How long is this I wonder?".length;

myString[3] \\"i"


```

### Arrays

```javascript
var myArray = [1,2,3];
var myMultidimensionalArray = [[1,2,3],["Hello","There"],["G3n3r@l","K3n0bi", 13]];

myArray[1]; // = 2
myMultidimensionalArray[3][1]; // = "K3n0bi"

//Push (adding an element to an array)
myArray.push(4); //myArray = [1,2,3,4]

//Pop (removing the last element of the array)
var myArray = [1,2,3];
var endElement = myArray.pop(); //myArray = [1,2]	endElement = 3

//Shift (removing the first element from an array)
var myArray = [1,2,3];
var endElement = myArray.push(); //myArray = [2,3]	endElement = 1

//Unshift (Inserting an element to the start of an array)
var myArray = [1,2,3];
var firstElement = 0;
myArray.unshift(firstElement); //myArray = [0,1,2,3]
```

### Functions

```javascript
function myFunction(logMessage){
	console.log(logMessage);
}

function notMyFunction(returnMe){
    var dontReturnME = returnME;
    return dontReturnME
}

//Arrow Functions

const myFunc = function(myVar) {
  const thisVar = 20;
  myVar += thisVar;
  return myVar;
}
//Is the same as:
const myFunc = (myVar) => {
    const thisVar = 20;
    return myVar+thisVar;
}
//Is the same as:
const myFunc = (myVar) => myVar+20
```

### If statements

```javascript
if (myName == "Doc" && (hisName == "Marty" || dogName == "Einstein")){
	console.log("We've got to go back to the future!")
} else if (myName == "Danny Devito" && myAge < 12){
	console.log("Gimme the meatballs")        
}
else{
    console.log("It is I, Jeff Goldbloom")
}

//Ternary operator
//condition ? execute-if-true : execute-if-false
function findGreater(a,b){
    return a > b ? "a is greater than b" : "b is greater than a";
}
//Multiple Ternery operators
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" : (a > b) ? "a is greater" : "b is greater";
}
```
### Switch Statements
```javascript
//Each case variable test for strict equality (===)
//Without the breakstatement after a case the following case statements will also be executed until a break statement is reached
switch(myVar){
	case value1: doThis; break;
	case value2: noDoThis; break;
	default: doDefualt; break;
}
```

### While, For,  Loops

```javascript
while (i < 10) {
	console.log(i);
	i++;
}
var i = 0;
do {
    console.log(i);
    i++;
} while (i < 10);
for (var i = 0; i < 5; i++){
    console.log(i);
}
```

### Random

```javascript
var randomInt = Math.random(); //Returns a random number in the range [0,1)

//To generate a random number within a range:
Math.floor(Math.random() * (max-min + 1)) + min
```

### Convert String to int

```javascript
var myInt = parseInt("1314");

//Converting using radix (converting string in binary to int)
var myBinaryNumber = parseInt("11",2);
```

_Majority of code was obtained from freeCodeCamp_

