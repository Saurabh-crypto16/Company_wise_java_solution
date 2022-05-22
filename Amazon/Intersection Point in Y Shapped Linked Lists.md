```java
class Intersect{
    //Function to find intersection point in Y shaped Linked Lists.
	  int intersectPoint(Node head1, Node head2){
        Node start1=head1,start2=head2;
         
        while(start1!=start2){
            if(start1.next==null){
                start1=head2;
            }else{
                start1=start1.next;
            }
            
            if(start2.next==null){
                start2=head1;
            }else{
                start2=start2.next;
            }
        }
        
        return start1.data;
	}
}
```
