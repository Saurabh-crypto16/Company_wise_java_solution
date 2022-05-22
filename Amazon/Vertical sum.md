```java
class Solution{
    class HNode{
        Node node;
        int h;
        HNode(Node node,int h){
            this.node=node;
            this.h=h;
        }
    }
    public ArrayList <Integer> verticalSum(Node root) {
        TreeMap<Integer,Integer> map=new TreeMap<>();
        Queue<HNode> q=new LinkedList<>();
        
        q.offer(new HNode(root,0));
        
        while(!q.isEmpty()){
            HNode curr=q.poll();
            
            map.put(curr.h,map.getOrDefault(curr.h,0)+curr.node.data);
            
            if(curr.node.left!=null)    q.offer(new HNode(curr.node.left,curr.h-1));
            if(curr.node.right!=null)    q.offer(new HNode(curr.node.right,curr.h+1));
        }
        
        ArrayList<Integer> res=new ArrayList<>();
        for(int key: map.keySet()){
            res.add(map.get(key));
        }
        
        return res;
    }
}
```
