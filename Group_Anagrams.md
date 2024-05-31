```
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        vector<vector<string>> res;
        unordered_map<string, vector<string>> map;
        unordered_map<string, vector<string>>::iterator it;

        for(int i = 0; i < strs.size(); i++){
            string temp = strs[i];
            sort(strs[i].begin(), strs[i].end());
            it = map.find(strs[i]);
            if(it == map.end()){
                vector<string> subres;
                subres.push_back(temp);
                map[strs[i]] = subres;
            }
            else{
                it->second.push_back(temp);
            }
        }
        for(it = map.begin(); it != map.end(); it++){
            res.push_back(it->second);
        }
        return res;   
    }
};
```
