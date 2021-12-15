```java
public class Solution {
    public int solve(ArrayList<ArrayList<Integer>> A) {
        if(A==null || A.size()==0)  return 0;

        //Sorting based on ascending start time
        Collections.sort(A,(p1,p2) -> p1.get(0)-p2.get(0));

        //priority based on ascending end time
        PriorityQueue<ArrayList<Integer>> pq=new PriorityQueue<ArrayList<Integer>>
                ((p1,p2) -> p1.get(1)-p2.get(1));
        pq.offer(A.get(0));
        
        for(int i=1;i<A.size();i++){
            ArrayList<Integer> curr=A.get(i);
            ArrayList<Integer> earliest=pq.poll();  //ending earliest
            if(curr.get(0)>=earliest.get(1)){
                //if curr meeting will start after the earliest ending meeting
                //then updtae the earliest ending time to curr ending  
                earliest.add(1,curr.get(1));
            }else{
                //else add it to pq
                pq.offer(curr);
            }

            pq.offer(earliest);
        }

        return pq.size();
    }
}
```
