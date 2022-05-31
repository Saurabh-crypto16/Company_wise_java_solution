```java
class QueueNode implements Comparable<QueueNode>{
    int arr,idx,val;
    QueueNode(int arr,int idx,int val){
        this.arr=arr;
        this.idx=idx;
        this.val=val;
    }
    
    public int compareTo(QueueNode n){
        if(val>n.val)   return 1;
        else if(val<n.val)  return -1;
        return 0;
    }
}
class Solution{
    //Function to merge k sorted arrays.
    public static ArrayList<Integer> mergeKArrays(int[][] arr,int K){
        PriorityQueue<QueueNode> pq=new PriorityQueue<>();
        
        //adding first value of every array
        int size=0;
        for(int i=0;i<arr.length;i++){
            size+=arr[i].length;
            if(arr[i].length > 0){
                pq.offer(new QueueNode(i,0,arr[i][0]));
            }
        }
        
        ArrayList<Integer> ans=new ArrayList<>();
        while(!pq.isEmpty()){
            QueueNode n=pq.poll();
            ans.add(n.val);
            
            if(n.idx<K-1){
                pq.offer(new QueueNode(n.arr,n.idx+1,arr[n.arr][n.idx+1]));
            }
        }
        
        return ans;
    }
}
```
