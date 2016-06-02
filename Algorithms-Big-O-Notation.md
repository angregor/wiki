# Big-O Notation

In mathematics, Big-O notation is a symbolism used to describe and compare the limiting behavior of a function. In short Big-O notation is used to describe the growth or decline of a function, usually with respect to another function. For example we say that x = O(x<sup>2</sup>) for all x > 1 or in other words, x<sup>2</sup> is an upper bound on x and therefore it grows faster. In general, the symbol of a claim like x = O(x<sup>2</sup>) for all x > *n* can be substituted with  x <= x<sup>2</sup>for all x > *n* where *n* is the minimum number that satisfies the claim, in this case 1.

Comparitively, in computer science we can use Big-O notation in order to describe the speed with which our algorithms will run. As a result of this analysis, we are able to compare the efficiency of our algorithms in terms of time complexity using Big-O notation. Specifically when using Big-O notation we are describing the efficiency of the algorithm with respect to an input: *n*, usually as *n* approaches infinity. When examining algorithms, we generally want a lower time complexity, and ideally a time complexity of O(1) which is constant time.

## Examples

As an example, we can examine the time complexity of the [bubble sort](https://github.com/FreeCodeCamp/wiki/blob/master/Algorithms-Bubble-Sort.md#algorithm-bubble-sort) algorithm.

#### Bubble Sort:

```c++
// Function to implement bubble sort
void bubble_sort(int array[], int n)
{
    // Here n is the number of elements in array
    int temp;

    for(int i = 0; i < n-1; i++)
    {
        // Last i elements are already in place
        for(int j = 0; j < n-i-1; j++)
        {
            if (array[j] > array[j+1])
            {
                // swap elements at index j and j+1
                temp = array[j];
                array[j] = array[j+1];
                array[j+1] = temp;
            }
        }
    }
}
```

Looking at this code, we can see that in the best case scenario where the array is already sorted, the program will only make *n* comparisons as no swaps will occur. Therefore we can say that the best case time complexity of bubble sort is O(*n*).

Examining the worst case scenario where the array is in reverse order, the first iteration will make *n* comparisons while the next will have to make *n* - 1 comparisons and so on until only 1 comparison must be made. The big-O notation for this case is therefore *n* * [(*n* - 1) / 2] = 0.5*n*<sup>2</sup> - 0.5*n* = O(*n*<sup>2</sup>) as the *n*<sup>2</sup> term dominates the function which allows us to ignore the other term in the function.


## Why?

Analyzing algorithms is an incredibly important aspect of any real world programming task as its important to pick the right algorithm for the job. It is important to make sure that you have the best efficiency that you can have in order to make sure your project will scale correctly. For more information on why Big-O notation and algorithm analysis is important visit this [hike](https://www.freecodecamp.com/videos/big-o-notation-what-it-is-and-why-you-should-care)!
