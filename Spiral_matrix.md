**<h3>Question</h3>**

Given an m x n matrix, return all elements of the matrix in spiral order.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/205872e2-981f-4c18-8a82-113ab1b0087b)

**<h3>Constraints</h3>**

1. n == matrix.length
2. m == matrix[i].length
3. 1 <= m,n <= 10
4. -100 <= matrix[i][j] <= 100

**<h3>Approach</h3>**

1. we are using nested loops to solve this question and for that we have created a matrix ans to store the spiral order.
2. so first we initialize count to 0 and it will be used to stop the loops once we have done the entire 2D array in spiral order.
3. so we start by running a for loop.
4. then we run 4 for loops in that loop, where each loop is for each direction.
5. so the first loop is for left to right, then from top to bottom excluding the top and bottom elements.
6. then the third loop is for left to right.
7. then the 4th loop for bottom to top excluding the top and bottom elements.
8. In each loop we have used count < sol so that we do not repeat the elements int he final matrix.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        vector<int>ans;
        int n = matrix.size(), m = matrix[0].size();
        int count = 0, sol = m*n;
        for (int i = 0; i< n; i++) {
            for (int j = i; count < sol && j < m-i; j++) {
                ans.push_back(matrix[i][j]);
                count++;
            }
            for (int j = i+1; count < sol && j < n-i-1; j++) {
                ans.push_back(matrix[j][m-1-i]);
                count++;
            }
            for (int j = m-i-1; count < sol && j >= i; j--) {
                ans.push_back(matrix[n-i-1][j]);
                count++;
            }
            for (int j = n-i-2; count < sol && j > i; j--) {
                ans.push_back(matrix[j][i]);
                count++;
            }
        }
        return ans;
    }
};
```
