Questions asked in google for Interviews, from [Interview Bit](https://www.interviewbit.com/google-interview-questions/)
### [Gas Station Problem](https://www.interviewbit.com/problems/gas-station/)
N gas stations in circle. gas[i], cost[i]. Find min index from where travel complete circuit.
### [Majority element in an array](https://www.interviewbit.com/problems/majority-element/)
An integer appears more than floor(n/2) times. Find that integer
### [Distinct Subsequences](https://www.interviewbit.com/problems/distinct-subsequences/)
Two string sequences, find number of unique Subsequences of **first string** identical to **second string**.
### [Regular expression](https://www.interviewbit.com/problems/regular-expression-ii/)
Given a string and a regular expression, find if string can be represented with regular expression.  
Take care of `.*` which will match anything.
### [Interleaving Strings](https://www.interviewbit.com/problems/interleaving-strings/)
Given three strings, return true if third string can be formed by interleaving first two strings.
### [Word-Squared?](https://discuss.leetcode.com/topic/60617/find-if-a-word-square-they-read-the-same-horizontally-and-vertically-example-ball-area-lead-lady-return-true-if-a-given-sequence-is-a-word-square)  
eg: True for "BALL AREA LEAD LADY"  
Just check if the matrix is symmetric or not:
```
for i in range(length):
    for j in range(i):
        if word[i][j] != word[j][i]:
            print('False')
            quit()
print('True')
```
