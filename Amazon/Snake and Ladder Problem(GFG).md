```java
//Level order traversal 
class Solution{
    static int minThrow(int N, int arr[]){
        HashMap<Integer,Integer> ladder=new HashMap<Integer,Integer>();
        HashMap<Integer,Integer> snake=new HashMap<Integer,Integer>();
        for(int i=0;i<2*N;i++){
            if(arr[i]>arr[i+1]){
                snake.put(arr[i],arr[i+1]);
                i++;
            }else{
                ladder.put(arr[i],arr[i+1]);
                i++;
            }
        }
        
        Queue<Integer> q=new LinkedList<>();
        int ans=1;
        q.offer(1);
        
        while(!q.isEmpty()){
            int size=q.size();
            for(int s=0;s<size;s++){
                int curr_pos=q.poll();
                for(int dice=1;dice<=6;dice++){
                    int new_pos=curr_pos+dice;
                    if(ladder.containsKey(new_pos)){
                        new_pos=ladder.get(new_pos);
                    }else if(snake.containsKey(new_pos)){
                        new_pos=snake.get(new_pos);
                    }
                    
                    if(new_pos==30){
                        return ans;
                    }
                    q.offer(new_pos);
                }
            }
            ans++;
        }
        
        return ans;
    }
}

```
