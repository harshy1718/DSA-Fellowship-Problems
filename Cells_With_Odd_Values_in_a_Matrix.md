**<h3>Question</h3>**

There is an m x n matrix that is initialized to all 0's. There is also a 2D array indices where each indices[i] = [ri, ci] represents a 0-indexed location to perform some increment operations on the matrix.

For each location indices[i], do both of the following:

1. Increment all the cells on row ri.
2. Increment all the cells on column ci.

Given m, n, and indices, return the number of odd-valued cells in the matrix after applying the increment to all locations in indices.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/df38bd80-5fd9-4664-ade7-2f458c0bb8b7)

**<h3>Constraints</h3>**

1. 1 <= m,n <= 50
2. 1 <= indices.length <= 100
3. 0 <= r<sub>i</sub> <= m
4. 0 <= c<sub>i</sub> <= n


**<h3>Code</h3>**

```
class Solution {
public:
    int oddCells(int m, int n, vector<vector<int>>& indices) {
        vector<bool> rows(m,false), cols (n,false);
        for (auto it : indices) {
            rows[it[0]] = rows[it[0]] ^ true;
            cols[it[1]] = cols[it[1]] ^  true;
        }
        int r = 0, c = 0;
        for (int i = 0; i < m; i++) {
            if (rows[i]) r++;
        }
        for (int i = 0; i < n; i++) {
            if (cols[i]) c++;
        }
        return r*(n-c) + c*(m-r);
    }
};
```
