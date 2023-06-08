#include <bits/stdc++.h> 

class Node{

    public:

    Node* arr[26];

    bool flag;

    

};

Node* getNode(){

    Node* node = new Node();

    node->flag = false;

    for(int i=0;i<26;i++){

        node->arr[i]=NULL;

    }

    return node;

}

 

 

 

void insert(Node* root,string &word){

    Node* node = root;

    for(int i=0;i<word.size();i++){

        if(node->arr[word[i]-'a']==NULL){

            node->arr[word[i]-'a']=getNode();

        }

        node=node->arr[word[i]-'a'];

    }

    node->flag=true;

}

void check(Node* root, string &word, string &str){

    Node* node = root;

    for(int i=0;i<word.size();i++){

        node = node->arr[word[i]-'a'];

        if(node->flag==false){

            return;

        }

    }

    if (word.size() > str.size()) {

      str = word;

    }else if (word.size() == str.size() && word < str) {

      str = word;

    }

    return;

}

string completeString(int n, vector<string> &a){

    // Write your code here.

    Node *root = getNode();

    for(int i=0;i<a.size();i++){

       insert(root,a[i]);

    }

    

    string str = "";

 

    for(int i=0;i<a.size();i++){

        check(root,a[i],str);

    }

    if(str==""){

        return "None";

    }

    return str;

}
