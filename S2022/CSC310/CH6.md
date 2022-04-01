# Transform and Conquer

There are two steps to the transformation stage:
1. Problem's instance is modified to be solved more easily
2. Problem is solved by the algorithm

There are 3 major variations to this idea:
- **Instance Simplificaton:** Transformation to a simpler/more convenient instance of the problem
- **Representation Change:** Transformation to a different representation of the same instance
- **Problem Reduction:** Transformation to an instance of a different problem, for which there is already an algorithm available

<br>

## Overview
- **6.1**: Presorting
- **6.2:** Gaussian Elimination
- **6.3:** Instance Simplification
- **6.4:** Heaps/Heapsort
- **6.5:** Horner's Rule
- **Review**

---

## 6.1: Presorting
**Many questions about a list are easier to answer if it's sorted.**

*Note: time efficiency of algorithms involving sorting may depend on the time efficiency of the algorithm used to sort it. For simplicity, assume that the lists in this section are implemented as arrays, since some sorting algorithms are easier to implement on arrays compared to lists.*

**Quadratic in worst & average cases:**
- Selection sort
- Bubble sort
- Insertion sort
  
**Advanced:**
- Mergesort: always *theta*(*n* log *n*)
- Quicksort: *theta*(*n* log *n*) in avg case, quadratic in worst case

**(1.3)** No general comparison-based sorting algorithm can have a better efficiency than *n* log *n* in the worst case, and the same result holds for the average-case efficiency.

<br>

### Example 1
*Checking element uniqueness in an array*

**(2.3 ex. 2)** This algorithm resembles the brute-force algorithm defined here. It compares pairs of array elements until either two equal elements are found or no more pairs are left. The worst case efficiency is *theta*(*n*<sup>2</sup>).

Another way is to sort first, then only check consecutive elements. *If there are equal elements, they will be next to each other.*

**PresortElementUniqueness**`(A[0..n-1])`
- Solves the element uniqueness problem by sorting the aray first
- Input: an array `A[0..n-1]` of orderable elements
- Output: returns `true` if `A` has no equal elements, `false` otherwise sort the array `A`

```py
for i = 0 to n - 2 do
    if A[i] = A[i+1] return false
return true
```

Running time = sum of time spent sorting + time spent checking consecutive elements
- Sorting requires at >= *n* log *n* comparisons
- Checking requires 