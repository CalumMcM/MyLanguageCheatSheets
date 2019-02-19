### Constructing a Matrix:

```matlab
A = [ a11 a12 a13 ; a21 a22 a23 ; a31 a32 a33]
```

### Getting the size of a matrix:

```matlab
[row, col] = size(A)
```

### Read Data Into A Matrix

```matlab
filename = 'data.txt'; %Name of file to be loaded
delimiterIn = '\t'; %Sets where to split the data
headerlinesIn = 0;  %Lets you take first lines are titles
A = importdata(filename, delimiterIn, headerlinesIn); 
```

### Read Data Into A Struct

```matlab
filename = 'data.txt'; %Name of file to be loaded
delimiterIn = '\t'; %Sets where to split the data in this case a tab
headerlinesIn = 1;  %Lets you take first lines are titles
file_data = importdata(filename, delimiterIn, headerlinesIn); 
A = file_data.data; %Store the actual data in a struct
col_headers = file_data.colheaders; %Extract the headers as a list
```

### Print 

```matlab
fprintf('Hello World') %For text

myMatrix %For an object
```

### If statements

```matlab
if (parameter)
	%Do this
elseif (anotherParameter)
	%Do this instead
else
	%Well do this then
end
```

### Loops

#### For 

```matlab
for c = 1:k % from the 1 to an integer K
	if (c==5)
		break; %This will jump out the loop
	elseif (c==6)
		continue %This will skip to the next iteration of the for loop
end
```

#### While

```matlab
while n>1
	n = n-1;
end
```

### Matrix sum

```matlab
sumMatrix = sum(A) %Sums whole matrix
sumColN = sum(A(:,n)) %For column n
sumRowN = sum(A(n,:)) %For row n
```

### Plotting a Graph

#### 2D

```matlab
x = A(:,1); %Sets x axis as first column of matrix A
y = A(:,2); %Sets y axis as second column of matrix A

%Scatter 2D with filled points
scatter(x,y,’filled’) 
axis([-1, 11, -1, 11]); %Axis limits

%Labels
xlabel('xLabel'); %Sets label for x axis
ylabel('yLabel'); %Sets label for y axis

c = cellstr(num2str([1:6]')); %Sets labels for the numbers 1 -> 6
dx = 0.1; dy = 0.3; %Adds displacement so numbers don't overlap points
text(x+dx, y+dy, c); %places text on graph
```

####3D

```matlab
x = A(:,1); %Sets x axis as first column of matrix A
y = A(:,2); %Sets y axis as second column of matrix A
z = A(:,3); %Sets z axis as third column of matrix A

%Scatter 3D with red filled points
scatter3(x,y,z,'red',’filled’) 
axis([-1, 11, -1, 11, -1, 11]); %Axis limits

%Labels
xlabel('xLabel'); %Sets label for x axis
ylabel('yLabel'); %Sets label for y axis
zlabel('zLabelk'); %Sets label for z axis
c = cellstr(num2str([1:6]')); %Sets labels for the numbers 1 -> 6
dx = 0.1; dy = 0.3; dz = 0.2; %Adds displacement so numbers don't overlap points
text(x+dx, y+dy, z+dz, c); %places text on graph

%Keep the current plot
hold on;

```

