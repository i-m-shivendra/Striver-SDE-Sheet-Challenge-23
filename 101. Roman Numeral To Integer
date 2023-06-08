#include <bits/stdc++.h> 
int numb(char st){
    switch(st){
        case 'I':
          return 1;
        case 'V':
          return 5;
        case 'X':
          return 10;
        case 'L':
          return 50;
        case 'C':
          return 100;
        case 'D':
          return 500;
        case 'M':
          return 1000;           
    }
}
int romanToInt(string s) {
    char s1,s2;
    int sum=0;
    int len= s.length();
    for(int i=0;i<len;i++){
        s1=s[i];
        s2=s[i+1];
        if(i+1==len){
            sum+=numb(s1);
            break;
        }
        if(numb(s1)>=numb(s2)){
            sum+=numb(s1);
        }
        else{
            sum-=numb(s1);
          
        }
    }
    return sum;
}
