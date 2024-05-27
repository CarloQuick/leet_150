// https://leetcode.com/problems/isomorphic-strings/submissions/1268971666?envType=study-plan-v2&envId=top-interview-150
// credit to himanshu_mehra_ 
```
class Solution {
public:
    bool isIsomorphic(string s, string t) {
        unordered_map<char, char> sMap; 
        unordered_map<char, char> tMap;    
        for(int i = 0; i < s.length(); i++){
            if(sMap[s[i]] && sMap[s[i]] != t[i]) // if mapping there and if the mapping doesnt equal current t[i]
                return false;
            if(tMap[t[i]] && tMap[t[i]] != s[i]) // if mapping there and if the mapping doesnt equal current t[i]
                return false;
            sMap[s[i]] = t[i];
            tMap[t[i]] = s[i];
        }
    return true;
    }
};
```
