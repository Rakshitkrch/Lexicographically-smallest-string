# Lexicographically-smallest-string#
//{ Driver Code Starts
// Initial Template for C++
#include <bits/stdc++.h>
using namespace std;

// } Driver Code Ends
// User function Template for C++
class Solution {
  public:
    string lexicographicallySmallest(string S, int k) {
        int n=S.size();
        if(!(n&(n-1))){
            k=k/2;
        }
        else{
            k=k*2;
        }
        if(k>=n){
            return "-1";
        }
        stack<char> st;
        for(int i=0;i<n;i++){
            char ch=S[i];
            
            while( k>0 && st.size()>0 && st.top()>ch){
                k--;
                st.pop();
            }
            st.push(ch);
            
        }
        while(k>0 && st.size()>0){
            st.pop();
            k--;
        }
        string ans="";
        while(st.size()>0){
            ans+=s.top();
            st.pop();
        }
        reverse(ans.begin(),ans.end());
        return ans;
    }
};

//{ Driver Code Starts.
int main() {
    int t;
    cin >> t;
    while (t--) {
        string S;
        int k;
        cin >> S >> k;
        Solution ob;
        cout << ob.lexicographicallySmallest(S, k) << endl;
    }
    return 0;
}

// } Driver Code Ends
