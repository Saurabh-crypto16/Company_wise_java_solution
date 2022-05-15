```java
// m is the given matrix and n is the order of matrix
class Solution {
    static ArrayList<String> res;
    public static ArrayList<String> findPath(int[][] m, int n) {
        res=new ArrayList<>();
        solve(0,0,n,m,"");
        
        return res;
    }
    public static void solve(int i,int j,int n,int[][] m,String path){
        if(i<0 || i>=n || j<0 || j>=n || m[i][j]==0){
            return;
        }
        
        if(i==n-1 && j==n-1){
            res.add(path);
            return;
        }
        
        m[i][j]=0;
        solve(i+1,j,n,m,path+"D");
        solve(i,j-1,n,m,path+"L");
        solve(i,j+1,n,m,path+"R");
        solve(i-1,j,n,m,path+"U");
        m[i][j]=1;
    }
}
```
