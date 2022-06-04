```java
class Solution
{
    //Function to find the least absolute difference between any node
    //value of the BST and the given integer.
    static int minDiff(Node  root, int K) 
    { 
        int ans=Integer.MAX_VALUE;
        
        while(root!=null){
            ans=Math.min(ans,Math.abs(root.data-K));
            
            if(root.data==K)    return 0;
            else if(root.data<K)    root=root.right;
            else root=root.left;
        }
        
        return ans;
    } 
}

```
