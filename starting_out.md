# Starting out

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
    ghci> True & False  
    False  
    ghci> True & True  
    True  
    ghci> False | True  
    True   
    ghci> not False  
    True  
    ghci> not (True & True)  
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
    ghci> 5 == 5  
    True  
    ghci> 1 == 0  
    False  
    ghci> 5 != 5  
    False  
    ghci> 5 != 4  
    True  
    ghci> "hello" == "hello"  
    True  
    ghci> "hello" != "hello"  
    False 
