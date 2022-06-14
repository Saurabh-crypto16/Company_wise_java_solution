```java
class Solution
{
    //Function to remove a loop in the linked list.
    public static void removeLoop(Node head){
        // code here
        // remove the loop without losing any nodes
        Node sptr=head,fptr=head, prev=null;
        boolean flag = false;
        
        while(fptr!=null && fptr.next!=null){
            prev=fptr;
            sptr=sptr.next;
            fptr=fptr.next.next;
            if(sptr==fptr){
                flag=true;
                break;
            }
        }
        
        if(flag){
            sptr=head;
            if(sptr==fptr){
                prev.next.next=null;
                return;
            }
            while(sptr.next!=fptr.next){
                sptr=sptr.next;
                fptr=fptr.next;
            }
            fptr.next=null;
        }
    }
}
```
