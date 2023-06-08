string longestPalinSubstring(string str)

{

    // Write your code here.

    int n=str.length();

    int l,r;

    int start=0;

    int end=1;

 

    for(int i=1;i<n;i++)

    {

        //even substring

        l=i-1;

        r=i;

 

        while(l>=0 && r<n && str[l]==str[r])

        {

            if(r-l+1 > end)

            {

                start=l;

                end=r-l+1;

                

            }

            l--;

            r++;

        }

 

        // odd substring

        l=i-1;

        r=i+1;

 

        while(l>=0 && r<n && str[l]==str[r])

        {

            if(r-l+1 > end)

            {

                start=l;

                end=r-l+1;

                

            }

            l--;

            r++;

        }

    }

    return str.substr(start,end);

}
