```java
class Spiral{
    //Function to return a list containing the level order 
    //traversal in spiral form.	
    ArrayList<Integer> findSpiral(Node root){
        if(root==null)  return new ArrayList();
        
        ArrayList<Integer> res=new ArrayList<>();
        Queue<Node> q=new LinkedList<>();
        boolean flag=false;
        
        q.offer(root);
        
        while(!q.isEmpty()){
            int size=q.size();
            ArrayList<Integer> currLvl=new ArrayList<>();
            for(int i=0;i<size;i++){
                Node curr=q.poll();
                
                if(flag){
                    currLvl.add(curr.data);
                }else{
                    currLvl.add(0,curr.data);
                }
                
                if(curr.left!=null) q.offer(curr.left);
                if(curr.right!=null) q.offer(curr.right);
            }
            
            res.addAll(currLvl);
            flag=!flag;
        }
        
        return res;
    }
}
```
