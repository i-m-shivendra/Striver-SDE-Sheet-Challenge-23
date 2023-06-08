#include<bits/stdc++.h>
void findMedian(int *arr, int n)
{
    priority_queue<int> mx;
    priority_queue<int, vector<int>, greater<int>> mn;
    
    for(int i=0; i<n; i++){
        if(mx.size() == 0) mx.push(arr[i]);
        else if(arr[i] > mx.top()) mn.push(arr[i]);
        else mx.push(arr[i]);
        
        if(mx.size() - mn.size() == 2)
            mn.push(mx.top()), mx.pop();
        else if(mn.size() - mx.size() == 1)
            mx.push(mn.top()), mn.pop();
        
        if(mx.size() == mn.size())
            cout << (mx.top() + mn.top())/2 << " ";
        else cout << mx.top() << " ";  
    }
}
