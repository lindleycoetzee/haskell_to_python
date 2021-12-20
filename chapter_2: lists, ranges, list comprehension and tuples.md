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

Please note that by using ```insert``` in Python you fundamentally change the list. Haskell the original list is still intact. 
If you want to get an element out of a list by index you use ```!!``` in Haskell. In Python you would pass the index number in square brackets after the list. 

| Haskell  | Python |
| --- | --- |
| ```ghci> "Haskell" !! 0```   | ```>>> "Haskell"[0]``` |
| 'H' |'H' |
| ```ghci> [1,2,3,4,5,6,7,8,9] !! 3```   | ```>>>  [1,2,3,4,6,7,8,9][3]``` |
| 4 | 4 |

Lists can also contain lists making it a list of lists. Below we create a list of lists and apply some of the functions we just learned. 

| Haskell  | Python |
| --- | --- |
| ```ghci> z = [[1,2,3],[4,5,6],[7,8,9]]```   | ```>>> numberList2 = [5,6,7,8]``` |
| ```ghci> z```   | ```>>> z``` |
| [[1,2,3],[4,5,6],[7,8,9]] | [[1,2,3],[4,5,6],[7,8,9]] |
| ```ghci> z !! 0```   | ```>>> z[0]``` |
| [1,2,3] | [1,2,3]]] |
| ```ghci> z ++ [[0,0,0]]```   | ```>>> z + [[0,0,0]]``` |
| [[1,2,3],[4,5,6],[7,8,9],[0,0,0]] | [[1,2,3],[4,5,6],[7,8,9],[0,0,0]] |
| ```ghci> [9,9,9]:z```   | ```>>> z.insert(0,[[9,9,9]])``` |
|  | ```>>> z ``` |
| [[9,9,9],[1,2,3],[4,5,6],[7,8,9]] | [[9,9,9],[1,2,3],[4,5,6],[7,8,9]] |

Lists are compared in lexicographical order, which more or less saying alphabetical order. 

| Numerical order  | Lexicographical order |
| --- | --- |
| 1,2,15,18   | 1,15,18,2 |

Let us do some comparisons on lists. 

| Haskell  | Python |
| --- | --- |
| ```ghci> [1,2,3] < [4,5,6]```   | ```>>> [1,2,3] < [4,5,6]``` |
| True |True |
| ```ghci> [5,7,3] > [4,5,6]```   | ```>>> [5,7,3] > [4,5,6]``` |
| True |True |
| ```ghci> [15,20] < [10,15,6]```   | ```>>> [15,20] < [10,15,6]``` |
| False |False |
| ```ghci> [5,3] == [5,3]```   | ```>>> [5,3] == [5,3]``` |
| True |True |
| ```ghci> [5,3] /= [5,3]```   | ```>>> [5,3] != [5,3]``` |
| False |False |

Now let us try out some basic list functions. Most of the below functions for Haskell are built-in. For almost all of them we will use [slicers](https://www.geeksforgeeks.org/python-list-slicing/) in Python. See the below table showing the functions and with their descriptions. The data used for the below workings will be as follows : ```myList = [1,2,3,4,5,6,7,8,9]``` and ``` emptyList = [] ```

| Haskell  | Python | Description |
| ---------- | ---------- | --- |
| ```ghci> head myList```   | ```>>> myList[0]``` | Returns the first element of a list |
| 1 |1 | |
| ```ghci> tail myList```   | ```>>> myList[1:] ``` | Returns all the elements of a list except the head |
| [2,3,4,5,6,7,8,9] |[2,3,4,5,6,7,8,9] | |
| ```ghci> last myList```   | ```>>> myList[-1]``` | Returns the last element of a list |
| 9 |9 | |
| ```ghci> init myList```   | ```>>> myList[:-1]``` | Returns all the elements of a list except the last element |
| [1,2,3,4,5,6,7,8] |[1,2,3,4,5,6,7,8] | |
| ```ghci> length myList ```   | ```>>> len(myList) ``` | Returns the number of elements in a list |
| 9 |9 | |
| ```ghci> null myList ```   | ```>>> myList != None ``` | Returns ``` True ``` is list is empty and ```False``` if list is not empty |
| False |False | |
| ```ghci> null emptyList ```   | ```>>> emptyList != None ``` | Returns ``` True ``` if list is empty and ```False``` if list is not empty |
| True |True | |
| ```ghci> reverse myList```   | ```>>> myList.reverse()``` | Returns all the elements of a list except the last element |
|    | ```>>> myList``` | In Python the original list gets updated to a reversed list |
| [9,8,7,6,5,4,3,2,1]| [9,8,7,6,5,4,3,2,1]| |
| ```ghci> take 5 myList```   | ```>>> myList[:5]``` | Returns the indicated number of elements of a list, starting from the beginning. |
| [1,2,3,4,5] | [1,2,3,4,5] | |
| ```ghci> drop 5 myList```   | ```>>> myList[5:]``` | Drops the indicated number of elements of a list, starting from the beginning, and returns the remaining elements |
| [6,7,8,9]] | [6,7,8,9] | |
| ```ghci> minimum myList```   | ```>>> min(myList)``` | Returns the smallest element in a list |
| 1 | 1 | |
| ```ghci> maximum myList```   | ```>>> max(myList)``` | Returns the largest element in a list |
| 9 | 9 | |
| ```ghci> sum myList```   | ```>>> sum(myList)``` | Returns the largest element in a list |
| 45 | 45 | |
| ```ghci> product myList```   | ```>>> import math``` | Returns the product of all the elements in a list |
|    | ```>>> math.prod(myList)``` | We need to import math to use the ```prod``` function |
| 362880 | 362880 | |
| ```ghci> 6 `elem` myList ```   | ```>>> 6 in myList ``` | Returns ``` True ``` if the element in the list and ```False``` if the element is not in the list|
| True |True | |
| ```ghci> 10 `elem` myList ```   | ```>>> 10 in myList ``` | Returns ``` True ``` if the element in the list and ```False``` if the element is not in the list|
| False |False | |


### **Ranges**


### **List comprehension**


### **Tuples**
