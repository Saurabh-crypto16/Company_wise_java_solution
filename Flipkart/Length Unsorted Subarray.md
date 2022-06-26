```java
class Solve {
    int[] printUnsorted(int[] arr, int n) {
        int min=Integer.MAX_VALUE,max=Integer.MIN_VALUE;
        boolean flag=false;
        
        for(int i=1;i<n;i++){
            if(arr[i]<arr[i-1])     flag=true;
            if(flag)    min=Math.min(min,arr[i]);
        }
        
        flag=false;
        for(int i=n-2;i>=0;i--){
            if(arr[i]>arr[i+1])     flag=true;
            if(flag)    max=Math.max(max,arr[i]);
        }
        
        //System.out.println(min+" "+max);
        
        int s=0,e=0;
        for(s=0;s<n;s++){
            if(min<arr[s])  break;
        }
        for(e=n-1;e>=0;e--){
            if(max>arr[e])  break;
        }
        
        return (s>=n || e<=0) ? new int[]{0,0} : new int[]{s,e};
    }
}
```
