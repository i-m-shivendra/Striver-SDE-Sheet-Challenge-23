#include<bits/stdc++.h>

int helper(int e,int f,vector<vector<int>>&dp) {
    if(f<=1 || e==1) {
        return dp[e][f]=f;
    }
    if(dp[e][f]!=-1) {
        return dp[e][f];
    }
    int ans=1e6,start=1,end=f;
    while(start<=end) {
        int mid=start+(end-start)/2;
        if(dp[e-1][mid-1]==-1) {
            dp[e-1][mid-1]=helper(e-1,mid-1,dp);
        }
        int BREAK=dp[e-1][mid-1];
        if(dp[e][f-mid]==-1) {
            dp[e][f-mid]=helper(e,f-mid,dp);
        }
        int SURVIVE=dp[e][f-mid];
        ans=min(ans,1+max(BREAK,SURVIVE));
        if(BREAK<SURVIVE) {
            start=mid+1;
        }
        else {
            end=mid-1;
        }
    }
    return dp[e][f]=ans;
}

int cutLogs(int k, int n) {
    vector<vector<int>>dp(k+1,vector<int>(n+1,-1));
    return helper(k,n,dp);
}
