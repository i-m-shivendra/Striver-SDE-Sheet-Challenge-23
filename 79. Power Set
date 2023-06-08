#include <bits/stdc++.h> 
void solve(vector<int>& v,int index,vector<int> subset,vector<vector<int>> &ans){
    if(index == v.size()){
        ans.push_back(subset);
        return;
    }
    // take 
    subset.push_back(v[index]);
    solve(v,index+1,subset,ans);
    // Not take
    subset.pop_back();
    solve(v,index+1,subset,ans);
}
vector<vector<int>> pwset(vector<int>v)
{
    vector<vector<int>> ans;
    int index =0;
    vector<int> subset;
    solve(v,index,subset,ans);
    return ans;
}
