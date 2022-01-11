# Chapter 3 - Type Systems and Type Classes

### **Type of Systems**

Both Haskell and Python have a strong type system meaning the system does not allow types to be coerced into another type. The opposite is true for a weak type system. Adding an integer to a string would result in an error.

| Haskell  | Python |
| --- | --- |
| ```ghci> 1 + "a"```   | ```>>> 1 + "a"``` |
| error:No instance for (Num [Char]) arising from a use of `+'   | TypeError: unsupported operand type(s) for +: 'int' and 'str' |

In dynamic typing systems, data is not processed until runtime, meaning we will see not any errors until we run the code. In static typing systems, data is processed at compile time, meaning the compiler would stop before we could execute the code. 

In dynamic typing systems, we can redefine variables as much as we want but in static typing systems, the variable needs to maintain its original type. Haskell has static typing while Python has dynamic typing.

#### **Explicit Type Declaration**

In explicit typing systems, data is assigned a type while in implicit typing systems; data does not need to be labelled. To examine the type of an expression, we will use ```:t``` in Haskell and ```type()``` in Python.

| Haskell  | Python |
| --- | --- |
| ```ghci> :t + 'x'```   | ```>>> type("x")``` |
| "x" :: Char  | <class 'str'> |
| ```ghci> :t 99```   | ```>>> type(99)``` |
| 99 :: Num p => p  | <class 'int'> |
| ```ghci> :t True```   | ```>>> type(True)``` |
| True :: Bool  | <class 'bool'> |
| ```ghci> :t ("cricket")```   | ```>>> type("cricket")``` |
| "cricket" :: [Char]  | <class 'str'> |
| ```ghci> ::t 8 == 7```   | ```>>> type(8 == 7)``` |
| 8==7 :: Bool  | <class 'bool'> |
| ```ghci> :t ('z', False)```   | ```>>> type(('z', False))``` |
| ('z', False) :: (Char, Bool)  | <class 'tuple'> |
| ```ghci> :t ('z', False)```   | ```>>> print(str(list(map(type,('z', False)))))``` |
| ('z', False) :: (Char, Bool)  | [<class 'str'>, <class 'bool'>] |

The ```::``` means _"has the type of"_ for example ```True``` has the type of ```Bool```. 

From the above you will notice in Haskell that:
* explicit types start with a uppercase letter e.g. Char, Bool and Num and
* each element in a tuple has its own type.

In both Haskell and Python, we can give our functions type declarations. The below function will take three elements and add them together. We will specify the type of the elements as integer.

| Haskell  | Python |
| --- | --- |
| ```ghci> addThree :: Int -> Int -> Int -> Int ; addThree x y z = x + y + z```   | <code>def addThree(x:int, y:int, z:int):</code> <br /> <code> &emsp; answer = x + y + z </code> <br /> <code> &emsp; &emsp;&emsp; &emsp;return int(answer)</code>|
| ```ghci> addThree 10 100 1000```   | ```>>> addThree(10,100,1000)``` |
| 1110 | 1110|
| ``` ghci> :t addThree```   | ```>>> type(addThree)``` |
| addThree :: Int -> Int -> Int -> Int | <class 'function'>|

### **Common Types**

| Haskell &emsp;&emsp;&emsp; &emsp;&emsp;&emsp;&emsp;&emsp;&emsp; | Python &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;| Description |
| ---------- | ---------- | --- |
| ```Int```   | ```int()``` | Integers(whole numbers) |
| ```Float```   |  | Floating point with single precision .e.g 14.242526 |
| ```Double```   | ```float()``` | Floating point with double precision .e.g 3.333333333333335|
| ```Bool```   | ```bool()``` | Boolean values: ```True``` and ```False``` |
| ```Char```   | ```str()``` | Unicode character. Denoted in single quotes in Haskell. In Python string can be denoted in both single and double quotes. |

### **Type Classes**

#### **The Eq Type Class**

This is to test for equality. Below are some examples.

| Haskell  | Python |
| --- | --- |
| ```ghci> 75 == 75```   | ```>>> 75 == 75``` |
| True | True |
| ```ghci> 75 /= 75```   | ```>>> 75 != 75``` |
| False | False |
| ```ghci> "Yes" == "No"```   | ```>>> "Yes" == "No"```|
| False | False |

#### **The Ord Type Class**

This is for types whose values can be put in some order. Let us have a look at some examples.

| Haskell  | Python |
| --- | --- |
| ```ghci> "afwefwwe" > "adwddw"```   | ```>>> "afwefwwe" > "adwddw"``` |
| True | True |
| ```ghci> 75 < 5```   | ```>>> 75 < 5``` |
| False | False |

In Haskell, the ```compare``` function takes 2 values and returns an ```Ordering```. The ```Ordering``` types are ```GT```(greater than), ```LT```(lesser than) and ```EQ```(equal).

| Haskell  |
| --- | 
| ```ghci> "afwefwwe" `compare` "adwddw"```   |
| GT | 
| ```ghci> 75 `compare` 75```   |
| EQ | 

#### **The Show Type Class**

In Haskell the ```show``` type class prints the values as a string. In Python, we can wrap ```str()``` around the value.

| Haskell  | Python |
| --- | --- |
| ```ghci> show 26```   | ```>>> str(26)``` |
| "26" | '26' |
| ```ghci> show False```   | ```>>> str(False)``` |
| "False" | 'False' |

#### **The Read Type Class**

In Haskell the ```read``` class type can be considered the opposite of the ```show``` class type. It takes a string and returns the appropriate type. In Python we will have to know the type before hand and wrap the object in its type. 

| Haskell  | Python |
| --- | --- |
| ```ghci> read "8" + 8```   | ```>>> int("8") + 8``` |
| 16 | 16 |
| ```ghci> read "False" && True```   | ```>>> bool(eval("False")) and True``` |
| False | False |
| ```ghci> read "87```   |  |
| error: * Could not deduce (Num String) arising from the literal `87' |  |

When using ```read``` with 87 only we get an error because GHCi does not know what to return. The previous 2 examples we added to an integer and we compared to a Boolean, so GHCi had an idea of what we wanted. We can tell Haskell what type we want an object to be. We have been doing this in Python in the previous examples.

| Haskell  | Python |
| --- | --- |
| ```ghci> read "17" :: Int```   | ```>>> int("17")``` |
| 17 | 17 |
| ```ghci> (read "17" :: Int) + 20```   | ```>>> int("17") + 20``` |
| 37 | 37 |
| ```ghci> (read "88" :: Float) + 1.5```   | ```>>> float("88") + 1.5``` |
| 89.5 | 37 |
| ```ghci> read "(44, 'm')" :: (Int, Char)```   | ```int("44"), str("m")``` |
| (44,'m') | (44,'m') |

#### **The Num Type Class**

These are numeric type classes.

| Haskell  | Python |
| --- | --- |
| ```ghci> 27 :: Int```   | ```>>> int(27)``` |
| 27 | 27 |
| ```ghci> 27 :: Integer```   | ```>>> int(27)``` |
| 27 | 27 |
| ```ghci> 12.123456789 :: Float```   | ```>>> float(12.123456789)``` |
| 12.123457 | 12.123456789 |
| ```ghci> 12.123456789 :: Double```   | ```>>> float(12.123456789)``` |
| 12.123456789 | 12.123456789 |
| ```ghci> (10 :: Int) + (20 :: Float)```   | ```>>> int(10) + float(20)``` |
| error : * Couldn't match expected type `Int' with actual type `Float'| 30.0 |

In Haskell, we get an error when we try to add 2 numbers that are not the same type. In Python, however you can add integers to floats as we have demonstrated. Let us inspect the ```+``` operator in Haskell.

| Haskell  |
| --- | 
| ```ghci> :t (+)```   |
| (+) :: Num a => a -> a -> a | 

The above shows that ```+``` takes in 2 numbers and returns a number of the same type. So ```Int``` + ```Int``` = ```Int```. The ```+``` is not limited to only 2 numbers. Let us do a few calculations. 

| Haskell  | Python |
| --- | --- |
| ```ghci> (10 :: Int) + (20 :: Int)```   | ```>>> int(10) + int(20)``` |
| 30| 30 |
| ```ghci> (10 :: Int) + (20 :: Int) + (30 :: Int)```   | ```>>> int(10) + int(20) + int(30)``` |
| 60| 60 |
| ```ghci> (10 :: Float) - (20 :: Float) - (30 :: Float)```   | ```>>> float(10) - float(20) - float(30)``` |
| -40.0| -40.0 |
