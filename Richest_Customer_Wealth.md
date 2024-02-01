**<h3>Question</h3>**

You are given an m x n integer grid accounts where accounts[i][j] is the amount of money the i​​​​​​​​​​​th​​​​ customer has in the j​​​​​​​​​​​th​​​​ bank. Return the wealth that the richest customer has.

A customer's wealth is the amount of money they have in all their bank accounts. The richest customer is the customer that has the maximum wealth.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/42f215a3-e627-4ac1-ac04-1c0beb1aeebd)

**<h3>Constraints</h3>**

1. n == matrix.length
2. m == matrix[i].length
3. 1 <= m,n <= 50
4. 1 <= accounts[i][j] <= 100

**<h3>Approach</h3>**

1. The most optimal approach is the brute force approach in which we traverse the entire array and find out the sum of each column and them compare it again and again to get the largest column sum
2. And that is our answer.

**<h3>Code</h3>**

```
class Solution {
public:
    int maximumWealth(vector<vector<int>>& accounts) {
        int sol = 0, count = 0, n = accounts.size(), m = accounts[0].size();
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                sol += accounts[i][j];
            }
            count = max(sol,count);
            sol = 0;
        }
        return count;
    }
};
```
