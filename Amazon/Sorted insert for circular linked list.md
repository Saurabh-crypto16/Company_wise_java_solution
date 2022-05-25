```java
class Solution{
	public static Node sortedInsert(Node head,int data){
        //if list is empty
        if(head==null){
            return new Node(data);
        }
        
        //if list has only 1 node
        if(head.next==head){
            if(data>=head.data){
                Node temp=new Node(data);
                head.next=temp;
                temp.next=head;
                return head;
            }else{
                Node newHead=new Node(data),nh=newHead;
                newHead.next=head;
                head.next=newHead;
                return nh;
            }
        }
        
        Node last=head,curr=head;
        while(true){
            if(curr.next==head){
                last=curr;
                break;
            }
            curr=curr.next;
        }
        
        //if data is less than head
        if(head.data>=data){
            last.next=new Node(data);
            last.next.next=head;
            head=last.next;
            return head;
        }
        
        //if data is greater than head
        curr=head;
        while(true){
            if(curr.data>=data){
                last.next=new Node(data);
                last=last.next;
                last.next=curr; 
                break;
            }
            last=curr;
            curr=curr.next;
        }
        
        return head;
    }
}
```
