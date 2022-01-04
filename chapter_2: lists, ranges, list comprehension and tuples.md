# Chapter_2: Lists, Ranges, List Comprehension and Tuples

_Most of the functions in this chapter can be written across one line but are cut off or written across multiple lines for readability._

### **Lists**
Lists have a general structure in Haskell. This means that a list can contain strings or integers but not both. This is not the case in Python. In Python, you can have list that that contain a mix of data types. Python lists can also contain other lists. For both Haskell and Python lists are surrounded by square brackets and data types in the list are separated by commas.

| Haskell  | Python |
| --- | --- |
| ```ghci> numberList = [1,2,3,4]```   | ```>>> numberList = [1,2,3,4]``` |
| ```ghci> numberList```   | ```>>> numberList``` |
| [1, 2, 3, 4]  | [1, 2, 3, 4]  |

If you try to create a list using different data types in Haskell you will get an error while in Python your code will execute. 

If we want to concatenate two lists we use ```++``` in Haskell and ```+``` in Python. 

| Haskell  | Python |
| --- | --- |
| ```ghci> numberList2 = [5,6,7,8]```   | ```>>> numberList2 = [5,6,7,8]``` |
| ```ghci> numberList ++ numberList2```   | ```>>> numberList + numberList2``` |
| [1, 2, 3, 4, 5, 6, 7, 8] | [1, 2, 3, 4, 5, 6, 7, 8] |
| ```ghci> textList = ["how", "are", "you"]```   | ```>>> textList = ["how", "are", "you"]``` |
| ```ghci> textList2 = ["i", "am", "fine"]```   | ```>>> textList2 = ["i", "am", "fine"]``` |
| ```ghci> textList ++ textList2```   | ```>>> textList + textList2``` |
| ['how', 'are', 'you', 'i', 'am', 'fine'] | ['how', 'are', 'you', 'i', 'am', 'fine'] |

By using the ```++``` in Haskell and ```+``` in Python, we are appending .i.e. we are adding the string, integer or list to the back of our list. If we want to append from the front we need to use ```:``` in Haskell and ```insert``` in Python.  

| Haskell  | Python |
| --- | --- |
|    | ```>>> numberList.insert(0,77)``` |
| ```ghci> 77: numberList``` | ```>>> numberList``` |
| [77,1,2,3,4]| [77, 1, 2, 3, 4] |
|    | ```>>> textList.insert(0,"hi")``` |
| ```ghci> "hi" : textList``` | ```>>> textList``` |
| ['hi', 'how', 'are', 'you'] | ['hi', 'how', 'are', 'you'] |

Please note that by using ```insert``` in Python you fundamentally change the list. Haskell the original list is still intact. 
If you want to get an element out of a list by index you use ```!!``` in Haskell. In Python, you would pass the index number in square brackets after the list. 

| Haskell  | Python |
| --- | --- |
| ```ghci> "Haskell" !! 0```   | ```>>> "Haskell"[0]``` |
| 'H' |'H' |
| ```ghci> [1,2,3,4,5,6,7,8,9] !! 3```   | ```>>>  [1,2,3,4,6,7,8,9][3]``` |
| 4 | 4 |

Lists can also contain lists making it a list of lists. Below we create a list of lists and apply some of the functions we just learned. 

| Haskell  | Python |
| --- | --- |
| ```ghci> z = [[1,2,3],[4,5,6],[7,8,9]]```   | ```>>> z = [[1,2,3],[4,5,6],[7,8,9]]``` |
| ```ghci> z```   | ```>>> z``` |
| [[1,2,3],[4,5,6],[7,8,9]] | [[1,2,3],[4,5,6],[7,8,9]] |
| ```ghci> z !! 0```   | ```>>> z[0]``` |
| [1,2,3] | [1,2,3]]] |
| ```ghci> z ++ [[0,0,0]]```   | ```>>> z + [[0,0,0]]``` |
| [[1,2,3],[4,5,6],[7,8,9],[0,0,0]] | [[1,2,3],[4,5,6],[7,8,9],[0,0,0]] |
|   | ```>>> z.insert(0,[[9,9,9]])``` |
| ```ghci> [9,9,9]:z```  | ```>>> z ``` |
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

