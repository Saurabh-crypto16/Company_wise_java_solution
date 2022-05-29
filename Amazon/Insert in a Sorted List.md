```java
class Solution {
    Node sortedInsert(Node head, int key) {
        if(head.data>=key){
            Node newHead=new Node(key);
            newHead.next=head;
            return newHead;
        }
        
        Node curr=head.next,prev=head;
        while(curr!=null && curr.data<key){
            prev=curr;
            curr=curr.next;
        }
        
        prev.next=new Node(key);
        prev.next.next=curr;
        
        return head;
    }
}
```
