```java
class Solution{
    //Function to add two numbers represented by linked list.
    static Node addTwoLists(Node first, Node second){
        // code here
        // return head of sum list
        Node ans=new Node(-1),ans_head=ans;
        
        first=reverse(first);
        second=reverse(second);
        int carry=0;
        
        while(first!=null || second!=null){
            int sum=carry;
            
            if(first!=null){
                sum+=first.data;
                first=first.next;
            }
            
            if(second!=null){
                sum+=second.data;
                second=second.next;
            }
            
            ans.next=new Node(sum%10);
            carry=sum/10;
            ans=ans.next;
        }
        
        if(carry>0){
            ans.next=new Node(carry);
        }
        
        return reverse(ans_head.next);
    }
    public static Node reverse(Node head){
        if(head==null || head.next==null)  return head;
        
        Node new_head=reverse(head.next);
        head.next.next=head;
        head.next=null;
        
        return new_head;
    }
}
```
