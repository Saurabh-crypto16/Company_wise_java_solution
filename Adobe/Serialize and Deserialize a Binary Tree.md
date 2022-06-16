```java
class Tree 
{
    //Function to serialize a tree and return a list containing nodes of tree.
	public void serialize(Node root, ArrayList<Integer> A) 
	{
	    if(root != null) {
	        A.add(root.data);
	        serialize(root.left, A); 
	        serialize(root.right, A);
	    }
	    else{
	        A.add(Integer.MAX_VALUE); 
	    } 
	}
	
	//Function to deserialize a list and construct the tree.
    public Node deSerialize(ArrayList<Integer> A)
    {
        Queue<Integer> q = new LinkedList<>();
        for(int i = 0; i < A.size(); ++i) {
            q.offer(A.get(i));  
        }
        
        return solve(q); 
    }
    public Node solve(Queue<Integer> q) {
	    if(q == null || q.isEmpty()) {
	        return null; 
	    }
	    
	    int curr = q.poll(); 
	    if(curr == Integer.MAX_VALUE)   return null;  
	        
	    Node newNode = new Node(curr);  
	    newNode.left = solve(q); 
	    newNode.right = solve(q); 
	    return newNode; 
	}
};
```
