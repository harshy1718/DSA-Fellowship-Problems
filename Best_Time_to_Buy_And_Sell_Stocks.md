**<h3>Question</h3>**

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/befd6266-d853-4f8e-ac4e-12c985d4b4e0)

**<h3>Constraints</h3>**

1. 1 <= prices.length <= 10<sup>5</sup> 
1. 0> <= prices[i] <= 10<sup>4</sup>

**<h3>Approach</h3>**

1. We initialise 2 variables maxi = 0 and mini = pruces[0].
2. Now we traverse the prices array and see if prices[i] is smaller than mini. If yes then update mini = prices[i].
3. Else we have to update the maxi = maximum of prices[i]-mini or maxi.
4. At the end of the loop we have the max profit in maxi variable.

**<h3>Code</h3>**

```
class Solution {
public:
	int maxProfit(vector<int>& prices) {
		int mini = prices[0];
        int maxi = 0;
        for (int i = 0; i < prices.size(); i++) {
            if (prices[i] < mini) {mini = prices[i];}
            else maxi = max(prices[i]-mini,maxi);
        }
        return maxi;
	}
};
```
