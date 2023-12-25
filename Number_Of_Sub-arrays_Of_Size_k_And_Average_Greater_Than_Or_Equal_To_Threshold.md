**<h3>Question</h3>**

Given an array of integers arr and two integers k and threshold, return the number of sub-arrays of size k and average greater than or equal to threshold.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/5e4c9fd4-455d-43d3-aa9a-002895374dea)

**<h3>Constraints</h3>**

1. 1 <= arr.length <= 10<sup>5</sup>
1. 1 <= arr[i] <= 10<sup>4</sup>
2. 1 <= k <= arr.length
3. 0 <= threshold <= 10<sup>4</sup>

**<h3>Approach</h3>**

1. Whenever there is a question relating to sub-arrays then the first approach that comes to mind is the sliding window approach.
2. So we will use that same approach in this question as well and first we will find out the sum of the first sub-array of size k.
3. Then we will keep on using the sliding window technique till the end of the array.
4. We will maintain a variable count that will be incremented whenever we find a sub-array that meets the condition.

**<h3>Code</h3>**

```
class Solution {
public:
    int numOfSubarrays(vector<int>& arr, int k, int threshold) {
        int count = 0;
        int sum = 0;
        int n = arr.size();
        for (int i = 0; i < k; i++) {
            sum += arr[i];
        }
        if (sum / k >= threshold) count++;
        for (int i = k; i < n; i++) {
            sum -= arr[i-k];
            sum+= arr[i];
            if (sum / k >= threshold) count++;
        }
        return count;
    }
};

```
