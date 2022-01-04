# Chapter 1 - Basic arithmetic, Equality, Booleans, Functions and If Statements

### **Basic arithmetic**


| Haskell  | Python |
| --- | --- |
| ```ghci> 12 + 10```   | ```>>> 12 + 10``` |
| 22  | 22  |
| ```ghci> 2 * 17```   | ```>>> 2 * 17``` |
| 34  | 34  |
| ```ghci> 1441 - 41```   | ```>>> 1441 - 41``` |
| 1400  | 1400  |
| ```ghci> 10 / 8```   | ```>>> 10 / 8``` |
| 1.25  | 1.25  |

In Haskell you need to wrap the negative numbers in parenthesis (round brackets) otherwise you will get an error.

| Haskell  | Python |
| --- | --- |
| ```ghci> 18 * (-10)```   | ```>>> 18 * -10``` |
| -180  | -180  |
    
### **Boolean expressions**
  
Boolean values in both Haskell and Python are ```True``` and ```False```. Below is a table showing the Boolean operators for Haskell and Python.

| Operator | Haskell  | Python |
|---| --- | --- |
|Conjunction| <code> &#124;&#124;</code>   | ```and``` |
|Disjunction| <code> &&</code>   | ```or``` |
|Negate| <code> not</code>   | ```not``` |
|Equality| <code> ==</code>   | ```==``` |
|Inequality| <code> /=</code>   | ```!=``` |

Using the above operators, let us look at how to use them.
 
| Haskell  | Python |
| --- | --- |
| ```ghci> True && False ```   | ```>>> True and False ``` |
| False  | False  |
| ```ghci> True && True```   | ```>>> True and True``` |
| True  | True  |
| <code>ghci> False &#124;&#124; True</code>  | <code>>>> False or True</code> |
| True  | True  |
| ```ghci> not False```   | ```>>> not False ``` |
| True  | True  |
| ```ghci> not (True && True)```   | ```>>> not (True & True)   ``` |
| True  | True  |
    
### **Testing for equality**
 
In Haskell we use ```/=``` (not equal to) while in Python we use ```!=```.

| Haskell  | Python |
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
| False  | False  |

### **Functions**

In Haskell you separate the function and the parameter with a space. In Python you wrap the parameter in parenthesis and the parameters are separated by commas. Also, note that these functions in Python can take many parameters while they are limited to 2 in Haskell. 

| Haskell  | Python |
| --- | --- |
| ```ghci> min 9 10   ```   | ```>>> min(9, 10)  ``` |
| 9  | 9  |
| ```ghci> min 3.4 3.2 ```   | ```>>> min(3.4, 3.2, 1.5)``` |
| 3.2  | 1.5  |
| ```ghci> max 100 101 ```   | ```>>> max(100, 101, 102, 103)``` |
| 101  | 103  |

### **User defined functions**

In Haskell, the way you define a function is as follows. First type the function name, then a space, then the parameter. In Python you define a function by first typing ```def```, then a space, then the function name, then the parameters inside parenthesis ending with a ```:```. On the lines below the function, you need explain what the function does. The lines below need to be indented. If I did a horrible job of explaining this, hopefully the below code snippets will give you a better idea.

| Haskell  | Python |
| --- | --- |
| ```addTen x = x + 10  ```   | <code> def addTen(x):</code> <br /> <code>&emsp; x = x + 10</code> <br /> <code>&emsp; return x</code> |

You can type the above Haskell code in your favourite text editor (I'm using Notepad++) and save it as first.hs. Now navigate to the where you have saved your file and run **ghci** from there. Once you are inside **GHCi**, type ```:l first```. Once you do that your script will be loaded and now we can try it out. 
For Python you can save the file as first.py and run it in any IDE or text editor. 

| Haskell  | Python |
| --- | --- |
| ```addTen 9 ```| ```print(addTen(9))``` |
| 19  | 19  |
| ```addTen 10 + addTen 30 ```| ```print(addTen(10) + addTen(30))``` |
| 60  | 60  |
    
We can write another function that includes our first function. 

| Haskell  | Python |
| --- | --- |
| ```addTentimesTwo x = addTen x * 2  ```   | <code>def addTentimesTwo(x):</code> <br /> <code>&emsp; y = addTen(x) * 2</code> <br /> <code>&emsp; return y</code> |

The above function takes a number, adds 10, then multiplies it with 2. So in basic algebra is would be **(x + 10) * 2**. We can run the code and see the results.
| Haskell  | Python |
| --- | --- |
| ```addTentimesTwo 25 ```| ```print(addTentimesTwo(25))``` |
| 70  | 70  |
| ```addTentimesTwo 25 + addTentimesTwo 10 ```| ```print(addTentimesTwo(25) + addTentimesTwo(10))``` |
| 110  | 110  |

The functions in both Haskell and Python do not have to be in a particular order. Order does not matter because we are just defining two functions. However, user defined function names cannot start with a capital letter.

### **If statements**

Regarding if statements, the main difference between Haskell and Python is that the "**else**" is necessary in Haskell while it is optional in Python. Let us write a function that squares a number equal to or below 10 and returns the same number is more than 10. 

| Haskell  | Python |
| --- | --- |
| <code>sqaureNumber x = if x > 10</code> <br /> <code>    &emsp;&emsp; &emsp;&emsp;&emsp; &emsp;&emsp;&emsp; &emsp; then x</code> <br /> <code>    &emsp;&emsp; &emsp;&emsp;&emsp; &emsp;&emsp;&emsp; &emsp; else x^2</code> | <code>def squareNumber(x):</code> <br /> <code> &emsp; if x < 10:</code> <br /> <code> &emsp; &emsp;&emsp; &emsp;x = x ** 2</code> <br /> <code> &emsp;  else:</code> <br /> <code> &emsp; &emsp;&emsp; &emsp;x </code> <br /> <code> &emsp;  return x </code> |

The main reason the Haskell function was coded across three lines is for readability. You can write the same code in one line. With Python however, you cannot write a user defined function in a single line. You should use a lambda function. 

| Haskell  | Python |
| --- | --- |
| ```sqaureNumber x = if x > 10 then x else x^2 ```| ```squareNumber = lambda x: x if x > 10 else x ** 2``` |
