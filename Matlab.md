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

###