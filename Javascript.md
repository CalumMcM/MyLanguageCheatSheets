### Comments

```javascript
// Line comment
/*
Multi-line comment
*/	
```

### Data types and Variables

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

//Check Data type
typeof(myVariableType) //Will return the type of the variable passed in

//ES6:
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


### Destructing Assignment of objects

```javascript
//ES6
//Multi-assignments of objects
var voxel = {x: 3.6, y: 7.4, z: 6.54 };
const {x, y, z} = voxel; //OR
const { x : a, y : b, z : c } = voxel // a = 3.6, b = 7.4, c = 6.54


//From an Object:
const LOCAL_FORECAST = {
  today: { min: 72, max: 83 },
  tomorrow: { min: 73.3, max: 84.6 }
};
//We can assign the value of max for tomorrow as such
const {tomorrow : {max: maxOfTomorrow, min : minOfTomorrow}} = LOCAL_FORECAST;

//From arrays
//Using commas to reach desired point:
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c); // 1, 2, 5
//Combine this with the use of the rest operator
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b); // 1, 2
console.log(arr); // [3, 4, 5, 7]


```

### Use Strict

```javascript
//ES6:
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

//Checking length of an object
Object.keys(patients).length;

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

//Inserting objects within quotations of a string
const planet = {
	name: "Earth",
	ageInBillions: 4.53
};
const info = "We are from ${planet.name}. A planet which is ${planet.ageInBillions} billion years old!";

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

//ES6:

//Defualt parameters - When a parameter is not provided it will defualt to the one given

function tableGuests(headGuest = "Greg Davies"){
	tablesGuests = [headGuest, "Alan Davies", "Robert Davies", "Dave Davies"];
	return tablesGuests;
}

//Rest parameters - Allows you to pass an unspecified amount of arguments and use them
function sum(...args){
	return args.reduce((previous, current) => { //The reduce function applies the given operation 
		return previous + current; 	    //to the parameters so in this example it will sum all the 
	}); 				            //values in the array from start to finish
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
const myFunc = (myVar) => myVar+20 //Essentially takes the format: type functionName = (inputParameters) => returnAllThis

//Higher order arrow functions:
//The following use of Filters a function as an argument
FBPosts.filter(function(post) {
  return post.thumbnail !== null && post.shares > 100 && post.likes > 500;
})
//Now with the use of arrow functions it can be written in one line like so:
FBPosts.filter((post) => post.thumbnail !== null && post.shares > 100 && post.likes > 500)
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

//ES6:

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
let i = 0;
do {
    console.log(i);
    i++;
} while (i < 10);
for (var i = 0; i < 5; i++){
    console.log(i);
}
//For loop for objects:
for (let key in objectName){
	delete objectName.key;
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

### Max function (and spread)

```javascript
var arr = [-1, 4, 60, 23];
var maxOfArr = Math.max(...arr); //returns 60 through spreading the array. OR
var maxOfArr = Math.max(null, arr); //returns 60 and the null is needed otherwise max expects comma seperated arguments and not an array

```

## Getters and Setters
```javascript
//Example:
class car{
	constructor(make) {
		this._make = make;
	}
	//getter
	get manufacturer(){
		return this._make;
	}
	//setter
	set manufacturer(newManufacturer){
		this._make = newManufacturer;
	}
}
const myCar = new car('Hyundai'); 
console.log(myCar.manufacturer); //Hyundai
myCar.manufacturer = 'Honda';
console.log(myCar.manufacturer); //Honda
```

### Import Functions

```javascript
//Import one function from the file:
import {functionName} from "file_path_goes_here"; //Sometimes the file path needs "./" at the start

//Import everything from a file:
import * as myModule from "file_path_goes_here"
myModule.functionFromMyModule(); //Call the function from my module

//Importing a defualt export
import myExportedFunction from "file_path_goes_here"; //Difference being there are no {} around the function name
```

### Export
```javascript
//Given a function you have written such as
const countCows = (cowsArray) => cowsArray.length

const favouriteCow = "Daisy";
export {cowsArray, favouriteCow}

//To add an export fallback (Usually used when only one function is being exported) - can only be used for functions
export default function myFunction(inp1, inp2) {return inp1*inp2}
```

### Regular Expressions REGEX
```javascript
//Test function:
 
