### Clear Commands

```matlab
clear % clear data stored in ’Workspace’
clc   % clear commands shown in ’Command Window’
```

### Save & Load Commands

```matlab
save test.mat % Will save all workspace variables in test.mat file
load test.mat % Will load test.mat file
```



### Constructing a Matrix:

```matlab
A = [ a11 a12 a13 ; a21 a22 a23 ; a31 a32 a33]
```

(:,:)  - Will retrieve a whole matrix

(n,:) - Will retrieve row n of a matrix

(:,n) - Will retrieve column n of a matrix

A' - Will make a transpose of matrix A

#### Reshape

````matlab
reshape(A,1,9) %Will reshape A (a 3x3 matrix) into a 1x9 matrix
````

#### Mean

```matlab
mean(A, 1)  % 1 indicates to apply the mean per column
mean(A,2) % 2 indicates to apply the mean per row
mean(A,'all') % Computes the mean over all elements of A
```

#### Getting the size of a matrix:

```matlab
[row, col] = size(A)
```

#### Magic Matrix



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

### Write data into a file

```matlab
dlmwrite(’data.txt’, test_data, ’delimiter’, ’\t’)
%Writes the matrix test_data into the file data.txt with tabs to seperate each entry of the matrix
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

#### 2D - Scatter

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

####3D - Scatter

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

#### 2D - Bar

```matlab
hh = bar(A(:,1), A(:,2), 1);
% Modify the initial plot
set(hh, 'FaceColor', 'white');
set(hh, 'EdgeColor', 'red');
set(hh, 'linewidth', 1.5);
% Define x and y labels
ylabel('Rel. Freq.'); xlabel('Length / cm');
% Create title
title('Lengths of male fish');
% Define only x-axis limits
xlim([0 20]);
```

#### 3D - meshgrid/surf

```matlab
figure
[x, y] = meshgrid(-10:0.1:10, -5:0.1:5);
z = x.*exp(-x.^2 - y.^2);
surf(x, y, z)
% call the surf function
```



####Cumulative Distribution Function

```matlab
hh = plot(A(:,1), cumsum(A(:,2))/N_M, '-r');
% Modify the initial plot
set(hh, 'linewidth', 1.5);
% Define x and y labels
ylabel('cdf'); xlabel('Length / cm');
% Define only x-axis limits
xlim([0 20]);
```

#### Decision boundary

```matlab
% Show decision boundary
dec_bound = 10.7;
plot([dec_bound dec_bound], get(gca, ’ylim’), ’--k’);
```

### Functions

```matlab
function [ A_shift ] = mean_shift_1( A )
%			↑						↑
%  What will be returned	function name and its arguments
```

