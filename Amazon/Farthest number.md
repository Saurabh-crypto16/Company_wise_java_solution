```java
class Solution { 
    static int[] farNumber(int n, int Arr[]){
        int suffix[]=new int[n];
        HashMap<Integer,Integer> map=new HashMap<>();
        
        for(int i=n-1;i>=0;i--){
            if(!map.containsKey(Arr[i]))    map.put(Arr[i],i);
            
            if(i==n-1)  suffix[i]=Arr[i];
            else suffix[i]=Math.min(suffix[i+1],Arr[i]);
        }
        
        Arr   =[3, 1, 5, 2, 4]
        suffix=[1, 1, 2, 2, 4]
        
        int ans[]=new int[n];
        Arrays.fill(ans,-1);
        
        //applying binary search for finding the farthest smallest element
        for(int i=0;i<n-1;i++){
            int curr=-1;
            int start=i+1,end=n-1;
            while(start<=end){
                int mid=start+(end-start)/2;
                
                if(suffix[mid]<Arr[i]){
                    curr=suffix[mid];
                    start=mid+1;
                }else{
                    end=mid-1;
                }
            }
            
            if(curr!=-1)    ans[i]=map.get(curr);
        }
        
        return ans;
	}
} 
```
