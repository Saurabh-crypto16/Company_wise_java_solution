```java
class GfG{
    /*You are required to complete this method*/
    Node delete(Node head, int k){
        if(head==null || k==1)  return null;
        if(k==0)    return head;
	    Node new_head=head;
	    
	    int idx=1;
	    while(head!=null && head.next!=null){
	        if(idx%(k-1)==0){
	            head.next=head.next.next;
	        }
	        
	        head=head.next;
	        idx++;
	    }
	    
	    return new_head;
    }
}
```
