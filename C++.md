### How to get current system time

```c++
#include <iostream>
#include <time.h>

time_t start = time (NULL); //Gets the current system time in milliseconds
```

### Get an input variable from terminal line

```c++
#include <iostream>

int a;
std::cin >> a;
//For an array you must take the input one by one in a for loop
//Remember c++ doesnt have strings so you would use a char array
```

