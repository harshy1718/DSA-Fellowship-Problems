**<h3>Question</h3>**

<h6>Given an integer array nums sorted in non-decreasing order, remove the duplicates  such that each unique element appears only once and return the new array.</h6>

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/00977e28-70cb-453e-87aa-631a25817ee4)


**<h3>Constraints</h3>**

1. 1 <= nums.length <= 3*10<sup>4</sup> 
1. -100 <= nums[i] <= 100
1. nums is sorted in non-decreasing order.

**<h3>Approach</h3>**

1. We initialize a variable count to 1. This variable will keep track of the count of unique elements in the modified nums array.
2. We iterate through the input vector nums starting from the second element (index 1) using a for loop.
3. Inside the loop, we compare the current element nums[i] with the previous unique element nums[count - 1]. If they are not equal, it means we have encountered a new unique element. In this case, we update the nums[count] position with the current element to keep it in place. We then increment k to indicate that we have found one more unique element.
4. After the loop completes, count contains the count of unique elements, and the first count elements of the nums vector contain the unique elements in the same order they appeared in the input.
5. Then we resize the nums array to count size and return the nums array

**<h3>Code</h3>**

```
class Solution {
public:
	vector<int> removeDuplicates(vector<int>& nums) {
		int count = 1;
        for (int i = 1; i < nums.size(); i++) {
            if (nums[i] != nums[i-1]) {
                nums[count] = nums[i];
                count++;
            }
        }
        nums.resize(count);
        >return nums;
	}
};
```
