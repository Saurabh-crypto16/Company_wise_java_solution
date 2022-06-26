```java

class Solution
{
    //Function to return the sorted array.
    ArrayList <Integer> nearlySorted(int arr[], int num, int k)
    {
        PriorityQueue<Integer> pq=new PriorityQueue<>();
        for(int i: arr) pq.offer(i);
        ArrayList <Integer> ans=new ArrayList<>();
        
        while(!pq.isEmpty()){
            ans.add(pq.remove());
        }
        
        return ans;
    }
}

```
