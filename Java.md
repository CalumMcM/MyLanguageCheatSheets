### Function Type Definition 

```java
public static void main(String[] args){
}
/*
 public			 - method is visible to other objects {protected, private, package}
 static 		 - method is assosiated with the class, not a specific 							instance (object) of that class. A static method can be 					called without creating an object of that class
 void			 - the return type of the function (in this case nothing)
 String[] args 	 - allows command line input
 */
 
```

### If Statements

```java
if (condition) {
    function();
}
if(condition){ //There are no elif statements in java
    anotherFunction();
}
else(condition){
    finalFunction();
}
```

### For Loops

```java
for (int i = 0; i < n; ++i){ 
    
}
```

###Switch

```java
switch(condition){ //Condition is an int with values ranging from 
    case 0: function0(); break;
    case 1: function1(); break;
      	...
    case n: functionn(); break;
}
```

### Frame

```java
import java.awt.*;

JFrame frame = new JFrame("My Frame"); //Names the frame
frame.setSize(420,600); // Sets the dimensions for the frame
... 
frame.setVisible(true); //Makes the frame visible
```

### JPanel

```java
import java.awt.*;

JPanel panel = new JPanel(); //Creates the panel that all containers/objects will go on
panel.setBackground(Color.white); //Sets the color of the panel
...
frame.add(panel); //Don't forget to add the panel to your frame!
```

### JLabel

```java
import java.awt.*;

//Want to initiate the label with text:
JLabel label = new JLabel("Text that will be visible in you label");
panel.add(label); //Add the label to the panel

//If you want to add the text to the label at a later point:
JLabel dynamicLabel = new JLabel();
dynamicLabel.setText(myString + " " + myInt);

panel.add(label);
```

### Images

```java
import java.awt.*;

ImageIcon myImage = new ImageIcon("images/myImage.png");

panel.add(myImage);
```

### Buttons

```java
import javax.swing.AbstractButton; //If this doesn't work do javax.swing.*
import java.awt.*;

JButton myButton = new JButton("THIS IS A BUTTON");

myButton.addActionLister(new ActionListener() {
    public void actionPerformed(ActionEvent e) {
        dothis()
    }
});

panel.add(myButton);
```

### Button Image

```java
import javax.swing.AbstractButton; //If this doesn't work do javax.swing.*
import java.awt.*;

ImageIcon myImage = new ImageIcon("images/myImage.png");
JButton myButton = new JButton(myImage); //Sets the content of the button to be an image

myButton.addActionLister(new ActionListener() {
    public void actionPerformed(ActionEvent e) {
        dothis()
    }
});

panel.add(myButton);
```

### JTextField

```java
import java.awt.*;

JTextField getName = new JTextField();
getName.setPreferredSize(new Dimension(50, 20));

submit.addActionListener(new ActionListener() { //When a button is pressed
    public void actionPerformed(ActionEvent e){
        String name = getName.getText(); //Set name to the text in the TextField
    }
});
```

### Exception Handler

```java
try{
    function();
} catch(IOException e){
    e.printStackTrace();
}
```

### Read

```java
try{//Its important to have a reader in an exception handler
    String fileData = readFileAsString("myFile.txt"); //Writes the contents of 'myFile.txt' to fileData
} catch(IOException e){
    e.printStackTrace();
}
```

### Write 

```java
try{ //Its important to have a writer in an exception handler
    FileWriter saver = new FileWriter("myFile.txt"); //Opens the file for writing to in saver
	saver.write("This lovely line of text"); //Writes the string to the file

	saver.close(); //Important to close the writer 
} catch(IOException e){
    e.printStackTrace();
}
```

### Length of String

```java
int length = myString.length();
```

### Char At certain postion of String

```java
String text = "foo";
char charAtZero = text.charAt(0);
```

### Convert String to Int

```java
Int a = Integer.parseInt(myChar);
```

### Convert Int to String

```java
String myString = Integer.toString(myInt);
```

### Take an input when class called

```java
//In your main definition where you have 'String[] args'
//This means that your input will be a string, to process this you do something along the lines of:

int[] input = new int[args.length];
for (int i = 0; i < args.length; ++i){
    input[i] = Integer.parseInt(args[i]);
}
//The list 'input' now contains the input given when the class was called
```

### Get the char at a specific point

```java
String input = "Hello";
Char a = input.charAt(2); // a = l
```

