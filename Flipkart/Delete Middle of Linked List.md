```java
class Solution {
    Node deleteMid(Node head) {
        // This is method only submission.
        // You only need to complete the method.
        Node fast=head,slow=head,prev=head;
        
        while(fast!=null && fast.next!=null){
            fast=fast.next.next;
            prev=slow;
            slow=slow.next;
        }
        
        prev.next=slow.next;
        
        return head;
    }
}
```
