# Chapter_2: Lists, ranges, list comprehension and tuples

### **Lists**
Lists have a general structure in Haskell. This means that a list can contain strings or integers but not both. This is not the case in Python. In Python you can have list that that contain a mix of data types. Python lists can also contain other lists. For both Haskell and Python lists are surrounded by sqaure brackets and data tyoes in the list are separated by commas.

| Haskell  | Python |
| --- | --- |
| ```ghci> numberList = [1,2,3,4]```   | ```>>> numberList = [1,2,3,4]``` |
| ```ghci> numberList```   | ```>>> numberList``` |
| [1, 2, 3, 4]  | [1, 2, 3, 4]  |

If you try to create a list using different data types in Haskell your will get an error while in Python your code will execute. 

If we want to concatenate two lists we use ```++``` in Haskel and ```+``` in Python. 

| Haskell  | Python |
| --- | --- |
| ```ghci> numberList2 = [5,6,7,8]```   | ```>>> numberList2 = [5,6,7,8]``` |
| ```ghci> numberList ++ numberList2```   | ```>>> numberList + numberList2``` |
| [1, 2, 3, 4, 5, 6, 7, 8] | [1, 2, 3, 4, 5, 6, 7, 8] |
| ```ghci> textList = ["how", "are", "you"]```   | ```>>> textList = ["how", "are", "you"]``` |
| ```ghci> textList2 = ["i", "am", "fine"]```   | ```>>> textList2 = ["i", "am", "fine"]``` |
| ```ghci> textList ++ textList2```   | ```>>> textList + textList2``` |
| ['how', 'are', 'you', 'i', 'am', 'fine'] | ['how', 'are', 'you', 'i', 'am', 'fine'] |

By using the ```++``` in Haskel and ```+``` in Python, we are appending .i.e we are adding the string, integer or list to the back of our list. If we want to append from the front we need to use ```:``` in Haskell and ```insert``` in Pyhon  

| Haskell  | Python |
| --- | --- |
| ```ghci> 77: numberList```   | ```>>> numberList.insert(0,77)``` |
| [77,1,2,3,4] | ```>>> numberList``` |
| | [77, 1, 2, 3, 4] |
| ```ghci> "hi" : textList```   | ```>>> textList.insert(0,"hi")``` |
| ['hi', 'how', 'are', 'you']| ```>>> textList``` |
| | ['hi', 'how', 'are', 'you'] |

### **Ranges**


### **List comprehension**


### **Tuples**
