```
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n = nums.size();
        // // O(n) but with extra space
        // // https://www.geeksforgeeks.org/a-product-array-puzzle/
        // vector<int> prefix(n,1);
        // vector<int> suffix(n,1);
        // vector<int> answer(n,1);

        // //get all values to the left
        // for(int i = 1; i < n; i++){
        //     prefix[i] = prefix[i-1] * nums[i-1];
        // }
        // //get all values to the right
        // for(int i = n-2; i >= 0; i--){
        //     suffix[i] = suffix[i+1] * nums[i+1];
        // }
        // for(int i = 0; i < n; i++){
        //     answer[i] = suffix[i] * prefix[i];
        // }
        
        // Final solution with help from dead_lock

        //https://leetcode.com/problems/product-of-array-except-self/submissions/1262654812?envType=study-plan-v2&envId=top-interview-150
        // modify answers array with prefix first
        // curr holds current total
        vector<int> answer(n,1);
        int curr = 1;
        for(int i = 0; i < n; i++){
            answer[i] *= curr;
            curr *=nums[i];
        }
        curr = 1;
         for(int i = n-1; i >= 0; i--){
            answer[i] *= curr;
            curr *=nums[i];
        }

        
        return answer;
        
        
    }
};
```