Now let us try out some basic list functions. Most of the below functions for Haskell are built-in. For almost all of them we will use [slicers](https://www.geeksforgeeks.org/python-list-slicing/) in Python. See the below table showing the functions and with their descriptions. The data used for the below workings will be as follows : ```myList = [1,2,3,4,5,6,7,8,9]``` and ``` emptyList = [] ```.

| Haskell &emsp;&emsp;&emsp; &emsp;&emsp;&emsp;&emsp;&emsp;&emsp; | Python &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;| Description |
| ---------- | ---------- | --- |
| ```ghci> head myList```   | ```>>> myList[0]``` | Returns the first element of a list. |
| 1 |1 | |
| ```ghci> tail myList```   | ```>>> myList[1:] ``` | Returns all the elements of a list except the head. |
| [2,3,4,5,6,7,8,9] |[2,3,4,5,6,7,8,9] | |
| ```ghci> last myList```   | ```>>> myList[-1]``` | Returns the last element of a list. |
| 9 |9 | |
| ```ghci> init myList```   | ```>>> myList[:-1]``` | Returns all the elements of a list except the last element. |
| [1,2,3,4,5,6,7,8] |[1,2,3,4,5,6,7,8] | |
| ```ghci> length myList ```   | ```>>> len(myList) ``` | Returns the number of elements in a list. |
| 9 |9 | |
| ```ghci> null myList ```   | ```>>> myList != None ``` | Returns ``` True ``` is list is empty and ```False``` if list is not empty. |
| False |False | |
| ```ghci> null emptyList ```   | ```>>> emptyList != None ``` | Returns ``` True ``` if list is empty and ```False``` if list is not empty. |
| True |True | |
| ```ghci> reverse myList```  | ```>>> myList.reverse()``` | Reverses the order of a list. |
|   | ```>>> myList``` |  |
| [9,8,7,6,5,4,3,2,1]| [9,8,7,6,5,4,3,2,1]| In Python the original list gets updated to a reversed list. |
| ```ghci> take 5 myList```   | ```>>> myList[:5]``` | Returns the indicated number of elements of a list, starting from the beginning. |
| [1,2,3,4,5] | [1,2,3,4,5] | |
| ```ghci> drop 5 myList```   | ```>>> myList[5:]``` | Drops the indicated number of elements of a list, starting from the beginning, and returns the remaining. elements |
| [6,7,8,9]] | [6,7,8,9] | |
| ```ghci> minimum myList```   | ```>>> min(myList)``` | Returns the smallest element in a list. |
| 1 | 1 | |
| ```ghci> maximum myList```   | ```>>> max(myList)``` | Returns the largest element in a list. |
| 9 | 9 | |
| ```ghci> sum myList```   | ```>>> sum(myList)``` | Returns the sum of all the elements in a list. |
| 45 | 45 | |
|   | ```>>> import math``` | In Python we need to import math to use the ```prod``` function. |
|  ```ghci> product myList```   | ```>>> math.prod(myList)``` | Returns the product of all the elements in a list. |
| 362880 | 362880 | |
| ```ghci> 6 `elem` myList ```   | ```>>> 6 in myList ``` | Returns ``` True ``` if the element in the list and ```False``` if the element is not in the list.|
| True |True | |
| ```ghci> 10 `elem` myList ```   | ```>>> 10 in myList ``` | Returns ``` True ``` if the element in the list and ```False``` if the element is not in the list.|
| False |False | |


### **Ranges**

