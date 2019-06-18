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
