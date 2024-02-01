**<h3>Question</h3>**

Write an efficient algorithm that searches for a value target in an m x n integer matrix matrix. This matrix has the following properties:

1. Integers in each row are sorted from left to right.
2. The first integer of each row is greater than the last integer of the previous row.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/1d9fd8ff-f1e0-4b10-86a7-41ecc89d4241)

**<h3>Constraints</h3>**

1. n == matrix.length
2. m == matrix[i].length
3. 1 <= m,n <= 100
4. -10000 <= matrix[i][j] <= 10000

**<h3>Approach</h3>**

1. wwe are using binary search approach to solve this question optimally.
2. As we can see the problem statement we are givena  sorted 2D array.
3. So first we apply binary search on the 1st row of the matrix and find the just smaller element than the target as the 2D array is sorted the target will be found in the column of that element only.
4. Then we apply binary search in that column to check for that element.

**<h3>Code</h3>**

```
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int n = matrix.size(), o = matrix[0].size(), s = 0, e = n-1, just = INT_MIN, index = n;
        while (s <= e) {
            int m = (s+e)/2;
            if (matrix[m][0] < target) {
                s = m+1;
                if (just < matrix[m][0]) {
                    just = matrix[m][0];
                    index = m;
                }
            }
            else if (matrix[m][0] > target) e = m-1;
            else if (matrix[m][0] == target) return true;
        }
        if (index == n) return false;
        s = 0, e = o-1; int i = index;
        while (s <= e) {
            int m = (s+e)/2;
            if (matrix[i][m] == target) return true;
            else if (matrix[i][m] > target) e = m-1;
            else s = m+1;
        }
        return false;
    }
};
```
