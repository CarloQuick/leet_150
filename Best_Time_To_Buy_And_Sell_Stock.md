// My code was running in n^2 time and exceeding time limit
// used LionKing's solution to model my own
// https://leetcode.com/problems/best-time-to-buy-and-sell-stock/solutions/39038/kadane-s-algorithm-since-no-one-has-mentioned-about-this-so-far-in-case-if-interviewer-twists-the-input/comments/36808
```
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int maxProfit = 0;
        int minProfit = INT_MAX;
        for(int i = 0; i < prices.size(); i++){
            minProfit = min(prices[i], minProfit);
            maxProfit = max(prices[i] - minProfit, maxProfit);
        }

        return maxProfit;
    }
};
```
