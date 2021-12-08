# Chapter 1 - The basics

**Basic arithmetic**


    --haskell code
    ghci> 12 + 10
    22
    ghci> 2 * 17
    34
    ghci> 1441 – 41
    1400
    ghci> 10 / 8
    1.25


    ##python code
    >>> 12 + 10
    22
    >>> 2 * 17
    34
    >>> 1441 – 41
    1400
    >>> 10 / 8
    1.25

With haskell you need to wrap the negative numbers in parenthesis(round brackets) otherwise you will get an error.

    --haskell code
    ghci> 18 * (-10)
    -180
    
        ##python code
    >>> 18 * -10
    -180
    
  **Bolean expressions**
  
 In haskell we use **&&**(and) and **||**(or) while in python we use **&** and **|**.
  
    --haskell code
    ghci> True && False  
    False  
    ghci> True && True  
    True  
    ghci> False || True  
    True   
    ghci> not False  
    True  
    ghci> not (True && True)  
    False 
    
    ##python code
    >>> True & False  
    False  
    >>> True & True  
    True  
    >>> False | True  
    True   
    >>> not False  
    True  
    >>> not (True & True)  
    False
  
 **Testing for equality**
 
In haskell we use **/=**(not equal to) while in python we use **!=**.

    --haskell code
    ghci> 5 == 5  
    True  
    ghci> 1 == 0  
    False  
    ghci> 5 /= 5  
    False  
    ghci> 5 /= 4  
    True  
    ghci> "hello" == "hello"  
    True  
    ghci> "hello" /= "hello"  
    False 
    
    ##python code
    >>> 5 == 5  
    True  
    >>> 1 == 0  
    False  
    >>> 5 != 5  
    False  
    >>> 5 != 4  
    True  
    >>> "hello" == "hello"  
    True  
    >>> "hello" != "hello"  
    False 

**Functions**

In haskell you separate the function and the parameter with a space. In python you wrap the parameter in parenthesis and the parameters are seperated by commas. Also not that these functions in python can take lots of parameters while they are limited to 2 in haskell. 

    --haskell code
    ghci> min 9 10  
    9  
    ghci> min 3.4 3.2  
    3.2  
    ghci> max 100 101  
    101  
    
    ##python code
    >>> min(9, 10) 
    9  
    >>> min (3.4, 3.2, 1.5)
    1.5
    >>> max (100, 101, 102, 103)  
    103

**User defined functions**
