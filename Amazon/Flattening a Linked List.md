```java
class GfG{
    Node merge2Lists(Node a,Node b){
        Node res=new Node(0),temp=res;
        
        while(a!=null && b!=null){
            if(a.data<b.data){
                temp.bottom=new Node(a.data);
                a=a.bottom;
            }else{
                temp.bottom=new Node(b.data);
                b=b.bottom;
            }
            temp=temp.bottom;
        }
        
        if(a!=null) temp.bottom=a;
        else    temp.bottom=b;
        
        return res.bottom;
    }
    Node flatten(Node root){
	    if(root==null || root.next==null)   return root;
	    
	    root.next=flatten(root.next);
	    
	    //merging last 2 lists every time
	    root=merge2Lists(root,root.next);
	    
	    return root;
    }
}
```
