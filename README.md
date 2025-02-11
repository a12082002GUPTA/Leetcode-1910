# Leetcode-1910

# C++

class Solution {
public:
    string removeOccurrences(string s, string part) {
        string ans="";
        int n=s.length(),m=part.length();
        char a=part[m-1];
        for(int i=0;i<n;i++)
        {
            if(s[i]==a&&ans.length()>=m-1)
            {
              string t=ans.substr(ans.length()-m+1,m-1)+a;
              cout<<t<<"\n";
              if(t==part)
              {
                 for(int j=0;j<m-1;j++)ans.pop_back();
                 cout<<ans<<"\n";
              }
              else
              {
                 ans+=s[i];
              }
            }
            else
            ans+=s[i];
        }
        return ans;
    }
};

# Python

class Solution:
    def removeOccurrences(self, s: str, part: str) -> str:
        while part in s:
            s = s.replace(part, "", 1)  # Remove only the first occurrence in each iteration
        return s


# Java

class Solution {
    public String removeOccurrences(String s, String part) {
        while (s.contains(part)) {
            s = s.replaceFirst(part, ""); // Remove only the first occurrence
        }
        return s;
    }
}
