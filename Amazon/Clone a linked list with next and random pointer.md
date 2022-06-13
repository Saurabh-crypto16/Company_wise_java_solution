```java
class Clone {
    //Function to clone a linked list with next and random pointer.
    Node copyList(Node head) {
        Node nh=head;
        
        while(nh!=null){
            Node new_node=new Node(nh.data);
            new_node.next=nh.next;
            nh.next=new_node;
            nh=new_node.next;
        }
        
        Node ans=head.next;
        nh=head;
        while(nh!=null){
            if(nh.arb!=null)    nh.next.arb=nh.arb.next;
            nh=nh.next.next;
        }
        
        nh=head;
        while(nh!=null){
            Node copy=nh.next;
            nh.next=copy.next;
            if(copy.next!=null) copy.next=nh.next.next;
            nh=nh.next;
        }
        
        return ans;
    }
}
```
