#include <bits/stdc++.h> 

void helper(string &s, unordered_set<string> &str_dict,vector<string> &ans, int n, int location,vector<string> &temp){
    if(location==n){

        string var = "";
        for(auto i: temp){
            var += i+" ";
        }
        ans.push_back(var);
        return ;

    }

    for(int i=location; i<n; i++)
    {
        string x = s.substr(location,i-location+1);
        if(str_dict.find(x) != str_dict.end()){
            temp.push_back(x);
            helper(s,str_dict,ans,n,i+1,temp);
            temp.pop_back();


        }
    }

}

vector<string> wordBreak(string &s, vector<string> &dictionary)
{
    // Write your code here
    unordered_set<string> str_dict(dictionary.begin(), dictionary.end());
    vector<string> ans;
    vector<string> temp;
    int n = s.length();

    helper(s,str_dict,ans, n, 0,temp);
    return ans;

}
