Questions asked in google for Interviews, from [Interview Bit](https://www.interviewbit.com/google-interview-questions/)
### [Gas Station Problem](https://www.interviewbit.com/problems/gas-station/)
N gas stations in circle. gas[i], cost[i]. Find min index from where travel complete circuit.
### [Majority element in an array](https://www.interviewbit.com/problems/majority-element/)
An integer appears more than floor(n/2) times. Find that integer
### [Highest product](https://www.interviewbit.com/problems/highest-product/)
Array of integers, find max product of 3 elements.
### [Distinct Subsequences](https://www.interviewbit.com/problems/distinct-subsequences/)
Two string sequences, find number of unique Subsequences of **first string** identical to **second string**.
### [Minimum jumps array](https://www.interviewbit.com/problems/min-jumps-array/)
Given a jumps array, reach last point in minimum jumps. DP solution is straight forward. Greedy solution:
stand at index `start_index = 0`. Keep a variable `max_reachable_index`. Scan from `start_index` to `max_reachable_index` and now stand at index for which `max_reachable_index` is maximum.
