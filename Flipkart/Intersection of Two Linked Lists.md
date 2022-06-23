```java
class Solution
{
    public static Node findIntersection(Node head1, Node head2)
    {
        Node ans=new Node(-1),ans_head=ans;
        
        HashSet<Integer> set=new HashSet<>();
        while(head2!=null) {
            set.add(head2.data);
            head2=head2.next;
        }
        
        while(head1!=null){
            if(set.contains(head1.data)){
                ans.next=new Node(head1.data);
                ans=ans.next;
            }       
            head1=head1.next;
        }
        
        return ans_head.next;
    }
}
```
