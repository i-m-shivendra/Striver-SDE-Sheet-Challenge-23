#include <bits/stdc++.h> 

void dfsTopoSort(vector<vector<int>> &adj, vector<bool> &visited, stack<int> &stk, int node){
    // Base Case
    if(visited[node]) return;
    visited[node] = true;
    for(int v : adj[node]){
        if(!visited[v]){
            dfsTopoSort(adj, visited, stk, v);
        }
    }
    stk.push(node);
}


vector<int> topologicalSort(vector<vector<int>> &edges, int v, int e)  {
    // Using DFS + STACK + VISITED ARRAY.
    // Time Complexity: O(V + E)
    // Space Complexity: O(V + E)
    // Build the adj. list
    vector<vector<int>> adj(v);
    for(auto edge : edges){
        adj[edge[0]].push_back(edge[1]);
    }
    // Visited array
    vector<bool> visited(v, false);
    // Stack
    stack<int> stk;
    // DFS 
    for(int i = 0; i < v; i++){
        if(!visited[i]){
            dfsTopoSort(adj, visited, stk, i);
        }
    }
    // store the final answer
    vector<int> ans;
    while(!stk.empty()){
        ans.push_back(stk.top());
        stk.pop();
    }

    return ans;
}
