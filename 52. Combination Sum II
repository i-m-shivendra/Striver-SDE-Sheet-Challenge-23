#include<bits/stdc++.h>
void combinationSumHelper(int ind, vector<vector<int>> &ans, vector<int> &v, vector<int> &arr, int n, int target){
    if(target == 0){
        ans.push_back(v);
        return;
    }
    
    for(int i = ind; i < n; i++){
        if(i > ind && arr[i] == arr[i-1])continue;
        if(arr[i] > target)break;
        v.push_back(arr[i]);
        combinationSumHelper(i+1, ans, v, arr, n, target - arr[i]);
        v.pop_back();
    }
}

vector<vector<int>> combinationSum2(vector<int> &arr, int n, int target)
{
    sort(arr.begin(), arr.end());
    int ind = 0;
    vector<vector<int>> ans;
    vector<int> v;
    combinationSumHelper(ind, ans, v, arr, n, target);
    return ans;
}
