// for understanding h-value formula
// https://en.wikipedia.org/wiki/H-index
// sorting in decreasing order
// https://www.geeksforgeeks.org/sorting-a-vector-in-c/
```
class Solution {
public:
    int hIndex(vector<int>& citations) {
        // sort in decreasing order
        sort(citations.begin(), citations.end(), greater<int>()); 
        // return the last index that the value is >= to index
        for(int i = citations.size() - 1; i >= 0; i--){
            if(citations[i] >= i+1)
                return i+1;
        }
        return 0;
    }
};
```
