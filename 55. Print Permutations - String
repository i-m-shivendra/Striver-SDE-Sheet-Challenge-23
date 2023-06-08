#include <bits/stdc++.h> 

void helper(int ind, string &s, vector<string> &ans){
    if(ind >= s.size()){
        ans.push_back(s);
        return;
    }
    for(int i = ind; i < s.size(); i++){
        swap(s[ind], s[i]);
        helper(ind+1, s, ans);
        swap(s[ind], s[i]);
    }
}

vector<string> findPermutations(string &s) {
    int ind = 0;
    vector<string> ans;
    helper(ind, s, ans);
    return ans;
}
