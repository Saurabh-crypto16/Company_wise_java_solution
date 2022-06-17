```java
class Check{
    
    public int firstNonRepeating(int arr[], int n) 
    { 
        HashMap<Integer,Integer> map=new HashMap<>();
        for(int i=0;i<n;i++){
            if(map.containsKey(arr[i])){
                map.put(arr[i],0);
            }else{
                map.put(arr[i],1);
            }
        }
        
        for(int key: arr){
            if(map.get(key)==1) return key;
        }
        
        return -1;
    }  
    
}


```
