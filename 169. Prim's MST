#include <bits/stdc++.h> 
vector<pair<pair<int, int>, int>> calculatePrimsMST(int n, int m, vector<pair<pair<int, int>, int>> &g)
{
    unordered_map<int, list<pair<int,int>>> adj;
    for(int i=0; i<g.size(); i++){

        int u = g[i].first.first;
        int v = g[i].first.second;
        int w = g[i].second;

        adj[u].push_back(make_pair(v,w));
        adj[v].push_back(make_pair(u,w));
    }

    //make key, mst, parent;
    vector<int> key(n+1);
    vector<bool> mst(n+1);
    vector<int> parent(n+1);

    for(int i=0; i<=n; i++){
        key[i] = INT_MAX;
        mst[i] = false;
        parent[i] = -1;
    }

    //let's play algo

    key[1] = 0;
    parent[1] = -1;

    for(int e=0; e<n-1; e++){

        int mini = INT_MAX;
        int curr;
        for(int i=1; i<=n; i++){
            if(mst[i] == false && key[i] < mini){

                mini = key[i];
                curr = i;
            }
        }

        //update mst
        mst[curr] = true;

        for(auto i: adj[curr]){
            int v = i.first;
            int w = i.second;
            if(mst[v] == false && w < key[v]){
                parent[v] = curr;
                key[v] = w;
            }
        }

    }

    vector<pair<pair<int, int>, int>> result;
    for(int i=2; i<=n; i++){
        result.push_back({{parent[i], i},key[i]});
    }
    return result;

}
