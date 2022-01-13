# Chapter 4 - Recursion

Recursion is the process where a fucntion calls itself until it has reached a certain critera or gotten the desired result. This means that the function stops runnning when the condition of that function has been met. Haskell is a declaretive language while Python is an impertive language. This means that for for Haskell you do computations by delaring _what_ something is while in Python you would specify _how_ to compute it. 

### **Recursive Functions**

#### **maximum**

In Haskell, the ```maximum``` function takes a list of numbers and returns the number with the highest value. In Python we would use the ```max()``` function. 

| Haskell  | Python |
| --- | --- |
| ```ghci> maximum[22,44,66,88]```   | ```>>> max([22,44,66,88])``` |
| 88  | 88|
| ```ghci> :t maximum```   | ```>>> type(max)``` |
| maximum :: (Foldable t, Ord a) => t a -> a  | <class 'builtin_function_or_method'> |

We can build our own function like this and call it ```maximum'``` in Haskell and my_max in ```my_max()``` in Python. This function will loop through a list to get the largest number. Our first step is to define our base case. This is the solution to the simplest possible input. From there we can add more conditions.

| Haskell &emsp;&emsp;&emsp; &emsp;&emsp;&emsp;&emsp;&emsp;&emsp; | Python &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;| Description |
| ---------- | ---------- | --- |
| ```maximum' :: (Ord a ) => [a] -> a ```   |  | Take in a list and return a single value |
| ```maximum' [] = error "list is empty"  ```   |  | Display error when the list is empty |
| ```maximum' [x] = x ``` |   | If there is only one element in the list, then retun that element. |
| ```maximum' (x:xs) = max x (maximum' xs)```   | | Split the list between head(x) and tail(xs), then use ```max``` function on ```maximum'```  and on xs (tail) |

Lets us try out our fuction.

| Haskell  | Python |
| --- | --- |
| ```ghci> maximum' [1,5,8,5,888,656,66666,4]```   |  |
| 66666 |  |