Ranges are like lists that are sequentially enumerated. Enumerate means to count off or to name one by one. In Haskell, you can make ranges of integers and letters but in Python, ranges are limited to integers only. In Haskell we specify a range by using ``` .. ``` in the middle our list. In Python we will use the built-in ``` range() ``` function with the [unpacking operator](https://www.python4networkengineers.com/posts/python-intermediate/unpacking_in_python/) ``` * ```.

| Haskell  | Python |
| --- | --- |
| ```ghci> [1..9]```   | ```>>> [*range(1,10)]``` |
| [1,2,3,4,5,6,7,8,9] |[1,2,3,4,5,6,7,8,9] |
| ```ghci> ['a'..'k']```   | ```>>> [*range('a','k')]``` |
| "abcdefghijk" |TypeError: 'str' object cannot be interpreted as an integer|

You can also step between ranges

| Haskell  | Python |
| --- | --- |
| ```ghci> [5,10..50]```   | ```>>> [*range(5,51,5)]``` |
| [5,10,15,20,25,30,35,40,45,50] |[5,10,15,20,25,30,35,40,45,50] |
| ```ghci> [1,7..25]```   | ```>>> [*range(1,26,6)]``` |
| [1,7,13,19,25] |[1,7,13,19,25]|

We can use the ``` replicate ``` function in Haskell if you can to have a list containing the same element.

| Haskell  | Python |
| --- | --- |
| ```ghci> replicate 13 5```   | ```>>> [5] * 13``` |
| [5,5,5,5,5,5,5,5,5,5,5,5,5] |[5,5,5,5,5,5,5,5,5,5,5,5,5]|
| ```ghci> replicate 4 "haskell"```   | ```>>> ["haskell"] * 4``` |
| ["haskell","haskell","haskell","haskell"] |["haskell","haskell","haskell","haskell"]|


### **List comprehension**

A list comprehension is a way of creating a list from an existing list and is written across one line. Let’s create two list comprehensions. The first one adds five to a list and the second one multiplies each number in the list by 3.

| Haskell  | Python |
| --- | --- |
| <code>ghci> [x + 5 &#124; x <-[1..7]] </code>  | ```>>> [5] * 13 ```|
| [6,7,8,9,10,11,12]|[6,7,8,9,10,11,12]|
| <code>ghci> [x * 3 &#124; x <-[1..5]]</code>   | ```>>> [x * 3 for x in range(1,6)]``` |
| [3,6,9,12,15] |[3,6,9,12,15]|

Now let’s add a condition or a predicate to our list comprehension. The predicate acts like a filter. Below we will use the same two list comprehensions from above but only display the numbers greater than or equal to 10. 

| Haskell  | Python |
| --- | --- |
| <code>ghci> [x + 5 &#124; x <-[1..7], x + 5 >= 10]</code>   | ```>>> [x + 5 for x in range(1,8) if x + 5 >=  10]``` |
| [10,11,12]|[10,11,12]|
| <code>ghci> [x * 3 &#124; x <-[1..5], x * 3 >= 10]</code>   | ```>>> [x * 3 for x in range(1,6) if x * 3 >= 10]``` |
| [12,15] |[12,15]|

Next, let us get all the numbers between 40 and 80 when the remainder is 5, if divided by 8.

| Haskell  | Python |
| --- | --- |
| <code>ghci> [x &#124; x <-[40..80], x `mod` 8 == 5]</code>   | ```>>> [x for x in range(40,81) if x % 8 == 5]``` |
| [45,53,61,69,77]|[45,53,61,69,77]|

We can also assign multiple predicated to our list comprehensions. Say we wanted all the numbers between 1 and 10 not to include 1, 4 and 9. We will need to separate our conditions with a ```,``` in Haskell and with ```and``` in Python. 

| Haskell  | Python |
| --- | --- |
| <code>ghci> [x &#124; x <-[1..10], x/=1, x/=4, x/=9]</code>   | ```>>> [x for x in range(1,11) if x != 1 and x != 4 and x != 9]``` |
| [2,3,5,6,7,8,10]|[2,3,5,6,7,8,10]|

We can also draw values from many lists and the result will be a list. We will create a list comprehension where the first number in the first list is added to all the numbers in the second list and will continue for all the numbers in the first list. If that sounds confusing, I hope the code will do a better job at explaining it. 

| Haskell  | Python |
| --- | --- |
| <code>ghci> [x + y &#124; x <- [10, 11, 12], y<- [100,200,300]]</code>   | ```>>> [x + y for x in [10,11,12] for y in[100,200,300]]``` |
| [110,210,310,111,211,311,112,212,312]|[110,210,310,111,211,311,112,212,312]|

So x1(10) + y1 (100) = 110, x1(10) + y2 (200) = 210 and x1(10) + y3 (300) = 310. We go on until the last number of the first list, x3(12) is added to the last number of the second list, y3 (300, which will give us 312. Now let us do another one but instead of addition we will do multiplication.

| Haskell  | Python |
| --- | --- |
| <code>ghci> [x * y &#124; x <- [3,6,9], y <- [10,20,30]]</code>   | ```>>> [x * y for x in [3,6,9] for y in [10,20,30]]``` |
| [30,60,90,60,120,180,90,180,270]|[30,60,90,60,120,180,90,180,270]|

We can again add a condition.

| Haskell  | Python |
| --- | --- |
| <code>ghci> [x * y &#124; x <- [3,6,9], y <- [10,20,30], x * y > 150 ]</code>   | ```>>> [x * y for x in [3,6,9] for y in [10,20,30] if x * y > 150]``` |
| [180,180,270]|[180,180,270]|

Finally, lets create a nested list comprehension on a list of lists.

| Haskell  | Python |
| --- | --- |
| <code>ghci> let xyz = [[1,2,3],[4,5,6],[7,8,9]]</code>   | ```>>> xyz = [[1,2,3],[4,5,6],[7,8,9]]``` |
| <code>ghci> [[x &#124; x <- xy, even x ] &#124; xy <- xyz]</code>   | ```>>> [[y for y in x if y % 2 == 0] for x in xyz]``` |
| [[2],[4,6],[8]]|[[2],[4,6],[8]]|

### **Tuples**
 
Tuples are similar to lists. In Haskell and Python, tuples contain a mix of data types. For both Haskell and Python tuples are surrounded by round brackets and the data types are separated by commas. The main difference between lists and tuples are that tuples are immutable which means tuples don’t change. You cannot append elements to a tuple. So that means tuples are fixed in size, so use them when you know how many elements you need. 

| Haskell | Python | Description |
| ---------- | ---------- | --- |
| ```ghci> (1,2)```   | ```>>> (1,2)``` | A tuple of 2 elements is called a _pair_  |
| (1,2) |(1,2) | |
| ```ghci> ("i", "love", "coding")```   | ```>>> ("i", "love", "coding") ``` | A tuple of 3 elements is called a _triple_ |
| ("i", "love", "coding") |("i", "love", "coding") | |
| ```ghci> ("i", 8, "fish")```   | ```>>> ("i", 8)``` | Pairs and triples are treated as different data types  |
| ("i", 8, "fish") |("i", 8) | |
  
Let us look at some common functions for pairs in Haskell. The below functions will only work on pairs. They will not work for triples, 4-tuples etc.

| Haskell  | Python |
| --- | --- |
| ```ghci> fst ("i",8)```   | ```>>> ("i",8)[0]``` |
| "i" |"i" |
| ```ghci> snd (1,2)```   | ```>>> (1,2)[1]``` |
| 2|2|

The ```zip``` function produces a pair of lists by joining the matching elements according to their position.

| Haskell  | Python |
| --- | --- |
| ```ghci> zip [1,2,3] ["a","b","c"]```   | ```>>> list(zip([1,2,3],["a","b","c"]))``` |
| [(1,"a"),(2,"b"),(3,"c")] |[(1,"a"),(2,"b"),(3,"c")] |
| ```ghci> zip [4,8..16] ["we", "times", "by", "four"]```   | ```>>> list(zip(range(4,17,4),["we", "times", "by", "four"]))``` |
| [(4,"we"),(8,"times"),(12,"by"),(16,"four")]|[(4,"we"),(8,"times"),(12,"by"),(16,"four")]|

Pairs can contain different data types. ```zip``` takes elements of different data types and works on lists with different lengths. 

| Haskell  | Python |
| --- | --- |
| ```ghci> zip [1,2,3,4,5] ["cricket", "soccer", "rugby"]```   | ```>>> list(zip([1,2,3,4,5],["cricket", "soccer", "rugby"]))``` |
| [(1,"cricket"),(2,"soccer"),(3,"rugby")] |[(1,"cricket"),(2,"soccer"),(3,"rugby")] |

Since the shorted list only contains 3 elements the result is a 3 element list. We can also zip a finite list with an infinite list. For this to work in Python, we would need to import ```itertools``` .

| Haskell  | Python |
| --- | --- |
| ```ghci> ```   | ```>>> import itertools``` |
| ```ghci> zip [3,6..] ["grape", "apple", "orange", "pear"]```   | ```>>> list(zip(itertools.count(start=3,step=3),["grape", "apple", "orange", "pear"]))``` |
| [(3,"grape"),(6,"apple"),(9,"orange"),(12,"pear")] | [(3,"grape"),(6,"apple"),(9,"orange"),(12,"pear")] |
 
#### **Finding the right triangle**

We will end with a problem that combines tuples with list comprehensions. We will create a function to find a right-angled triangle that satisfies the following conditions:
* the lengths of all sides are integers(whole numbers);
* the length of each side is equal to or less than 10; and 
* the triangles perimeter(sum of all the side lengths) is equal to 24.

Before we start writing our function, we need to know what the properties of a right-angled triangle are. Right-angled triangles or right triangles:
* have one angle that is equal to 90 degrees;
* the longest side of a right triangle is called the _hypotenuse_; and
* the hypotenuse is equal to the sum of the remaining 2 sides(_Pythagorean theorem (a^2 + b^2 == c^2_).

Armed with that knowledge we can now write our function. We will use a common practice in functional programming. We will start with a certain set of solutions and then transform and/or filter them until you have narrowed it down to the solution you are looking for. For Python, we will need to import the ```product``` function from the ```intertools``` library. 
 
| Haskell | Python | Description |
| ---------- | ---------- | --- |
|  | ```>>> from itertools import product``` | Importing needed function in Python. |
| <code>ghci> let triangle = [(a,b,c) &#124; c <- [1..10], a <- [1..10], b<- [1..10]]</code>   | ```>>> triangle = [x for x in product(range(1,11), repeat = 3)]``` | First, we will get all possible triples (triangles) that are equal to or less than 10. |
| ```ghci> length triangle```   | ```>>> len(triangle)``` | We will only print the length of the list since it contains 1,000 elements. |
| 1000 |1000 | |
| <code> ghci> let rightTriangles = [(a,b,c) &#124; c <- [1..10], a <- [1..c], b <- [1..a], a^2 + b^2 ==c^2]</code>    | ```>>> rightTriangles = [x for x in product(range(1,11), repeat = 3) if x[2] <= 10 and x[1] < x[2] and x[0] < x[1] and x[0]**2 + x[1]**2 == x[2]**2] ``` | Second, we add a predicate to only show right triangles. Note that _a_ may not be bigger than _c_ and b needs to be smaller than _a_ because _a_ and _b_ are the smaller sides.|
| ```ghci> rightTriangles```   | ```>>> rightTriangles``` | |
| [(4,3,5),(8,6,10)]|[(3,4,5),(6,8,10)] |Now we have narrowed our solutions to only 2.  |
| <code> ghci> let rightTriangles = [ (a,b,c) &#124; c <- [1..10], a <- [1..c], b <- [1..a], a^2 + b^2 == c^2, a+b+c == 24]</code>    | ```>>> rightTriangles = [x for x in product(range(1,11), repeat = 3) if x[2] <= 10 and x[1] < x[2] and x[0] < x[1] and x[0]**2 + x[1]**2 == x[2]**2 and x[0] + x[1] + x[2] == 24]``` | Lastly, we ensure that all the lengths of the triangle add up to 24.  |
| ```ghci> rightTriangles```   | ```>>> rightTriangles``` | |
| [(8,6,10)] |[(6,8,10)] | |
 

