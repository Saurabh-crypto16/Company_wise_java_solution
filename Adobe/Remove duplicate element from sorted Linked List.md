```java
class GfG
{
    //Function to remove duplicates from sorted linked list.
    Node removeDuplicates(Node head)
    {
    	Node prev=head,curr=head;
    	
    	while(prev!=null){
    	    while(curr!=null && curr.data==prev.data) curr=curr.next;
    	    
    	    prev.next=curr;
    	    prev=curr;
    	}
    	
    	return head;
    }
}
```
