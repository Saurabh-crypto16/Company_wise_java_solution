```java
class Solution{
    static int minSteps(int D){
        int target=Math.abs(D),sum=0,steps=0;
        
        while(sum<target || (sum-target)%2!=0){
            steps++;
            sum+=steps;
        }
        
        return steps;
    }
}
```
