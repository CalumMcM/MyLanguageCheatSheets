### Function type defintion expained

```haskell
functionA:: [Int] -> Int -> String
-- Function definitions start with a lower case letter
-- Takes a list of ints and an int as input and returns a string
```

### Type Definitons explained

```haskell
type Cell = (Int, Int)
-- Type definitions start with capitals
```

### List comprehension explained

```haskell
listCompExample:: [Int] -> Int
listCompExample xs = sum[x | x <- xs]
-- This function will sum all integers in the input list together 
```

### [LC] Splitting a list on the left hand side & Base Cases

```haskell
listCompExample:: [Int] -> Int
listCompExample (x:ys) = sum[x*y | y <- ys]
-- This list will take the first element of the list and times it by every subsequent element of the list and return the sum of each multiplication

listCompExample:: [Int] -> Int
listCompExample (x:y:zs) = sum[(x+y)*z | z <- xs]
-- This list will sum the first two elements and times them against every other element in the list returning the sum

listCompExample:: [Int] -> Int
listCompExample [] = 0
listCompExample [x] = x
listCompExample [x,y] = x+y
listCompExample (x:y:zs) = sum[(x+y)*z | z <- zs]
-- It is important to include base cases to cover all inputs otherwise your function will fail for certain inputs
```

### Recursion Explained

```Haskell
recursionExample:: [Int] -> Int -> Int
recursionExample [] y = y
recursionExample (x:xs) y | x`mod`2 == 0 = (x + y) + recursionExample xs y
                          | otherwise = recursionExample xs y
-- This function will sum every even element of the input list of ints with the input int (y).
-- Dont forget the base case as this is recursion so without it, it will fail
-- This is also an example of guarded recursion. The use of '|' means that it can filter certain options, in this case, even numbers
```

### Using 'where'

```Haskell
whereExample :: [Int] -> Int
whereExample [] = 1
whereExample (x:xs) = (((added (x:xs)) `div` 24) `mod` 7) + 1
  where
   added :: [Int] -> Int
   added [] = 0
   added (x:xs)
      | x >= 0 = x + added xs
      | otherwise = added xs
-- This example takes a list of time durations and calculates what time it is after all those durations have passed. Ignoring negative durations
-- The use of 'where' allows us to implement a second function within the current function
```

### [LC] Guards

```haskell
[ (x,y) | x <‐ [0..3], y <‐ [0..3], x<y ]
-- Output: [(0,1),(0,2),(0,3),(1,2),(1,3),(2,3)]
-- The guard at the end of the list comp acts as a filter
```

###Combining lists

```Haskell
-- To add an element to the head of a list:
element : List 
--e.g.
1 : [2,3] = [1,2,3]
"l" : "ist" = "list"
-- To combine to lists together
list1 ++ list2 
--e.g.
[1] ++ [2,3] = [1,2,3]
"l" ++ "ist" = "list"
```

### Zip 

```haskell
-- This will combine two lists to create a list of tuples
zip [0,1,2] "abc" = [(0,a), (1,b), (2, c)]
```

### Higher Order Function

#### Map

```haskell
squares :: [Int] -> [Int]
squares xs  =  map sqr xs
    where
    sqr x = x*x
-- What map does is it will apply a function (in this case sqr) to every element of a given list
```

#### Filter

```haskell
positives :: [Int] -> [Int]
positives xs  =  filter pos xs
    where
    pos x = x>0
-- What filter does is it will apply a condition to every element in a list (in this case pos) and remove those that do not meet the condition
```

#### Fold

```haskell
-- What foldr does is it will apply a operation which will reduce the size of the input by 1.
-- E.g. 
-- [Int] will become Int 
-- [[Int]] will become [Int]

concatEg  :: [[a]] ‐> [a]
concatEg xs  =  foldr (++) [] xs

-- Here this example is concatenating each list within the list of lists
-- E.g. 
-- [[1,2],[10,11],[3]] = [1,2,10,11,3]

productEg  :: [Int] ‐> Int
productEg xs  =  foldr (*) 1 xs

-- Here this example is taking the sum of each element in a list
```

#### All 3 Together

```haskell
f :: [Int] -> Int
f xs  =  foldr (+) 0 (map sqr (filter pos xs))
     where
     sqr x = x * x
     pos x = x > 0
-- This takes the sum of squared positive integers from a given list
```

### Maybe Function

```haskell
-- Used when optional input or output
-- Optional Input:
power :: Maybe Int -> Int -> Int
power Nothing n = 2^n
power (Just m) n = m^n
--Optional output
divide :: Int -> Int -> Maybe Int
divide n 0  =  Nothing
divide n m  =  Just (n`div`m)
```

### Currying

```

```

