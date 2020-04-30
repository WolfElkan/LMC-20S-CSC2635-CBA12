# Activity: Selection Sort

*Lecture 6a, Slide 33*

## Objective

Understand behavior of selection sort

## Instructions

Trace a walkthrough of selection sort with this array

 | `0` | `1` | `2` | `3` | `4` | `5` | `6` | `7` | `8` | `9` | Notes |
 |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---|
 |**4**|**7**| 11  |  4  |  9  |  5  | 11  |  7  |  3  |  5  |The `[0]` is provisional minimum.  Compare to `[1]`.|
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
 | *3* |  7  | 11  |  4  |  9  |  5  | 11  |  7  |  4  |  5  | Partition the array, and ignore the first element |
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