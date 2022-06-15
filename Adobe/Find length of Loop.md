```java
class Solution{
    //Function to find the length of a loop in the linked list.
    static int countNodesinLoop(Node head){
        Node fast=head,slow=head;
        int ans=0;
        
        while(fast!=null && fast.next!=null){
            fast=fast.next.next;
            slow=slow.next;
            
            if(fast==slow){
                slow=head;
                while(fast!=slow){
                    fast=fast.next;
                    slow=slow.next;
                }
                
                while(fast.next!=slow){
                    ans++;
                    fast=fast.next;
                }
                
                return ans+1;
            }
        }
        
        return 0;
    }
}
```
