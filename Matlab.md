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

```matlab
M = magic(n) %Creates an nxn matrix of random numbers
```

### Zeros

```matlab
zeros(n, m) %Creates an nxm array of zeros
```



### Prod

```matlab
%Takes the product of an array
% To get the product of the columns of a matrix 
A = [1 2 3; 4 5 6; 7 8 9];
B = prod(A);
%  B = [6 120 504]

%For an array of booleans
A = [true false; true true] %A = [1 0; 1 1]
B = prod(A) 
%B = [1 0]

%To get the product of the rows of a matrix
A = [1 2 3; 4 5 6; 7 8 9];
B = prod(A,dim) %I believe prod(A') would also work
%B = [28; 80; 162]
```

### Absolute

```matlab
abs(myMatrix) %Will return the absolute value of each element in the array
```

### Squared

```matlab
X = -2:2 % X = vector [-2 -1 0 1 2]

Y = sqrt(X) % Y = vector [0.0000 + 1.4142i   0.0000 + 1.0000i   0.0000 + 0.0000i   1.0000 + 0.0000i   1.4142 + 0.0000i]
```

### Inverse of a matrix

```matlab
inv(C) %Where C is a matrix
```

### ~=

```matlab
%This fancy combination allows you to search for occurences of an element amongst an array, 0 = Found, 1 = Not Found
M = "Banana"
M ~= 'n' % = [1,1,0,1,0,1]

A = coinFlips({'heads' 'heads' 'tails'; 'tails' 'heads' 'tails'})
A ~= 'tails' % = [0 0 1; 1 0 1]
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

### Write data into a file

```matlab
dlmwrite(’data.txt’, test_data, ’delimiter’, ’\t’)
%Writes the matrix test_data into the file data.txt with tabs to seperate each entry of the matrix
```

### Print 

```matlab
fprintf('Hello World'); %For text

myMatrix %For an object

disp('error: this happened');

error(myErrorMessage); %Will print a red error message to the console
```

### If statements

```matlab
if (parameter)
	%Do this
elseif (anotherParameter | myName == myLastName)
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

### Random Numbers

```matlab
%To create random numbers we can use the function
rand() %Returns a random variable between (0,1)
rand(n) %Returns an nxn matrix of random variables
rand(n, m, typeDef) %Returns an nxm matrix of type typeDef (single or double)

%To make it so that the random numbers that are generated are consitent everytime the file is ran we can use
rng(1) %This sets a seed that will be ensure the random numbers generated are repeatable

%We can create multivariate random numbers using
mvnrnd(mu, sigma) % Where mu = the mean and sigma is the matrix of variances
mvrnd(mu, sigma, n) % This will create an n x d matrix where d is from the dimensions of mu (1xd) 
```

### Concatenate

```matlab
%To combine arrays we can use
cat(dim, A, B) %Concatenates array A and B to the given dimension dim 
%E.g.
A = [1 2 3 4]; B = [5 6 7 8];
C = cat(1, A, B); %C = [1 2; 3 4; 5 6; 7 8]
D = cat(2, A, B); %D = [1 2 5 6; 3 4 7 8]
```

### Define a Single Layer Neural Network

```matlab
slnet = glm(n,m, 'linear') % Defines a neural network with n inputs, m outputs and a linear output function
```

### Training a Single Layer Neural Network with Linear Activation Function

```matlab
%Go to graddesc for more details
options=foptions;
options(1)=1; % display/log error values
options(3)=0.01; % convergence criterion
options(14)=100; % maximum number of training iterations
options(18)=0.001; % learning rate (eta)

% Netopt function takes a specfici training algorithm.
% xtrain is the matrix of training data
% ttrain contains the correspongind targets, one row per pattern

[slnet options errlog] = netopt(slnet, options, xtrain, ttrain, 'graddesc');
plot(errlog) % graph of error vs learning rate
```

### Training a Single Layer Neural Network with Sigmoid Activation Function

```matlab
options=foptions;
options(1)=1;
options(18)=0.01;

ttrain = [ta;tb];

slnet=glm(2,1,’logistic’)
[slnet options errlog] =
netopt(slnet, options, xtrain, ttrain, ’graddesc’);
```

### Testing a Single Layer Neural Network

```matlab
% glmfwd(net, x) runs the test data xtest throught the network

test out = glmfwd(slnet, xtest);

% If ttest contains the correct classification of for the test data then this will compute the classification error

[maxOut, classified] = max(testOut,[],2); % return the maximum value for each row (work along dimension 2). This then returns the max value for each row in maxOut, adn the index in classified
[tmpOut, answerClasses] = max(ttest,[],2); 
numberMisclassified = size(find(classified-answerClasses)); % returns the indices of non-zero elements (i.e where the output class is different to the target class). Then returns the size of misclassified patterns
percentError = 100.0 * numberMisclassified / size(answerClasses); 

```

### Nargin

```matlab
%The function nargin will return how many arguments the function given to it has. If called inside a function with no given arguments (like below) it will return the number of arguments that were passed to the function

%E.g. for a given function

function c = addme(a,b)
    switch nargin
        case 2
            c = a + b;
        case 1
            c = a + a;
        otherwise
            c = 0;
    end
end

%We can can call it in multiple ways:
c = addme(13,42) % c = 55
c = addme(13) % c = 26
```

