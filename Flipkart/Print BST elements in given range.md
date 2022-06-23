```java
class Solution
{   
    //Function to return a list of BST elements in a given range.
	public static ArrayList<Integer> printNearNodes(Node root,int low,int high) {
        TreeSet<Integer> ans=new TreeSet<Integer>();
        solve(root,low,high,ans);
        
        return new ArrayList<Integer>(ans);
    }
    public static void solve(Node root,int low,int high,TreeSet<Integer> ans){
        if(root==null){
            return;
        }
        
        if(root.data>low && root.data>high){
            solve(root.left,low,high,ans);
        }else if(root.data<low && root.data<high){
            solve(root.right,low,high,ans);
        } else{
            solve(root.left,low,high,ans);
            ans.add(root.data);
            solve(root.right,low,high,ans);
        }
    }
}
```
