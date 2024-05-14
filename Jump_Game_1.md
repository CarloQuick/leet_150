// Used https://medium.com/geekculture/the-jump-game-software-engineering-problem-5f7b58d9e1ec
// to understand to complete the problem
```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        if(nums.size() ==  1){
            return true;
        }
        int j = nums.size() - 1;

        for(int i = nums.size() - 2; i >= 0; i--){
            if(i + nums[i] >= j){
                j = i;
            }
        }
        return (j == 0 ? true : false);
    }
};
```
