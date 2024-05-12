// credit to chipbk10
// https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/solutions/208241/explanation-for-the-dummy-like-me

```
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int profit = 0;
        int buy = 0;
        int sell = 0;
        int n = prices.size() - 1;
        int i = 0;

        while(i < n){
            while( i< n && prices[i+1] <= prices[i]){
                i++;
            }
            buy = prices[i];
            while(i< n && prices[i+1] > prices[i]){
                i++;
            }
            sell = prices[i];

            profit += sell - buy;
        } 

        return profit;
    }
};
```
