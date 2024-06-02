```
// https://www.enjoyalgorithms.com/blog/longest-consecutive-sequence
class Solution {
public:
    int longestConsecutive(vector<int>& nums) {
      unordered_map<int, int> map;
      unordered_map<int, int>::iterator it;

      for(int i = 0; i < nums.size(); i++){
        map[nums[i]] = i;
      }

      int longestLength = 0;
      int currLength = 0;

      for(int i = 0; i < nums.size(); i++){
        if(map.find(nums[i]-1) == map.end()){ //first number
            currLength = 1;
            int currElem = nums[i];
            while(map.find(currElem+1) != map.end()){// next in sequence
              currLength++;
              currElem++;
            }
            longestLength = max(currLength, longestLength);
        }
      }
       return longestLength; 
    }
};
```
