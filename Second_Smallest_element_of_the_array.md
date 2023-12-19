**<h3>Question</h3>**

Given an array of integer nums . Find the second smallest element from an array.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/5bad0c8a-1c71-4570-b189-bd1ccaa88c33)

**<h3>Constraints</h3>**

1. 1 <= n <= 10<sup>5</sup> 
1. -10<sup>6</sup> <= nums[i] <= 10<sup>6</sup>

**<h3>Approach</h3>**

1. We initialise a variable mini1 with INT_MAX and another variable with nums[0].
2. Now we traverse the array from the second element and we check for 2 conditions.
3. If nums[i] is smaller than mini2 then we update mini2 with nums[i] and mini1 with mini2
4. Else we check if nums[i] lies between mini1 and mini2 then we update mini1 = nums[i].
5. In this way at the end of the loop we have mini2 as the smallest element and mini1 as the second smallest element

**<h3>Code</h3>**

```
class Solution {
public:
	int secondSmallest(vector<int>& nums) {
		int mini1 = INT_MAX;
		int mini2 = nums[0];
		for (int i = 1; i < nums.size(); i++) {
			if (nums[i] < mini2) {
				mini1 = mini2;
				mini2 = nums[i];
			}
			else if ((nums[i] < mini1 ) && (nums[i] > mini2)) {
				mini1 = nums[i];
			}
		}
		return mini1;
	}
};
```
