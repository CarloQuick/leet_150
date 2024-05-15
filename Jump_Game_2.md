Dynamic Approach using
https://medium.com/@mistysamia/45-jump-game-ii-leetcode-d8a06c49b09b
```
class Solution {
public:
    int jump(vector<int>& nums) {
        int n = nums.size();
        vector<int> dp(n, -1); // size n, but filled with -1s
        return minJumps(nums, 0, dp);
    }
    int minJumps(vector<int>& nums, int index, vector<int>& dp){
        int n = nums.size();
        // base case
        if(index == n-1) // reached the n-1 index
            return 0;
        // if there is  a minJump, return it
        if(dp[index] != -1)
            return dp[index];
        
        int minJumpsRequired = 100000;
        // Calculate the maximum jump that can be made from the current index (maxJump). 
        // This is the minimum of the value at the current index and the distance to the end of the array from the current index.
        int maxJumps = min(nums[index], n - 1 - index);

        // from the current index, starting with the next one j = 1, visit the elements up to and equal maxJump
        for(int j = 1; j <= maxJumps; j++){
            // next index is the current index plus j for the recursive function
            int nextIndex = index + j;
            // recursive functionality to get the min jumps from each
            int jumpsToNext = minJumps(nums, nextIndex, dp);
            // when it's finally returned, we add one and take the minumum
            minJumpsRequired = min(minJumpsRequired, jumpsToNext + 1);
        } 
        // when all calculated we updated the dynamic programming array
        dp[index] = minJumpsRequired;
        return minJumpsRequired;
    }
};
```

Alternatire Approach
https://leetcode.com/problems/jump-game-ii/solutions/18014/concise-o-n-one-loop-java-solution-based-on-greedy
```
class Solution {
public:
    int jump(vector<int>& nums) {
        int jumps = 0;
        int currEnd = 0;
        int currFarthest = 0;

        for(int i = 0; i < nums.size() - 1; i++){
            currFarthest = max(currFarthest, i + nums[i]);

            if(i == currEnd){
                currEnd = currFarthest;
                jumps++;
            }
        }
        return jumps;
    }

};
```
