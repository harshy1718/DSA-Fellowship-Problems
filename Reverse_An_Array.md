**<h3>Question</h3>**

Given an array nums of n elements . Complete the given function and return the reversed array .

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/31736985-eddd-4c69-be9d-b8792a717474)


**<h3>Constraints</h3>**

1. 1 <= n <= 10<sup>5</sup> 
1. -1000 <= nums[i] <= 1000

**<h3>Approach</h3>**

1. We use 2 pointers for this question, one from the starting of the array and the other from the end
2. Then we run a loop with the condition while(start<= end) and keep swapping nums[start] and nums[end]
3. after every iteration we do start++ and end--

**<h3>Code</h3>**

```
class Solution {
   public:
   vector <int> reverseArray(vector <int> &arr) {
     int start = 0;
     int end = arr.size()-1;
     while (start <= end) {
       swap(arr[start],arr[end]);
       start++;
       end--;
     }
     return arr;
   }
};
```
