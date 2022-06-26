```java
class Solution {
    static ArrayList<Integer> max_of_subarrays(int arr[], int n, int k) {
        ArrayList<Integer> ans=new ArrayList<Integer>();
        Deque<Integer> dq=new ArrayDeque<>();
        
        for(int i=0;i<n;i++){
            if(!dq.isEmpty() && dq.peek()==i-k){
                dq.poll();
            }
            
            while(!dq.isEmpty() && arr[dq.peekLast()]<arr[i]){
                dq.pollLast();
            }
            
            dq.offer(i);
            if(i>=k-1){
                ans.add(arr[dq.peek()]);
            }
        }
        
        return ans;
    }
}
```
