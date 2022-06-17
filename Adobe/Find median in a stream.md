```java
class Solution
{
    static PriorityQueue<Integer> min=new PriorityQueue<>();//contains numbers greater than x
    static PriorityQueue<Integer> max=new PriorityQueue<>(Collections.reverseOrder());
    //contains numbers less than x
    
    public static void insertHeap(int x){
        if(max.isEmpty() || max.peek()>=x){
            max.offer(x);
        }else{
            min.offer(x);
        }
        
        if(max.size()>min.size()+1){
           min.offer(max.poll());
        }else if(max.size()<min.size()){
           max.offer(min.poll());
        }
    }
    
    //Function to balance heaps.
    public static void balanceHeaps()
    {
       
    }
    
    //Function to return Median.
    public static double getMedian()
    {
        if(!max.isEmpty()){
            if(min.size()==max.size()){
                return (min.peek()+max.peek())/2.0;
            }
            
            return max.peek();
        }
        return -1;
    } 
}
```
