```java
class Solution
{
    // return the Kth largest element in the given BST rooted at 'root'
    int ans[];
    public int kthLargest(Node root,int K)
    {
        ans=new int[2];
        solve(root,K);
        
        return ans[1];
    }
    public void solve(Node root,int k){
        if(root==null)  return;
        
        solve(root.right,k);
        if(++ans[0]==k){
            ans[1]=root.data;
            return;
        }
        solve(root.left,k);
    }
}
```
