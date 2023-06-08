#include <bits/stdc++.h>

class Node{
    public:
    int data;
    Node*child[2];
    Node(int data){
        this->data = data;
        for(int i = 0;i<2;i++){
            child[i] = NULL;
        }
    }
};

class Trie{
    public:
    Node *root;
    Trie(){
        root = new Node('\0');
    }
    void insert(int num){  
        Node *prev = root;
        for(int i = 31;i>=0;i--){ // inserting a 32 bit integer starting from the 
            int bit = (num>>i)&1;
            Node*child;
            if(prev->child[bit]== NULL){
                child = new Node(bit);
                prev->child[bit] = child; // pushes the bit at 0 if bit is 0, 1 if the bit is 1
            }
            else{
                child = prev->child[bit];
            }
            prev = child;
        }
    }

    int find_max(int num){
        int val = 0;
        Node *prev = root;
        for(int i = 31;i>=0;i--){
            int bit = (num>>i)&1;
            Node *child;
            if (bit & 1){// means the bit is 1
                if(prev->child[0]){ // check for 0 bit
                    child = prev->child[0];// put child on the 0th bit to maximize answer     
                    val = val |(1<<i); 
                }
                else{
                    child = prev->child[1];
                }
            } 
            else{ // bit is 0
                if(prev->child[1]){
                    child = prev->child[1];
                    val = val |(1<<i);
                }
                else{
                    child = prev->child[0];
                }
            }
            prev = child;
        }
        return val;
    }
};



vector<int> maxXorQueries(vector<int> &arr, vector<vector<int>> &queries){
	Trie t;
	sort(arr.begin(),arr.end());
	vector<pair<int,pair<int,int>>> offlineQuery;
	int q = queries.size();
	for(int i = 0;i<q;i++){
		offlineQuery.push_back({queries[i][1],{queries[i][0],i}}); // we want to later sort it according to Ai hence we stored Ai at first
	}
	sort(offlineQuery.begin(),offlineQuery.end());
	vector<int>ans(q,0); // we will later push it according to query index 

	int idx = 0;
	for(int i = 0;i<offlineQuery.size();i++){
		int ai = offlineQuery[i].first;
		int xi = offlineQuery[i].second.first;
		int qindex = offlineQuery[i].second.second;
		while(idx<arr.size() && arr[idx]<=ai){
			t.insert(arr[idx]);
			idx++; // we dont initialize to again to 0 by putting idx in the for loop as the array is sorted hence all the previous elements 
			 	   // would already be inserted.
		}
        if(idx == 0){
            ans[qindex] = -1;
        }
        else{
            ans[qindex] = t.find_max(xi); // find max for xi.
        }
	}
	return ans;
}
