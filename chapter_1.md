# Chapter 1 - The basics

**Basic arithmetic**


| haskell  | python |
| --- | --- |
| ```ghci> 12 + 10```   | ```>>> 12 + 10``` |
| 22  | 22  |
| ```ghci> 2 * 17```   | ```>>> 2 * 17``` |
| 34  | 34  |
| ```ghci> 1441 - 41```   | ```>>> 1441 - 41``` |
| 1400  | 1400  |
| ```ghci> 10 / 8```   | ```>>> 10 / 8``` |
| 1.25  | 1.25  |

With haskell you need to wrap the negative numbers in parenthesis(round brackets) otherwise you will get an error.

| haskell  | python |
| --- | --- |
| ```ghci> 18 * (-10)```   | ```>>> 18 * -10``` |
| -180  | -180  |
    
  **Bolean expressions**
  
 In haskell we use **&&**(and) and **||**(or) while in python we use **&** and **|**.
 
| haskell  | python |
| --- | --- |
| ```ghci> True && False ```   | ```>>> True & False ``` |
| False  | False  |
| ```ghci> True && True```   | ```>>> True & True``` |
| True  | True  |
| <code>ghci> False &#124;&#124; True</code>  | <code>>>> False &#124; True</code> |
| True  | True  |
| ```ghci> not False```   | ```>>> not False ``` |
| True  | True  |
| ```ghci> not (True && True)```   | ```>>> not (True & True)   ``` |
| True  | True  |
    
 **Testing for equality**
 
In haskell we use **/=**(not equal to) while in python we use **!=**.

| haskell  | python |
| --- | --- |
| ```ghci> 5 == 5  ```   | ```>>> 5 == 5  ``` |
| True  | True  |
| ```ghci> 1 == 0```   | ```>>> 1 == 0``` |
| False  | False  |
| ```ghci> 5 /= 5```   | ```>>> 5 != 5``` |
| False  | False  |
| ```ghci> 5 /= 4 ```   | ```>>> 5 != 4 ``` |
| True  | True  |
| ```ghci> "hello" == "hello" ```   | ```>>> "hello" == "hello"   ``` |
| True  | True  |
| ```ghci> "hello" /= "hello" ```   | ```>>> "hello" != "hello"   ``` |
| True  | True  |

**Functions**

In haskell you separate the function and the parameter with a space. In python you wrap the parameter in parenthesis and the parameters are seperated by commas. Also note that these functions in python can take lots of parameters while they are limited to 2 in haskell. 

| haskell  | python |
| --- | --- |
| ```ghci> min 9 10   ```   | ```>>> min(9, 10)  ``` |
| 9  | 9  |
| ```ghci> min 3.4 3.2 ```   | ```>>> min(3.4, 3.2, 1.5)``` |
| 3.2  | 1.5  |
| ```ghci> max 100 101 ```   | ```>>> max(100, 101, 102, 103)``` |
| 101  | 103  |

**User defined functions**

In haskell, the way you define a fucntion is as follows. First type the function name, then a space, then the parameter. In python you define a function by first typing "def", then a space, then the function name, then the parameters inside parenthesis ending with a colon(**:**). On the lines below the function you need explain what the function does. The lines below need to be indented. If I did a horibble job of explaining this, hopefully the below code snippets will give you a better idea.

| haskell  | python |
| --- | --- |
| ```addTen x = x + 10  ```   | <code>def addTen(x):</code> <br /> <code> &emsp; x = x + 10</code> <br /> <code> &emsp; print(x)</code> |

You can type the above haskell code in your favourite text editor(I'm using Notepad++) and save it as first.hs. Now navigate to the where you have saved your file and **ghci** from there. Once you are inside **GHCi**, type ```:l first```. Once you do that your script will be loaded and now we can try it out. 

