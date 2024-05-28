```
class Solution {
public:
    bool wordPattern(string pattern, string s) {
        stringstream ss(s);
        string token;
        vector<string> sV;
        unordered_map <char, string> pMap;
        unordered_map <string, char> sMap;

        while(getline(ss, token, ' ')){
            sV.push_back(token);
        }
        if(sV.size() != pattern.length())
            return false;
        for(int i = 0; i < pattern.size(); i++){
            //if(sMap[s[i]] && sMap[s[i]] != t[i])
            if(pMap.find(pattern[i]) != pMap.end() && pMap[pattern[i]] != sV[i])
                return false;
            else if(sMap[sV[i]] && sMap[sV[i]] != pattern[i])
                return false;
            pMap[pattern[i]] = sV[i];
            sMap[sV[i]] = pattern[i];
        }
        return true;
    }
};
```
