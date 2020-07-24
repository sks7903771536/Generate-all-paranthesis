# Generate-all-paranthesis
class Solution {
public:
    
    void solve(string op,int o,int c,vector<string> &v)
    {
        if(o==0&&c==0)
        {
            
            v.push_back(op);
            return ;
        }
        
        if(o!=0)
        {
            string op1=op;
            op1.push_back('(');
            solve(op1,o-1,c,v);
        }
        if(c>o)
        {
           
            string op2=op;
            
            if(c) {
                 op2.push_back(')');
                 solve(op2,o,c-1,v);
             }
             
        }return ;
    }
    vector<string> generateParenthesis(int n) {
        
        vector<string> v;
        if(n==0) return v;
        int o=n,c=n;
        string op;
       
        solve(op,o,c,v);
        return v;
    }
};
