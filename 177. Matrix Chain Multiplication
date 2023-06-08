#include <bits/stdc++.h> 

int helper(vector<int>&arr,int start,int end,vector<vector<int>>&dp) {
    if(start==end-1) {
        return dp[start][end]=0;
    }
    if(dp[start][end]!=-1) {
        return dp[start][end];
    }
    int ans=INT_MAX;
    for(int i=start+1;i<end;i++) {
        if(dp[start][i]==-1) {
            dp[start][i]=helper(arr,start,i,dp);
        }
        if(dp[i][end]==-1) {
            dp[i][end]=helper(arr,i,end,dp);
        }
        ans=min(ans,dp[start][i]+dp[i][end]+(arr[start]*arr[i]*arr[end]));
    }
    return dp[start][end]=ans;
}

int matrixMultiplication(vector<int> &arr, int N) {
    vector<vector<int>>dp(N+1,vector<int>(N+1,-1));
    return helper(arr,0,N-1,dp);
}
