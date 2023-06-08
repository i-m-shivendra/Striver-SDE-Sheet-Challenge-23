#include <bits/stdc++.h>

int binSearch(vector<int> &arr, int target, int low, int high, int flag)

{

    int l=low, h=high, mid, occ=-1;

    while(h>=l)

    {

        mid = (l+h)/2;

        if(arr[mid]==target)

        {

            occ = mid;

            if(flag==1) //right

            {

                l = mid+1;

                h = high;

            }

            else

            {

                h = mid-1;

                l = low;

            }

        }

        else if (arr[mid]>target)

            h = mid-1;

        else

            l = mid+1;

    }

    return occ;

}

vector<vector<int>> pairSum(vector<int> &arr, int s)

{

   sort(arr.begin(), arr.end());

   vector<vector<int>> ans;

   int n = arr.size();

   for(int i=0; i<n-1; i++)

   {

       int elem = arr[i], complement = s-elem;

       int right = binSearch(arr, complement, i+1, n-1, 1);

       int left = binSearch(arr, complement, i+1, n-1, 0);

       while(right!=-1 && left<=right)

       {

         ans.push_back(vector<int>{elem, complement});

         left++;

       }

   }

   return ans;

}
