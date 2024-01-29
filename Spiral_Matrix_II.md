**<h3>Question</h3>**

Given a positive integer n, generate an n x n matrix filled with elements from 1 to n<sup>2</sup> in spiral order.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/46ff049d-110a-464a-98c5-0b3537f42fc8)

**<h3>Constraints</h3>**

1. 1 <= n <= 20

**<h3>Approach</h3>**

1. we are using nested loops to solve this question and for that we have created a 2d matrix of size n x n.
2. so first we initialize count to 1 and it will be used to overwrite the values of the ans matrix.
3. so we start by running a for loop.
4. then we run 4 for loops in that loop, where each loop is for each direction.
5. so the first loop is for left to right, then from top to bottom excluding the top and bottom elements.
6. then the third loop is for left to right with extra condition for count <= n*n so that we do not overdo the count value.
7. then the 4th loop for bottom to top excluding the top and bottom elements.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<vector<int>> generateMatrix(int n) {
        vector<vector<int>> ans(n,vector<int>(n));
        int count = 1;
        for (int i = 0; i< n; i++) {
            for (int j = i; j < n-i; j++) {
                ans[i][j] = count++;
            }
            for (int j = i+1; j < n-i-1; j++) {
                ans[j][n-1-i] = count++;
            }
            for (int j = n-i-1; count <= n*n && j >= i; j--) {
                ans[n-i-1][j] = count++;
            }
            for (int j = n-i-2; j > i; j--) {
                ans[j][i] = count++;
            }
        }
        return ans;
    }
};
```
