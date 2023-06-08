#include <bits/stdc++.h> 
void minHeapify(int i,vector<int>&myheap){
    int lchild=2*i+1;
    int rchild=2*i+2;
    int smallest=i;
    if(myheap[lchild]<myheap[i] && lchild<myheap.size()){
        smallest=lchild;
    }
    if(myheap[rchild]<myheap[i] && myheap[rchild]<myheap[lchild] && rchild<myheap.size()){
        smallest=rchild;
    }
    if(smallest!=i){
        swap(myheap[smallest],myheap[i]);
        minHeapify(smallest,myheap);
    }
    return;
}
void insert(vector<int>&myheap,int x){
    myheap.push_back(x);
    int idx=myheap.size()-1;
    int par=(idx-1)/2;
    while(myheap[par]>myheap[idx]){
        minHeapify(par,myheap);
        idx=par;
        par=(par-1)/2;
    }
}
int removehead(vector<int>&myheap){
    int ans=myheap[0];
    swap(myheap[0],myheap[myheap.size()-1]);
    myheap.pop_back();
    minHeapify(0, myheap);
    return ans;
}
vector<int> minHeap(int n, vector<vector<int>>& q) {
    
    vector<int>myheap;
    vector<int>ans;
    for(int i=0;i<q.size();i++){
        if(q[i][0]==0){
            insert(myheap,q[i][1]);
        }
        else{
            ans.push_back(removehead(myheap));
        }
    }
    return ans;
}
