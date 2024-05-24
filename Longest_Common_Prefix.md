```
// original submission
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        if(strs.size() == 1){
            return strs[0];
        }
        string res = strs[0];
        for(int i = 1; i < strs.size(); i++){ 
            string temp = "";
            for(int j = 0; j < min(strs[i].length(), res.length()); j++){
                if(strs.at(i)[j] == res[j]){
                    temp += res[j];
                }
                else
                    break;
            }
            res = temp;
        }
        return res;     
    }
};
```

```
// credit to abdullayev_akbar
// https://leetcode.com/problems/longest-common-prefix/solutions/3273176/python3-c-java-19-ms-beats-99-91
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        string res = "";

        sort(strs.begin(), strs.end()); // sorts them into alphabetical order
        string first = strs[0];
        string last = strs[strs.size() - 1];
        for(int i = 0; i < min(first.size(), last.size()); i++){ // then the first and last show be compared for longest prefix
            if(first[i] != last[i])
                return res;
            
            res += first[i];
        }  
        return res;
    }
    
};
```
