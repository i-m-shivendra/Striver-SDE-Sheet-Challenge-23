#include <bits/stdc++.h> 
using namespace std;
int atoi(string str) {
    // Write your code her
    int n =str.size();
    if(n==0) return 0;

    int i=0;
    while(i<n&& str[i]==' ') i++;

    str = str.substr(i);

    int sign = +1;
   int  ans =0;
    if (str[0]=='-') sign =-1;
   
    i = (str[0]=='+'|| str[0]=='-') ? 1:0;

      while(i<n){
        if (isdigit(str[i])) {
          ans = ans * 10 + str[i] - '0';
        }
        i++;
      }
    return (sign*ans);
}
