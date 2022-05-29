```java
class Solution
{
    public static Node reverse(Node node, int k)
    {
        Node prev,next;
        Node head=node;
        prev=next=null;
        int i=0;
        
        while(head!=null && i<k){
            next=head.next;
            head.next=prev;
            prev=head;
            head=next;
            i++;
        }
        
        if(next!=null){
            node.next=reverse(next,k);
        }
        
        return prev;
    }
}

```
