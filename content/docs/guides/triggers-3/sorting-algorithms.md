---
draft: true
authors:
  - v1ewsh0t
title: Sorting Algorithms
seo:
    title: Sorting Algorithms for Geometry Dash
    description: Learn how sorting algorithms work and how they can organize data in advanced Geometry Dash trigger systems.
    canonical: ""
    noindex: false
weight: 9110
date: 2026-07-21T00:00:00.000Z
contributors:
  - v1ewsh0t
  - chuckolate
description: Sorting numbers is one of the most common operations in computing, and are the basis for a wide range of applications and complex algorithms. This guide will cover various sorting systems and their implementations.
tags:
  - Grade 3
  - Applied Math & Algorithms
math: true
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

- Uses and implementations of various sorting algorthms such as **Bubble Sort, Selection Sort, Merge Sort, Counting Sort, and Radix Sort.**

{{< /callout >}}

---

# 1: Introduction

### What is a sorting algorithm?

A sorting algorithm is a **function** that takes in a **list/array** and **sorts** the items inside numerically from least to greatest/greatest to least. 

Sorting algorithms are incredibly useful when dealing with **large amounts of data** that have a certain priority to the items inside. For example, in 3D engines, triangles are drawn from **farthest to closest** from the camera, or viceversa. If the triangles were left unsorted, triangles farther away can render on top of triangles closer to the camera, which would mess up the final image. To combat this, engines will **sort the triangles based off of their Z position**, sorting from least to greatest. Other uses include **pathfinding/AI**, where nodes need to be sorted by their **priority** in what's commonly called an **"open list" or "frontier"** to determine where to move next.

Sorting algorithms are also used in many applications that deal with parsing through and retrieving information from large datasets.

# 2: Sorting Algorithms

