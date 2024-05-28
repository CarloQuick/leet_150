```
class Solution {
public:
    bool isAnagram(string s, string t) {
        //make sMap with count of each char
        // same for t
        unordered_map<char, int> sMap;
        unordered_map<char, int> tMap;

        if(s.length() != t.length())
            return false;

        for(int i = 0; i < s.length(); i++){
            auto it = sMap.find(s[i]);
            if(it == sMap.end()){ // not there
                sMap[s[i]] = 1;
            }
            else{
                it->second = it->second + 1;
            }
        }
        for(int i = 0; i < t.length(); i++){
            auto it = tMap.find(t[i]);
            if(it == tMap.end()){
                tMap[t[i]] = 1;
            }
            else{
                it->second = it->second + 1;
            }
        }
        for(auto it = sMap.begin(); it != sMap.end(); it++){
            auto it2 = tMap.find(it->first);
            if(it2 == tMap.end() || it2->second != it->second)
                return false;
        }
        return true;

    }
};
```
