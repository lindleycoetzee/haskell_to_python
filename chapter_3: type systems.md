# Chapter 3 - Type Systems, 

### **Type of Systems**

Both Haskell and Python have a strong type system meaning the system does not allow types to be coerced into another type. The opposite is true for a weak type system. Adding a integer to a string would reslut in an error.

| Haskell  | Python |
| --- | --- |
| ```ghci> 1 + "a"```   | ```>>> 1 + "a"``` |
| error:No instance for (Num [Char]) arising from a use of `+'   | TypeError: unsupported operand type(s) for +: 'int' and 'str' |

In dynamic typing systems, data is not processed until runtime meaning we will see any errors until we run the code. In static typing systems, data is processed at compile time meaning the compiler would stop before we could execute the code. 

In dynamic typing systems we can redefine variables as mush as we want but in static typing systems, the variable need to maintain its original type. Haskell has static typing while Python has dynamic typing.

#### **Explicit Type Declaration**

In explicit typing systems data is assigned a type while in implicit typing systems data does not need to be labelled. To examine the type of an expression, we will use ```:t``` in Haskell and ```type()``` in Python.

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
* explicit types start with a uppercase letter e.g Char, Bool and Num and
* each element in a tuple has its own type

In both Haskell and Python, you can give our functions type declarations. The below function will take three elements and add them together. We will specify the type of the elements as integer.

| Haskell  | Python |
| --- | --- |
| ```addThree :: Int -> Int -> Int -> Int ; addThree x y z = x + y + z```   | <code>def addThree(x:int, y:int, z:int):</code> <br /> <code> &emsp; answer = x + y + z </code> <br /> <code> &emsp; &emsp;&emsp; &emsp;return int(answer)</code>|
| ```addThree 10 100 1000```   | ```>>> addThree(10,100,1000)``` |
| 1110 | 1110|
| ``` :t addThree```   | ```>>> type(addThree)``` |
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

This for types whose values can be put in some order. Lets have a look at some examples.

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

In Haskell the ```read``` class type can be considered the opposite of the ```show``` class type. 
