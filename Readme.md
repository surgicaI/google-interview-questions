## Array Questions
1. Among **all pairs** find sum of bits that are different. [link](http://www.geeksforgeeks.org/sum-of-bit-differences-among-all-pairs/)  
**Trick**: For each bit scan all the elements in array. **O(n.64)**

2. Find total number of continuous subarrays whose sum equals to k. [geeksforgeeks](http://practice.geeksforgeeks.org/problems/subarray-with-given-sum/0) [leetcode](https://leetcode.com/problems/subarray-sum-equals-k/#/description)  
**Trick**: If integers are **non-negetive** then **windowing solution**.  
**Otherwise** create sums array and use hashmap.  
**[Variant](https://leetcode.com/problems/continuous-subarray-sum/#/description)-sum is multiple of k** create sums array and use hashmap to find if the same remainder occurred previously.

3. Maximum subarray problem [leetcode](https://leetcode.com/problems/maximum-subarray/#/description)  
**Trick**: Start scanning for left, keep adding numbers in your result and maintain current sum. As soon the current_sum becomes negative => result.empty() and repeat above algorithm from next index.  

4. Rearrange string, same characters appear atleast d distance apart. [geeksforgeeks](http://www.geeksforgeeks.org/rearrange-a-string-so-that-all-same-characters-become-at-least-d-distance-away/)  
**Trick**: Sort by frequency`(use heap, have to remain sorted at all times)`. Maintain last `d` characters in a set. Always print most frequent character which is not in the set.

5. Merge Interval. Given a sorted list of non-overlapping intervals, merge a new interval in that list. [interview-bit](https://www.interviewbit.com/problems/merge-intervals/)  
**Trick**: Write a function to check overlap between two intervals.  
Then scan the intervals and fit the new interval at its location if it overlaps with some intervals.  
*edge cases:* The new interval may not overlap with any of the intervals in the list and can be at the start or at the end.

6. Given an array of integers, find max product of 3 elements.  [interview-bit](https://www.interviewbit.com/problems/highest-product/)   
**Trick** Sort the list.
cases:  
(i) No positive number and no zero present in list.
(ii) No positive number but zero is in list.
(iii) Two positives and one negative.
(iv) Two or more negatives and one or more positives.

7. Given a sorted array, remove duplicates in place.   [interview-bit](https://www.interviewbit.com/problems/remove-duplicates-from-sorted-array/)  
**Trick** Maintain two pointers.

## Linked List:
1. Sort Linked list in O(nlogn) time and constant space. [interview-bit](https://www.interviewbit.com/problems/sort-list/)  
**Trick** Use merge sort and recursion. Find mid point, sort two lists and merge them.(Technically recursion is not constant space solution)

## Stack Questions
1. Given file system in <kbd>\t</kbd> delimited string, find longest absolute path of a file. [link](https://leetcode.com/problems/longest-absolute-file-path/#/description)  
**Trick**: Append to the stack while entering a directory and pop while leaving.

2. Decode String. s = "3[a]2[bc]", return "aaabcbc". [link](https://leetcode.com/problems/decode-string/#/description)  
**Trick**: Use recursion, or can be done iteratively using stack also.

## Logic
1. Replace adjacent digits such that result is smallest possible. [link](https://discuss.leetcode.com/topic/55360/replace-two-adjacent-digits-with-larger-one-to-find-the-smallest-number-that-can-be-obtained) [solution](https://github.com/x-surgical-x/leetcode/blob/master/replace-adjacent-numbers.py)  
**Trick**: Find pattern (high, mid, low) => (high, low). Otherwise replace least significant digit.

2. Remove duplicates from the sting such that remaining string has smallest lexicographical ordering. [leetcode](https://leetcode.com/problems/remove-duplicate-letters/description/)  
**Trick**: Maintain locations of all chars in an array. Try to print 'a' by testing if all characters on left of 'a' also have a duplicate on right side of a. Then do this for remaining characters.

3. Kth row of pascal triangle. [Interview-bit](https://www.interviewbit.com/problems/kth-row-of-pascals-triangle/)  
**Trick**: **Kth** row will have **k+1** elements if **K** starts from 0. `nC(r+1) = nCr * (n-r) / (r+1)`

## Dynamic Programming
1. Minimum number of swaps required for arranging pairs adjacent to each other.[geeksforgeeks](http://www.geeksforgeeks.org/minimum-number-of-swaps-required-for-arranging-pairs-adjacent-to-each-other/)  
**Tricks**: Start from left. Two possible options:  
a. Either swap 2nd element with the pair of 1st  
b. Swap 1st element with the pair of 2nd element.

2. Given string and a dict of words, return **true** if string can be broken into words in dict. **Word Break Problem** [interview-bit](https://www.interviewbit.com/problems/word-break/)  
**Trick-1** Start from reverse to prevent maximum recursion depth issue.
**Trick-2** Store lengths of words in dict and run a loop over these lengths.
```
def solve(self, start_index):
    if start_index in self.my_map:
        return self.my_map[start_index]
    for length in self.lengths:
        if start_index + length > self.length:
            continue
        word = self.string[start_index:start_index+length]
        if start_index + length == self.length and word in self.dict:
            self.my_map[start_index] = 1
            return 1
        elif start_index + length < self.length:
            if word in self.dict and self.solve(start_index+length):
                self.my_map[start_index] = 1
                return 1
    self.my_map[start_index] = 0
    return 0
```

## Greedy algorithms
1. Given a jumps array, reach last point in minimum jumps.  [interview-bit](https://www.interviewbit.com/problems/min-jumps-array/)  
Can be solved using DP also.  
**Trick** Stand at index `start_index = 0`. Keep a variable `max_reachable_index`. Scan from `start_index` to `max_reachable_index` and now stand at index for which `max_reachable_index` is maximum.
