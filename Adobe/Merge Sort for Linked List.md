```java
class Solution
{
    //Function to sort the given linked list using Merge Sort.
    static Node mergeSort(Node head)
    {
        if(head==null || head.next==null)   return head;
        
        Node mid=findMid(head);
        Node left=head;
        Node right=mid.next;
        mid.next=null;
        
        left=mergeSort(left);
        right=mergeSort(right);
        
        Node result=merge(left,right);
        
        return result;
    }
    public static Node findMid(Node head){
        Node fast=head.next,slow=head;
        
        while(fast!=null && fast.next!=null){
            fast=fast.next.next;
            slow=slow.next;
        }
        
        return slow;
    }
    public static Node merge(Node left,Node right){
        if(left==null)  return right;
        if(right==null)  return left;
        
        Node res=new Node(-1),res_head=res;
        while(left!=null && right!=null){
            if(left.data<right.data){
                res.next=new Node(left.data);
                res=res.next;
                left=left.next;
            }else{
                res.next=new Node(right.data);
                res=res.next;
                right=right.next;
            }
        }
        
        while(left!=null){
            res.next=new Node(left.data);
            res=res.next;
            left=left.next;
        }
        
        while(right!=null){
            res.next=new Node(right.data);
            res=res.next;
            right=right.next;
        }
        
        return res_head.next;
    }
}
```