{{< callout context="caution" title="Caution:" icon="outline/info-circle" >}}

  This guide uses **Python** for its code. I highly suggest learning the [syntax](https://docs.python.org/3/library/index.html) before continuing this guide if you don't already know.

{{< /callout >}}

## Algorithm 1: Bubble Sort

Out of the 5 algorithms listed in this guide, this is the **easiest one conceptually and to implement**. It is commonly used for educational purposes due to its high learnability. It is also used for small datasets (1-20), as the performance increase from faster algorithms are negligible at these scales.

Bubble Sort works by repeatedly looking from left to right a disorded array, and **swapping adjacent elements if they are in the wrong order**. The algorithm makes multiple passes through the array while ignoring sorted values, that way at each pass the array gets increasingly ordered.

In fact, if the sort works in ascended order, the first full pass will place the largest number of the array to the furthest right, so we don't have to move it again. That way, for each pass the algorithm can work on disorded subarrays that decrease in size up until the whole array is fully ordered.

{{< gif src="https://miro.medium.com/v2/resize:fit:4800/format:webp/1*GUkhhrPDfgdvvwVFo-il1g.gif" >}}

Bubble Sort is useful for when the **data set is minimal** as larger arrays **significantly increase computational time.**

The time complexity is listed below:

* Best: $O(n)$.
* Average: $O(n^2)$.
* Worst: $O(n^2)$.

### Implementation

The following implementation uses a `swapped` boolean flag to control a `while` loop, making so the algorithm continues iterating only as long as elements remain out of order. At the start of each pass, swapped is reset to `False` on the assumption that the array might be sorted.

```py
def Bubble_Sort(Array):
    swapped = True  # Initializes swap variable

    while swapped == True:
        swapped = False  # Sets loop up to end if there's no swap

        for i, value in enumerate(Array):
            # Checks to see if both index > 0 and current value is less than last value
            if i > 0 and value < Array[i-1]:
                minvalue = value        # Saves the current value for swapping
                Array[i] = Array[i-1]   # Swaps the current value with the last value
                Array[i-1] = minvalue   # Sets the last value to the saved current value
                swapped = True          # Continues loop

    return Array
```

## Algorithm 2: Selection Sort

Selection Sort is a **comparison based algorithm**, the second easiest in this guide. Commonly used for **small data sets** and in situations where memory is limited due to the fact that it’s an **in-place sorting algorithm**.

Selection Sort works by starting with a pointer at the first element of the array, finding the **smallest element in the array, swapping it with the pointer, and then moving the pointer to the next element in the array.** This repeats until the full array has been sorted.

{{< gif src="https://www.sahinarslan.tech/b8b466d2eb284a87c82fd49a2b033dfe/javascript-selection-sort-visualization.gif" >}}

Like Bubble Sort, Selection Sort is useful for small data sets as computational time significantly increases as the array increases.

The time complexity is listed below:

* Best: $O(n^2)$.
* Average: $O(n^2)$.
* Worst: $O(n^2)$.

### Implementation

```py
def Selection_Sort(Array):
    for current_index in range(len(Array)):  # Current index goes through length of array
        min_index = 0  # Minimum undex
        min_value = float('inf')  # Minimum value, uses infinity so the first value is min

        # Iterates through to the array to find the minimum value
        for i, value in enumerate(Array):
            if i > current_index - 1 and value < min_value:
                min_value = value
                min_index = i

        # Swaps the current index value and the minimum index value
        current_value = Array[current_index]
        Array[current_index] = min_value
        Array[min_index] = current_value

    return Array
```

## Algorithm 3: Merge Sort

Merge Sort is a very popular sorting algorithm due to its efficiency and stability. Used for large datasets and when memory is not an issue.

Merge Sort works by **splitting** the array into **smaller arrays**, dividing the arrays in half until it can no longer be divided. It then **sorts each subarray** in pairs using the Merge Sort algorithm and **merges** the subarrays, repeating the process until the array is fully sorted. There are two implementations of the Merge Sort algorithm, the **Top Down** approach and the **Bottom Up** approach, the Bottom Up approach being the one we are implementing here.

#### Bottom-Up Approach

We begin with our array of values. `[0,8,6,4,9,3,4,2]` We are going to imagine that each individual item in this array is its **own subarray** `[[0],[8],[6],[4],[9],[3],[4],[2]]` We are now going to take each adjacent pair of subarrays and sort them, **merging** the subarrays one layer.  `[[0,8],[4,6],[3,9],[2,4]]`

{{< img src="https://lh3.googleusercontent.com/d/1jJ1Glpwv4OerTidS0z98OITy1ldGaD6B" >}}

Now that we have these new arrays, we are going to sort the adjacent list again, **comparing** the first item in the first array with each item in the second array, moving the smaller value into another array:

{{< gif src="https://lh3.googleusercontent.com/d/1131wcbecWFfHDAUoT_aIdeDidGQpKf5S" >}}

Now we **repeat** the process 1 more time, **merging** `[0,4,6,8]` and `[2,3,4,9]` together:

{{< gif src="https://lh3.googleusercontent.com/d/1019fJGYoV2LMFegQu1CHzXZgQYVKNTvQ" >}}

{{< callout context="note" title="Remember:" icon="outline/info-circle" >}}

Merge sort **never rearranges elements** inside a subarray, it only **merges already-sorted subarrays.**

{{< /callout >}}

Because of its **efficiency**, merge sort is a **very popular algorithm**, often used for large data sets.

The time complexity is listed below:

* Overall: $O(n \log n)$.

### Implementation

```py
def MS_SortSubArray(LeftArray,RightArray):
    SubArray = []  # Final Sorted SubArray
    LAI = 0  # Left Array Index
    RAI = 0  # Right Array Index

    '''Continuously goes through both Left and Right Arrays, checking for min values
    and appending to SubArray'''

    while LAI < len(LeftArray) and RAI < len(RightArray):
        if LeftArray[LAI] < RightArray[RAI]:
            SubArray.append(LeftArray[LAI])
            LAI += 1
        else:
            SubArray.append(RightArray[RAI])
            RAI += 1

    # Takes remaining values and adds to SubArray
    if LAI == len(LeftArray):
        SubArray += RightArray[RAI:]
    else:
        SubArray += LeftArray[LAI:]
    return SubArray


def Merge_Sort(Array):
    SAS = 2  # Sub Array Size

    while SAS < 2 * len(Array):
        for SAI in range(0, len(Array), SAS):  # Sub Array Index

            # Sets up both Left and Right Arrays
            LeftArray = Array[SAI : SAI + (SAS//2)]
            RightArray = Array[(SAI + SAS//2) : SAI + SAS]

            Array[SAI : SAI + len(LeftArray) + len(RightArray)] = \
            MS_SortSubArray(LeftArray, RightArray)  # Sorts Individual Sub arrays

        SAS *= 2  # Increases Sub Aray Index by a multiple of 2

    return(Array)
```

## Algorithm 4: Counting Sort

**Counting Sort** is a non-comparison based sorting algorithm, great for arrays with small integer values. It works by taking count of every **distinct** number in the array, computing their **starting positions** via **cumulative sums**, and mapping the original array to the new array using said new positions.

Because of its **simplicity, efficiency, and stability**, it is commonly used in conjunction with other sorting algorithms such as **Radix Sort**, which will be discused in the next section.

The time complexity is listed below:

* Overall: $O(n + k)$.
* $k$: range of key.

### Implementation

```py
def Counting_Sort(Array):
    # Initialization of MaxNum, CountArray and FinalArray arrays
    MaxNum = max(Array) + 1
    CountArray = [0] * MaxNum
    FinalArray = [0] * (len(Array))

    # Counts all instances of each number in Array
    for i in Array:
        CountArray[i] += 1

    # Stores cumulative sum of elements in CountArray
    for i in range(1, len(CountArray)):
        CountArray[i] += CountArray[i-1]

    '''Uses the Array Value as an Index to Count Array,
    Using Count array's resulting value as an index for Final Array,
    subtracting 1 to align with Array'''

    for i in range(len(Array)-1, -1, -1):
        FinalArray[CountArray[Array[i]]-1] = Array[i]
        CountArray[Array[i]] -= 1

    return FinalArray
```

## Algorithm 5: Radix Sort

**Radix Sort** is a non-comparative, stable sorting algorithm that sorts values by their **Significant Digits**, going from the *Most Significant Digit* to the *Least Significant Digit*. To sort the individual digits, Radix Sort relies on a secondary, *Stable sorting algorthim*, commonly using **Counting Sort** as said algorithm.

**Radix Sort** is most commonly used for sorting **large integer-based datasets** including string based sets.

The time complexity is listed below:

* Overall: $O(d\cdot(n + b))$.
* $d$ is the # of digits in the largest element and $b$ is the base # system.

### Implementation

```py
'''Similar as normal Counting Sort, but sorts using the integer
in the specific decimal place indicated via the exp variable'''

def RS_CountingSort(Array, num, exp):
    FinalArray = [0] * num
    CountArray = [0] * 10

    for i in range(num):
        CountArray[(Array[i] // exp) % 10] += 1

    for i in range (1, 10):
        CountArray[i] += CountArray[i - 1]

    for i in range(num-1, -1, -1):
        FinalArray[CountArray[(Array[i] // exp) % 10] - 1] = Array[i]
        CountArray[(Array[i] // exp) % 10] -= 1

    return FinalArray


def Radix_Sort(Array):
    num = len(Array)
    MaxNum = max(Array) # Gets maximum number in Array
    exp = 1 # Initializes exponent

    while MaxNum / exp > 0:
        Array = RS_CountingSort(Array, num, exp)
        exp *= 10 # Increases exp by a factor of 10

    return Array
```

# Sources

- [Sorting GIFs](<https://visualgo.net/en/sorting>)