let myString = "The baby clothing industry is booming";
let myWord = /clothing/;
let myLetters = /boom/;
myWord.test(myString); //Returns True
myLetters.test(myString); //Returns True
myString.test(/^The/) //Returns True		Test occurance is at start of string (^)
myString.test(/booming/$) //Returns True	Test occurance is at end of string ($)
let mySample = "gorilla";
mySample.test(/(?=\w{5,}); //Returns true			Positive Lookahead (?=...)
mySample.test(/(?!b)/); Returns tre				Negative Lookahead (?!...)
let testStr = "Repeat Repeat Repeat";
testStr.match(/(\w+)\s\2);

let myWords = /up|down|left|right/;			//Catch different possibilities			
let ignoreCase = /YoUcAn'TExPrEsSsArCaSmWiThTeXt/i 		//case Insensitive	

//Match function:
let testStr = "Repeat Repeat Repeat";
testStr.match[/Repeat/g]; //Returns ["Repeat, Repeat, Repeat"] //Returns multiple occurances (g)
let jobDone = "Bingo Bango Bongo. Bish. Bash. Bosh";
jobDone.match(/Bish/g); //Returns ["Bish"]			Simple match
jobDone.match(/Ba./g); //Returns ["Bango", "Bash"]		Anything fill (.)
jobDone.match(/b[iao]ngo/g); //Returns ["Bingo, Bango, Bongo"];	Set characters gap
jobDone.match(/b[a-j]sh/g); //Returns ["Bish", "Bosh"] 		Alphabet range ([a-z])
date.match(/[a-z0-9]/);						Alphabet and numbers match([a-z0-9])
jobDone.match(/b[^ia]ngo/); //Returns ["Bongo"]			Ignore specified letters([^])
let repeatedChars = "Heeeeeeeeeeeeeeeeeelp!"
repeatedChars.match(/He*/); //Returns ["Heeeeeeeeeeeeeeeeee"]	Zero or More times (*)
let oneString = "Mississippi";
oneString.match(/s+/g); //Returns ["ss","ss"]			One or More times (+)
jobDone.match(/\w+/); //Returns the whole string jobDone	Shorthand notation for match every character (\w+)
jobDone.match(/\W/); //Returns nothing				Shorthand non-alphnumeric characters (\W)
myPi.match(/\d\); //Returns only digits or numbers		Shorthand for only digits/numbers (\d)
miPi.match(/\D/); //Returns all non-numbers			Shorthand for non-numbers (\D)
jobDone.match(/\s/) //Returns [" "," ", " ", " ", " "]		Shorthand for whitespace (\s)
let ohStr = "Ohhh no";
ohStr.match(/Oh{3,6}\s/); //Returns true			Upper and lower bound for occurances
ohStr.match(/Oh{3,}/);	Returns True				Only lower bound for occurances
ohStr.match(/Oh{3}/); Returns True				Exact number of occurances
testStr.match(/(\w+)\s\2); Returns ["Repeat Repeat Repeat", "Repeat"] Reuse regex expression (())

//Replace
var str = "Mr Blue has a blue house and a blue car";
var res = str.replace(/blue/g, "red"); //Replaces all occurnaces of the first input with the second input
```

### Trim
```javascript
//Will remove all whitepace from the given input
let myString = "    Why is there so much white space?    ";
myString.trim(); //Returns "Why is there so much white space?";
myString.trimLeft() //Returns "Why is there so much white space?    ";
myString.trimRight() //Returns "    Why is there so much white space?";

```

### Console Log
```javascript

console.log("Hello World"); //Will output "Hello World" to the web console

```
### Run a shell command from within the Javascript file
Only works for javascript programs that are not running online
```javascript
const execSync = require('child_process').execSync;
let myCommand = 'ping www.bbc.co.uk';
output = execSync(myCommand, { encoding: 'utf-8' }); //Calls the command and reads the output
console.log(output);
```

###Call an API
```javascript
response=getJSON('http://mylink.com/happyAPI', function(data) {});
//data is the JSON string
console.log(response);
```
### 

_Majority of code was obtained from freeCodeCamp_

