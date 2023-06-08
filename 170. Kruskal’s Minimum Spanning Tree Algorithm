#include <bits/stdc++.h> 
class Disjoint {
    vector<int> parent, size;
    public: 
        Disjoint(int n) {
            parent.resize(n+1);
            size.resize(n+1,1);
            for(int i=1;i<=n;i++)
                parent[i] = i;
        }
        int find(int node) {
            if(node == parent[node])
                return node;
            return parent[node] = find(parent[node]);
        }
        void unionBySize(int u, int v) {
            int pu = find(u), pv = find(v);
            if(size[pu] < size[pv]) {
                parent[pu] = pv;
                size[pv] += size[pv];
            }
            else {
                parent[pv] = pu;
                size[pu] += size[pv];
            }
        }
};
int kruskalMST(int n, int m, vector<vector<int>> &graph) {
	vector<pair<int,pair<int,int>>>edges;
    for(auto i: graph) {
        int u = i[0], v = i[1], wt = i[2];
        edges.push_back({wt,{u,v}});
        edges.push_back({wt,{v,u}});
    }
    sort(edges.begin(), edges.end());
    Disjoint d(n);
    int sum = 0;
    
    for(auto i: edges) {
        int wt = i.first, u = i.second.first, v = i.second.second;
        if(d.find(u) != d.find(v)) {
            sum += wt;
            d.unionBySize(u,v);
        }
    }
    
    return sum;
}
