```java
class Solution {
    // Function to get the maximum width of a binary tree.
    int getMaxWidth(Node root) {
        if(root==null)  return 0;
        
        Queue<Node> q=new LinkedList<>();
        q.offer(root);
        
        int ans=0;
        
        while(!q.isEmpty()){
            int size=q.size();
            ans=Math.max(ans,size);
            for(int i=0;i<size;i++){
                Node curr=q.poll();
                
                if(curr.left!=null) q.offer(curr.left);
                if(curr.right!=null) q.offer(curr.right);
            }
        }
        
        return ans;
    }
}
```
