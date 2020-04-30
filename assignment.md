# Activity: Selection Sort

*Lecture 6a, Slide 33*

## Objective

Understand behavior of selection sort

## Instructions

Trace a walkthrough of selection sort with this array

 | `0` | `1` | `2` | `3` | `4` | `5` | `6` | `7` | `8` | `9` | Notes |
 |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---|
 |**4**|**7**| 11  |  4  |  9  |  5  | 11  |  7  |  3  |  5  |`[0]` is provisional minimum.  Compare to `[1]`.|
 |**4**|  7 |**11**|  4  |  9  |  5  | 11  |  7  |  3  |  5  | Then to `[2]` |
 |**4**|  7  | 11  |**4**|  9  |  5  | 11  |  7  |  3  |  5  | And so on... |
 |**4**|  7  | 11  |  4  |**9**|  5  | 11  |  7  |  3  |  5  | Looking for an element smaller... |
 |**4**|  7  | 11  |  4  |  9  |**5**| 11  |  7  |  3  |  5  | |
 |**4**|  7  | 11  |  4  |  9  |  5 |**11**|  7  |  3  |  5  | |
 |**4**|  7  | 11  |  4  |  9  |  5  | 11  |**7**|  3  |  5  | |
 |**4**|  7  | 11  |  4  |  9  |  5  | 11  |  7  |**3**|  5  | Found one! This is the new minimum |
 |  4  |  7  | 11  |  4  |  9  |  5  | 11  |  7  |**3**|**5**| We've reached the end of the array|
 |  4  |  7  | 11  |  4  |  9  |  5  | 11  |  7  |**3**|  5  | ...so `[8]` must be the minimum |
 |4&rarr;| 7 | 11  |  4  |  9  |  5  | 11  |  7  |&larr;**3**| 5 | Swap it with `[0]` |
 | *3* |  7  | 11  |  4  |  9  |  5  | 11  |  7  |  4  |  5  | Partition the array, and *ignore* the first element |
 | *3* |**7**|**11**| 4  |  9  |  5  | 11  |  7  |  4  |  5  |Step through as before... |
 | *3* |**7**| 11  |**4**|  9  |  5  | 11  |  7  |  4  |  5  |Found an element smaller than 7 |
 | *3* |  7  | 11  |**4**|**9**|  5  | 11  |  7  |  4  |  5  |This becomes our new minimum |
 | *3* |  7  | 11  |**4**|  9  |**5**| 11  |  7  |  4  |  5  | |
 | *3* |  7  | 11  |**4**|  9  |  5 |**11**|  7  |  4  |  5  | |
 | *3* |  7  | 11  |**4**|  9  |  5  | 11  |**7**|  4  |  5  | |
 | *3* |  7  | 11  |**4**|  9  |  5  | 11  |  7  |**4**|  5  | |
 | *3* |  7  | 11  |**4**|  9  |  5  | 11  |  7  |  4  |**5**|We've reached the end of the array.  |
 | *3* |  7  | 11  |**4**|  9  |  5  | 11  |  7  |  4  |  5  | So our provisional minimum really is the minimum. |
 | *3* |7&rarr;| 11  |&larr;**4**|9|5| 11  |  7  |  4  |  5  | Swap with first element not partitioned. |
 | *3* | *4* | 11  |  7  |  9  |  5  | 11  |  7  |  4  |  5  | Repeat. (I'll skip ahead to the swaps) |
 | *3* | *4* | 11&rarr;|  7  |  9  |  5  | 11  |  7  |&larr;**4**|  5  | Swap |
 | *3* | *4* | *4* | 7&rarr; |  9  |&larr;**5**| 11  |  7  | 11  |  5  | Swap |
 | *3* | *4* | *4* | *5* | 9&rarr; |  7  | 11  |  7  | 11  | &larr;5 |  Swap |
 | *3* | *4* | *4* | *5* | *5* |**7**| 11  |  7  | 11  | 9 | No swap, the leftmost unpartitioned element is already smallest. |
 | *3* | *4* | *4* | *5* | *5* | *7* | 11&rarr; |&larr;7 | 11  | 9 | Swap  |
 | *3* | *4* | *4* | *5* | *5* | *7* | *7* | 11&rarr; | 11  | &larr;9 | Swap |
 | *3* | *4* | *4* | *5* | *5* | *7* | *7* | *9* | 11  | 11 | Swap  |
 | *3* | *4* | *4* | *5* | *5* | *7* | *7* | *9* |**11**| 11 | Again, no swap. |
 | *3* | *4* | *4* | *5* | *5* | *7* | *7* | *9* | *11* | 11 | Only one element left, nothing to compare.  Array is sorted! |

# Activity: Merge Sort

*Lecture 6b, Slide 26*

## Objective

Understand behavior of MERGE SORT

## Instructions

Trace a walkthrough of MERGE SORT with this array

|`0`|`1`|`2`|`3`|`4`|`5`|`6`|
|---|---|---|---|---|---|---|
| 4 | 7 |11 | 4 | 9 | 5 |11 |
| 4 | 7 | 4 |11 | 5 | 9 |11 |
| 4 | 4 | 7 |11 | 5 | 9 |11 |
| 4 | 4 | 5 | 7 | 9 |11 |11 |

I didn't write notes for this walkthrough, because I don't think that best captures how Merge Sort really works.  Merge Sort is recursion at its finest.  It relies on two ideas:
* Sorting an array of only 1 or 2 elements is trivial
  * If it has only 1 element, or if the second element is greater than the first, return it as is.
  * If the second element is less than the first, swap them and return.
* If you have two arrays *that you know are already sorted*, they can be easily combined to form a larger array that is also sorted.
  * First, make a new empty array
  * Compare the first element of one given array to the first element of the other
  * Push whichever element is smaller into the new array *and remove it from its original array* (or you could implement a partition counter for each array to track how many elements have already been assessed)
  * Repeat this process until one of the arrays is empty.
  * When this happens, append the other array to the new array in its entirety.
  * This new array now contains the elements from both arrays and, provided they were sorted beforehand, is also sorted.
  
Using these two methods, you can sort an array of any size, even if it's not sorted beforehand.

Merge Sort is given an array and defined as follows:
* If the array is 1 or 2 elements in length, sort it according to the first method listed above.
* If it is 3 or more elements, split it in half, *Merge Sort each half*, and then combine the two halves using the second method.

This is all you need to tell the computer.  It will then keep breaking down the array until it's in a bunch of tiny pieces that can all be sorted trivially, and then *magically reassemble them* so that the final outcome is sorted.

### Anecdote:

These algorithms are much better than xkcd's [ineffective sorts](https://xkcd.com/1185/).