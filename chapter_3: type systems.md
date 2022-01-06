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

From the above you will notice in Haskell that:
* explicit types start with a uppercase letter e.g Char, Bool and Num and
* each element in a tuple has its own type

In both Haskell and Python, you can label variables with a data type. We will use the function we made in

