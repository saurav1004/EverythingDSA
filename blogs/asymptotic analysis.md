# **Asymptotic Analysis and Analysis of Algorithms: A Guide for Engineers**

As engineers, we are constantly faced with the challenge of making our code run faster. Whether it's optimizing a sorting algorithm or reducing the number of iterations in a loop, we need to have a good understanding of how our code will perform as the input size increases. This is where asymptotic analysis and the analysis of algorithms come in.

## **Asymptotic Analysis**

Asymptotic analysis is a way to describe the performance of an algorithm as the input size increases. We use `big O notation` to describe the upper bound of an algorithm's running time. For example, if an algorithm takes $`5n^2 + 3n + 2`$ steps to run for an input of size n, we say that the algorithm's time complexity is $O(n^2)$.

Big O notation is useful because it describes the behavior of an algorithm as n gets very large, which is important when working with large inputs. However, it's important to note that big O notation only gives an `[upper bound` on an algorithm's running time](https://3xplorations.cc/Asymptotic-Analysis-A-Guide-for-Engineers-884129b196aa4cffa254a227119b2eae), and it doesn't take into account the constant factors.

Asymptotic notation was first introduced by **[Paul Bachmann](https://en.wikipedia.org/wiki/Paul_Gustav_Heinrich_Bachmann)** in **1894**, who used it to describe the growth of functions in number theory. The notation was later popularized by [Edsger Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) in the 1960s, who used it to analyze the efficiency of algorithms.

There are several other notations that are used in asymptotic analysis such as

- `Big Omega (Ω) notation`: describes the lower bound of an algorithm's running time.
- `Big Theta (Θ) notation`: describes the exact running time of an algorithm.

## **Example of Asymptotic Analysis**

Let's take a look at an example of asymptotic analysis from a software engineer's point of view.

```python
def my_algorithm(n):
    result = 0
    for i in range(n):
        for j in range(n):
            result += i * j
    return result
```

This algorithm has a nested loop, with the outer loop running n times and the inner loop also running n times. The running time of the algorithm is therefore $O(n^2)$.

There are three common asymptotic notations: $O(n), O(n^2),$ and $O(log n)$.

### $**O(n)**$

$O(n)$ is a notation for describing an algorithm whose running time increases linearly with the size of the input. Mathematically, this can be represented as:

**`T(n) = O(f(n))`** where **`T(n)`** is the running time of the algorithm and **`f(n)`** is a function that describes the upper bound of the running time.

A simple example of an O(n) algorithm is linear search, which has a running time of O(n) because it iterates through an array of size n and takes a constant amount of time for each iteration.

```python
def linear_search(arr, x):
    for i in range(len(arr)):
        if arr[i] == x:
            return i
    return -1
```

### $**O(n^2)**$

$O(n^2)$ is a notation for describing an algorithm whose running time increases quadratically with the size of the input. Mathematically, this can be represented as:

**`T(n) = O(n^2)`** where **`T(n)`** is the running time of the algorithm.

A simple example of an $O(n^2)$ algorithm is bubble sort, which has a running time of $O(n^2)$ because it iterates through an array of size n twice and takes a constant amount of time for each iteration.

```python
def bubble_sort(arr):
    for i in range(len(arr)):
        for j in range(0, len(arr)-i-1):
            if arr[j] > arr[j+1] :
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr
```

### $**O(log n)**$

$O(log n)$ is a notation for describing an algorithm whose running time increases logarithmically with the size of the input. Mathematically, this can be represented as:

**`T(n) = O(log n)`** where **`T(n)`** is the running time of the algorithm.

A simple example of an $O(log n)$ algorithm is binary search, which has a running time of $O(log n)$ because it repeatedly divides the input by 2, and the number of iterations is equal to the number of times the input can be divided by 2.

```python
def binary_search(arr, x):
    low = 0
    high = len(arr) - 1
    mid = 0
    while low <= high:
        mid = (high + low) // 2
        if arr[mid] < x:
            low = mid + 1
        elif arr[mid] > x:
            high = mid - 1
        else:
            return mid
    return -1
```

It's worth noting that these notations provide an `upper bound` on the running time of an algorithm and do not take into account constant factors or lower-order terms. In practice, the actual running time of an algorithm may be affected by factors such as the specific implementation and the hardware it's running on. However, asymptotic notation provides a useful tool for comparing the relative efficiency of different algorithms and making general statements about their performance.

It's also important to note that these notations are not only limited to time complexity but also apply to space complexity, which is the amount of memory used by an algorithm as a function of the size of the input.

In conclusion, asymptotic notation is a powerful tool for analyzing the efficiency of algorithms. $O(n)$, $O(n^2)$, and $O(log n)$ are common notations used to describe the time complexity of algorithms, with $O(n)$ being the most efficient, $O(n^2)$ being less efficient, and $O(log n)$ being the least efficient.

As a software engineer, you should always be mindful of the time and space complexity of your algorithms, and strive to use the most efficient algorithms possible to improve the performance of your software.

And remember, as computer scientist Donald Knuth once said, **

💡 *Premature optimization is the root of all evil.*

So, always keep in mind the trade-offs between algorithm efficiency and code readability.

## **Conclusion**

Asymptotic analysis and the analysis of algorithms are essential tools for engineers who want to optimize their code and make it run faster. By understanding the time and space complexity of an algorithm, we can make informed decisions about which algorithm to use for a given task.

And remember, when in doubt, always use quicksort! 😆

<aside>
💡 Upper bound and lower bound are terms used in the analysis of algorithms to describe the maximum and minimum amount of resources (such as time or space) that an algorithm can use, respectively.

Upper bound, also known as worst-case complexity, is the maximum amount of resources that an algorithm can use for any input of a given size. It is represented using the "big O" notation $(O(f(n)))$, where $f(n)$ represents the upper bound function. For example, the upper bound for a linear search algorithm is $O(n)$, as the algorithm can take up to n steps to find the desired element in the worst-case scenario.

On the other hand, lower bound, also known as best-case complexity, is the minimum amount of resources that an algorithm can use for any input of a given size. It is represented using the "big omega" notation $(Ω(f(n)))$, where $f(n)$ represents the lower bound function. For example, the lower bound for a binary search algorithm is $Ω(log n)$, as the algorithm can find the desired element in logarithmic time in the best-case scenario.

It's worth noting that in some cases, an algorithm may have both a tight upper bound and a tight lower bound, meaning that the upper and lower bounds are both tight, and the actual time complexity of the algorithm is within a constant factor of the upper and lower bounds. This is represented using the "big theta" notation $(Θ(f(n)))$. For example, the time complexity of the merge sort algorithm is $Θ(n log n)$, which means that the actual time complexity is within a constant factor of $n log n$

</aside>