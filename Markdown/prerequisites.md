---
title: Prerequisites
description: Prerequisites page
layout: "@main"
---

## **Prerequisites**
### Algorithms:
### Arrays and Lists:

Arrays are groups of items of the same type arranged sequentially. A list is similar to an array, except the items may be of different types. In both arrays and lists, each item in an array has an index, which refers to its position in the sequence. 

In Java, arrays must be initialized with a predetermined length, which cannot be changed. Arrays do not exist in Python. Lists in Python may be of any length, which can be changed. Java has a data structure called an ArrayList, which is an array that may have its length changed.

Arrays and lists are zero-indexed in both Python and Java, meaning the first item in an array or list has an index of 0, and not 1.

#### Initializing Arrays, Lists, and ArrayLists
##### Java

```java
//Initializing an array of type int and of length 10. (static array)
int[] array = new int[10];

//Initializing an ArrayList of type int. (ArrayList)
ArrayList<Integer> array = new ArrayList<Integer>();
```

As you see in the ArrayList with Java (compared to the array), you’ll notice that the ArrayList is an object and has to be instantiated with the ‘new’ keyword. Unlike the static array, the ArrayList is dynamic, meaning that you do not have to define a size when it is created. You can add and delete elements wherever you choose to in the array. More examples of ArrayList operations can be found through this [W3 Schools Article](https://www.w3schools.com/java/java_arraylist.asp "W3 Schools Article") as well as the [Java documentation](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html "Java documentation") for the ArrayList class.

##### Python
```python
#Initializing a list.
list = []

#Initializing a list with some items in it.
list = [0, 'a', 3.14, False]
```

Unlike Java, arrays, or lists, in Python do not have to be created with a pre-declared size. You can learn more about arrays in Python through this [W3 Schools Article](https://www.w3schools.com/python/python_lists.asp "W3 Schools Article") and the [Python documentation](https://docs.python.org/3/tutorial/datastructures.html "Python documentation").

#### Multidimensional Arrays and Lists

A two-dimensional array or list is simply an array of arrays or a list of lists. A three-dimensional array is an array of arrays of arrays. The pattern can be extended to any integer number of dimensions. Items can be located by the indexes of themselves within the array they are an immediate part of, and the indexes of the arrays the item is contained within.

##### Java
```java
//Initializing a two-dimensional array
int[][] twoDimentionalArray = new int[10][10];
```

As you can see, the Java two-dimensional array is a collection of two one-dimensional arrays as shown through the double brackets ‘[ ][ ]’ each symbolizing a one-dimensional array itself. In this two dimensional array, each object has two indexes. One with the ‘row’ and one with the ‘column.’ In Java, the typical convention for the index of two-dimensional arrays is $[row][column]$. Learn more about multidimensional arrays in Java through this [W3 Schools Article](https://www.w3schools.com/java/java_arrays_multi.asp "W3 Schools Article").

##### Python
```python
#Initializing an example of a 2D list.
list = [[1, 2, 3, 4, 5], [6,  7, 8, 9, 10], [11, 12, 13, 14, 15]]
```
Similar to the one-dimensional array, a size does not need to be declared in Python for a multidimensional array. You can see that it is still one list, but this time, the list is composed of lists inside the list itself. Each element in the list is also a list, creating a two dimensional aspect to it. So, if I wanted to access the number 6, it would be the first index of the list (remember, the indexes start at zero), and the zeroth index of the list at the first index. You can also picture it as a matrix. In the first row (zeroth index), I have a list with [1, 2, 3, 4, 5]. In my second row (first index), I have a list with [6, 7, 8, 9, 10], and the same with the third row (second index) with [11, 12, 13, 14, 15]. If I wanted to access the number 6, I would go to the first index and the zeroth index in that list.

***Question***: What is the difference between an array and a list?

*Solution*: Arrays exist in Java, but not in Python. They serve the same purpose: to arrange items of the same type sequentially.

***Question***: What does zero-indexing entail?

*Solution*: The first element in the array or list has an index of zero.

***Question***: What are multidimensional arrays?

*Solution*: Arrays, or lists, within themselves, arranging elements in rows and columns. Practical examples include chess boards or matrices.

***Challenge Task***: Make a representation of a tic-tac-toe board with a 2D array or a 2D list.

*Solution*: 
list = $[[“X”,”O”,”X”],[“O”,”X”,”O”],[“X”,”O”,”X”]]$;

### Bubble Sort:
The bubble sort is known as the ‘classic’ method of sorting when it comes to arrays. It is often the first method of sorting that is introduced because of its ease to understand conceptually. When you imagine sorting an array, you might imagine putting the largest element at the end, smallest element at the front, or comparing the element to the one next to it to see which belongs at which end (greater or smaller). The latter method is the same idea behind the bubble sort.

Let’s look at the example of what the Bubble Sort does below. Note that the example below briefly addresses the first few steps involved in the Bubble Sort.

![Bubble Sort Graphic 1](https://i.postimg.cc/4NvGNL2y/Prereq-1.png)

We start with an unordered array. Then, we look to the first index (index 0) which has an element of 20 in this case. Then, we’ll compare the element next to it which is 18. Since 20 is greater than 18, we’ll swap 20 and 18. Then, the algorithm looks to the next index. Since we just swapped 20 and 18, now 20 is in 18’s old position (index 1). We then compare this to the element next to it which is 14. Since 20 is greater than 14, we’ll swap 20 and 14. This happens so on and so forth. At the end of this first iteration, the greatest element will be at the end of the array.

Let’s look into this with a smaller array.

![Bubble Sort Graphic 2, Part 1](https://i.postimg.cc/QtpD9fNf/Screen-Shot-2022-11-04-at-9-02-54-AM.png)

![Bubble Sort Graphic 2, Part 2](https://i.postimg.cc/HnKhZtkx/Prereq-3.png)

![Bubble Sort Graphic 2, Part 3](https://i.postimg.cc/rpJYXTw7/Prereq-4.png)

Here, you see the full bubble sort. For each iteration, we look at the element at the front (index 0) and compare it to the element next to it until we approach the area of the array that is already sorted. Notice that after the first iteration, the greatest element is at the end of the array, and after the second iteration, the two greatest elements are at the end in sorted order. Once we reach that point of the array, no more comparisons should be made (for efficiency, since that area is already sorted). Then, we can stop the iteration, return to the front of the array, and do it over again.

To demonstrate how this sort algorithm looks in Java, the bubbleSort method is below:


```java
    public static void bubbleSort(int[] list)
    {
        for(int i = 1; i < list.length; i++)
        {
            for(int p = 0; p < list.length - i; p++)
            {
                if(list[p] > list[p+1])
                {
                    int y = list[p];
                    list[p] = list[p+1];
                    list[p+1] = y;
                }
            }
        }
    }
```

To start, we define an int $i$ with initial value $1$. This counts the number of passes that we will do in the array. Then, we define an int $p$ with initial value $0$. Like $i$, this is the index of the other element in the array that is being compared. Remember, in bubble sort, we are comparing two elements and swapping them subsequently through the array as shown in the illustration above.

Then, we check if $p$ is greater than the element in front of it. If it is, we swap them. We continue in this inner for-loop until we compare the entire list and the greatest element is at the end.

Then, our outer for-loop value of $i$ will increment, and we will do the comparisons again starting at the front of the array. A really cool part of this code is that you’ll notice the inner loop states $p < list.length - i$, which means our inner-loop does not have to traverse the full array - rather, it can stop at a certain point before it reaches the end on each subsequent pass. Why might that be? (*if you want a challenge, try to answer this before you move on to the next paragraph*)

Recall that the end of our list is sorted because at the end of the first pass, the greatest value is at the end of the array. The same applies for each pass after that. The next greatest element will be at the end of the array. This means we can stop each subsequent pass once we get to the part of the array that is already sorted, hence the $p < list.length - i$ rather than $p < list.length$.

***Exercise***: Use the bubble sort idea above to sort an array: $[5, 10, 2, 9, 7]$. Go through each pass and determine the final sorted array. What do you notice? Do you notice any alternative ways to sort this data?

*Solution*: Trace the code and you’ll notice a similar drawing/trace to the one above. You’ll likely have to go through 4 passes using the traditional bubble sort method. The next part of the question asks if you notice alternative ways to sort the data, and you probably thought of many. As you’ll see further on, there are many different algorithms to sort an array. There’s insertion sort (next section), selection sort, merge sort, quick sore, etc. Many of these algorithms vary in time-complexity, which you’ll read more on later in this section. For now, think of all the possibilities with different sorting algorithms.

### Insertion Sort:

**Before You Read**: Watch this [insertion sort demonstration](https://youtu.be/EdIKIf9mHk0 "insertion sort demonstration") for a way to visualize the insertion sort.

The bubble sort is the ‘elementary’ version of sorts. It does the trick in a very easy-to-understand way for humans, but it makes the computer do a little extra work. The insertion sort is very similar to the bubble sort in the way that it functions; however, it has a few kinks to it. Nonetheless, the insertion sort has a similar efficiency to the bubble sort. More about efficiency in the later section, though.

The theory behind the insertion sort is the creation of another array. When we look at the Bubble Sort, we see how the sort method takes the current array, compares adjacent elements, and makes swaps until everything is in order. This is essentially the same essence as insertion sort, but instead of sorting elements in the actual array, we create a new array (sometimes called temp since it is a temporary array), add elements to that array and sort them as we add them, and use the new array as the sorted array.

Let’s break down the insertion sort’s pseudocode.

* We start with an array and we assume that the entire array is unsorted.
* We create a new array called temp.
* We start with the first element in the array. We add this element to the temp array.
* Then, we look at the next element in the unsorted array. We add this element to the next empty spot in the temp array.
* We then compare this new element we just added to the temp array to the elements before it in the temp array. If the element is greater than the one before it, no additional moves are completed since that indicates it is already sorted. If it is less, then we swap the new element with the one before it until the new element is greater than the one before it.
* This same process happens for each element in the array until the array is fully sorted.

Let’s look at an illustration below:

![Insertion Sort Graphic 1](https://i.postimg.cc/tgw5hc1s/Prereq-5.png)

To demonstrate a way this sort algorithm looks in Java, an implementation insertionSort method is below:

##### Java
```Java
public static int[] insertionSort(int[] list)
{
   int n = list.length;
   int temp[] = new int[list.length];
   int index, j;
   temp[0] = list[0];

   for (j = 1; j < n; j++)
   {
       index = linearSearch(list[j],temp,j);
       insertItem(index,temp,list[j],j);
   }
   return temp;
}

public static void insertItem(int index, int[] temp, int searchNum, int size)
{
   for (int j = size; j > index; j--)
       temp[j] = temp[j-1];
   temp[index] = searchNum;
}

public static int linearSearch(int searchNum, int[] temp, int size)
{
   int index = 0;
   while (index < size && searchNum > temp[index])
       index++;
   return index;
}
```

Notice how the insertion sort relies on two helper methods: insertItem and linearSearch. The linearSearch method takes the new element to be added to the temporary array and finds the index of where that element should go. This method differs from what was said above about how the element is added directly to the end of the array and sorted from there, but rather places the element at the index it belongs in the temp array. Then, the insertItem method places the new element at the location it belongs in the temp array, making appropriate swaps of the elements before it to put it in the right position.

This implementation is different than what we discussed above in the order that it takes, but the steps are essentially the same.

### Asymptotic Notation and Time Complexity
With so many ways to perform searches and sorts, how do we decide which one to use? One factor that we take into account is how long the algorithm will take to run. Of course, algorithms will often have different runtimes based on the input. In order to generally measure the efficiency of different algorithms, we use something called time complexity, which we represent in **asymptotic notation**. Time complexity is an advanced computer science topic and is rooted in complex math, but at its core, the time complexity of an algorithm represents how many times statements will execute with respect to the size of the input, $n$. We most commonly use **big-O** notation to represent time complexity which is written as $O(f(n))$, where $f(n)$ is the function that represents how runtime changes in terms of $n$. For example, an algorithm that runs in $O(n)$ time will execute (on average) double the number of statements if we double the size of the input set. Time complexity gives us a guideline for how the runtimes of different algorithms grow as the size of the input, $n$, grows, though it is important to note that runtime and time complexity are not synonymous, and will not always vary proportionally. 


***Exercise***: Given the previous example, explain how the time complexity of an algorithm that runs in $O(1)$ time will (theoretically) change when we double the size of the input. What if we triple the size?
*Solution*: The runtime will (on average) not change
***Exercise***:: Suppose we have a three-part algorithm. The first part runs in $O(n)$ time, the second in $O(n)$ and the third in $O(n^2)$. What is the time complexity of the overall algorithm? 
*Solution*: $O(n^2+2n)$

When determining time complexity, we disregard very small inputs, and suppose that $n$ is of a “reasonably large” size such that the algorithm will run in a predictable way. This is at the core of asymptotic notation, where the function represented inside the parentheses (ex. $n^2$ for $O(n^2))$ represents the “asymptote” of the runtime as the input gets very very large. Because of this, we can often simplify these functions as their limits when n approaches infinity. We also typically ignore constants when writing these functions, meaning we typically write $O(n)$ or $O(n^2)$ rather than $O(2n)$ or $O(3/2 n^2)$. This is often because these constants don’t particularly matter as $n$, $2n$, $3n$, $4n$, etc. will always be less than $n^2$ as $n$ gets very large. Though we most often use asymptotic notation to represent time complexity, it can also be used to represent space complexity in a similar way.

***Exercise***: After learning these rules, simplify the time complexity you found in the previous exercise
*Solution*: O(n^2)

Generally, we use big-O notation to represent runtime, but there are a couple of variations and complexities in the notation we can use. There are three main types of asymptotic notation: **Ω notation, O notation and Ө-notation. Ω-notation** is the asymptotic lower bound, meaning it is the best-case runtime for a sufficiently large size $n$. **O notation** is the asymptotic upper bound, meaning it is the worst-case runtime for a sufficiently large size n. **Ө-notation** is both the upper and lower bound, meaning for a $Ө(f(n))$ algorithm, the runtime will be between different constants multiplied by $f(n)$ for all sufficiently large $n$. 

This is easier to visualize in the graphs below: 

![Asymptotic Notation and Time Complexity Graphic 1](https://i.postimg.cc/mZVgr1t5/Prereq-6.png)

(From Textbook)

***Exercise***: Graph the following functions, with respect to n:  nlog(n), 2^n, n^2, n, n!, log(n), 1
*Solution*:
![Asymptotic Notation and Time Complexity Graphic 2](https://i.postimg.cc/jSTTQsw7/Prereq-7.png)

***Exercise***: Using your answer to the previous exercise, rank these time complexities as n gets very large: $nlog(n)$, $2^n$, $n^2$, $n$, $n!$, $log(n)$, $1$
*Solution*: $1$, $log(n)$, $n$, $nlog(n)$, $n^2$, $2^n$, $n!$

#### Determining Time Complexity of Simple Algorithms
Before we hop straight into code, let us do a few examples of time complexity in real-life scenarios. 

Let’s say you’re looking for your backpack at school in a hallway of lockers, but you know your exact locker number, so you can walk straight to your locker and find your backpack after opening only one locker. 

***Exercise***: What time complexity would this represent?
*Solution*: $O(1)$

Let us now say that you’re looking for your seat in a classroom full of desks, but they’re not organized in any way so you must check each desk, one by one. 

***Exercise***: What time complexity would this represent?
*Solution*: $O(n)$

Now, you need to find your notebook in a pile of notebooks, but you have the help of your teacher, who knows which one is yours, but will only nod YES or shake their head NO. You begin by splitting the pile in two, and asking your teacher if your notebook is in the left pile. Depending on their answer, you put aside the pile your notebook was not in, and split the pile it was in into two again, and continue asking your teacher whether its in the left stack until you locate your notebook. 

***Exercise***: What time complexity would this represent?
*Solution*: $O(log(n))$

When we go from abstract examples to actual code, we can think of these examples to give us clues on the time complexity of an algorithm. For example, if a function takes an input, and delivers an output without every iterating through more than one member, the time complexity will often be $O(1)$. If there is one loop that iterates through each member of the group, the time complexity will often be $O(n)$. If the group is recursively split,  the time complexity will often be $O(log(n))$.

