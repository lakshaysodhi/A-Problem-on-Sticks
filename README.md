# A-Problem-on-Sticks
#include <bits/stdc++.h>
using namespace std;

int main() {

    int t;
    cin>>t;
    while(t--){
        int n;
        int cuttedportion=0;
        int count=0;
        cin>>n;
        vector<int> height(n);
        for(int i=0;i<n;i++){
            cin>>height[i];
        }
        sort(height.begin(),height.end());
        reverse(height.begin(),height.end());
        for(int i=1;i<n;i++){
            if(height[i-1]>height[i]){
                    count++;
                cuttedportion+=(i*(height[i-1]-height[i]));
                height[i-1]=height[i];
            }
        }
        if(height[n-1]!=0){
        cuttedportion+=n*height[n-1];
        count++;
        }
        cout<<count<<endl;
    }

}

