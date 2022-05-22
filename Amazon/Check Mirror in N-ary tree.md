```java
/*
for each edge i->j make a stack and for j and push j on it
iterate 2nd array and the i->j edge should be reverse order
for eg:    1 2 1 3
           1 3 1 2
           
           Stack for 1-> 3
                         2
           while iterating B we should pop each if j is same
*/
class Solution {
    static int checkMirrorTree(int n, int e, int[] A, int[] B) {
        HashMap<Integer,Stack<Integer>> map=new HashMap<>();
        
        for(int i=0;i<2*e;i+=2){
            if(!map.containsKey(A[i]))  map.put(A[i],new Stack<Integer>());
            map.get(A[i]).push(A[i+1]);
        }
        
        for(int i=0;i<2*e;i+=2){
            if(!map.containsKey(B[i]))  return 0;
            if(map.get(B[i]).peek()==B[i+1]){
                map.get(B[i]).pop();
            }else{
                return 0;
            }
        }
        
        return 1;
    }
};
```
