```java
class Solution{
    //Function to connect nodes at same level.
    public void connect(Node root){
        if(root==null)  return;
        
        Queue<Node> q=new LinkedList<>();
        q.offer(root);
        
        while(!q.isEmpty()){
            int size=q.size();
            
            Node temp=new Node(-1);
            while(size-->0){
                Node curr=q.poll();
                
                temp.nextRight=curr;
                temp=curr;
                
                if(curr.left!=null) q.offer(curr.left);
                if(curr.right!=null) q.offer(curr.right);
            }
        }
    }
}
```
