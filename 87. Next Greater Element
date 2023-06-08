#include <bits/stdc++.h>

#include<stack>

vector<int> nextGreater(vector<int> &arr, int n) {

// Write your code here

stack<int>s;

 

s.push(-1);

for(int i=n-1; i>=0; i--){

int curr=arr[i];

while(!s.empty() && s.top()<=curr){

s.pop();

}

if(s.empty()){

arr[i]=-1;

}

else{

arr[i]=s.top();

}

s.push(curr);

}

return arr;

}

