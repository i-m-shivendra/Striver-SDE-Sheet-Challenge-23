#include<bits/stdc++.h>
using namespace std;

void topologicalSort(vector<int> adj[], int S, bool visited[], stack<int> &st) {
    visited[S] = true;
    for(int v : adj[S]) {
        if(!visited[v]) topologicalSort(adj,v,visited,st);
    }
    st.push(S);
}

void DFS(vector<int> adj[], int s, bool visited[], vector<int> &ans) {
    visited[s] = true;
    ans.push_back(s);
    for(int v : adj[s]) {
        if(!visited[v]) DFS(adj,v,visited,ans);
    }
}

vector<vector<int>> stronglyConnectedComponents(int n, vector<vector<int>> &edges)
{   
    vector<int>adj1[n],adj2[n];
    bool visited[n] = {0};
    stack<int> st;
    vector<vector<int>> res;
    
    for(auto i: edges) 
        adj1[i[0]].push_back(i[1]);
    
    for(int i = 0; i < n; i++)
        if(!visited[i]) topologicalSort(adj1, i, visited, st);

    for(auto i: edges) 
        adj2[i[1]].push_back(i[0]); 
    fill(visited, visited+n, 0);

    while(!st.empty()) {
        int u = st.top();
        st.pop();
        vector<int> ans;
        if(!visited[u]) {DFS(adj2,u,visited,ans); res.push_back(ans);}
    }
    return res;
}
