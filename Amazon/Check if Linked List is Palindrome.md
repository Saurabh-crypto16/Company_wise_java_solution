```java
class Solution
{
    //Function to check whether the list is palindrome.
    boolean isPalindrome(Node head) 
    {
        Node fast=head,slow=head;
        
        while(fast!=null && fast.next!=null){
            slow=slow.next;
            fast=fast.next.next;
        }
        
        fast=head;
        slow=reverse(slow);
        
        while(fast!=null && slow!=null){
            if(fast.data!=slow.data)    return false;
            fast=fast.next;
            slow=slow.next;
        }
        
        return true;
    }    
    public Node reverse(Node head){
        if(head==null || head.next==null)   return head;
        
        Node newHead=reverse(head.next);
        head.next.next=head;
        head.next=null;
        
        return newHead;
    }
}
```
