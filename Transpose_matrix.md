**<h3>Question</h3>**

Given a 2D integer array matrix, return the transpose of matrix.

The transpose of a matrix is the matrix flipped over its main diagonal, switching the matrix's row and column indices.

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/daa3aaf8-5e3d-4cea-be53-a54c53723206)

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/8e6985fe-771a-41eb-a2d3-bc9d4832c6ef)

**<h3>Constraints</h3>**

1. n == matrix.length
2. m == matrix[i].length
3. 1 <= m,n <= 1000
4. 1 <= m*n <= 10<sup>5</sup>
5. -10<sup>9</sup> <= matrix[i][j] <= 10<sup>9</sup>

**<h3>Approach</h3>**

1. We just made a new 2D matrix by changing the rows and columns of the given matrix.
2. Then as in transpose we swapped the elements on the left side of the diagonal to the right side of the disgonal.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<vector<int>> transpose(vector<vector<int>>& matrix) {
        vector<vector<int>> v(matrix[0].size(), vector<int>(matrix.size()));
        for(int i=0;i<matrix.size();i++){
            for(int j=0;j<matrix[0].size();j++){
                v[j][i]=matrix[i][j];
            }
        }
        return v;
    }
};
```
