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

## Stack Questions
1. Given file system in <kbd>\t</kbd> delimited string, find longest absolute path of a file. [link](https://leetcode.com/problems/longest-absolute-file-path/#/description)  
**Trick**: Append to the stack while entering a directory and pop while leaving.

## Logic
1. Replace adjacent digits such that result is smallest possible. [link](https://discuss.leetcode.com/topic/55360/replace-two-adjacent-digits-with-larger-one-to-find-the-smallest-number-that-can-be-obtained), [solution](https://github.com/x-surgical-x/leetcode/blob/master/replace-adjacent-numbers.py)  
**Trick**: Find pattern (high, mid, low) => (high, low). Otherwise replace least significant digit.
