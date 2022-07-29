```java
class Solution {
    public boolean isPossible(int N, int[][] prerequisites){
       // Your Code goes here
       //creating an adjacentcy list
       ArrayList<ArrayList<Integer>> adj = new ArrayList<ArrayList<Integer>>();
       for(int i=0;i<N;i++){
           adj.add(new ArrayList<Integer>());
       }
       for(int p[] : prerequisites){
           adj.get(p[0]).add(p[1]);
       }
       
       boolean[] visited = new boolean[N];
       boolean[] dfsVis = new boolean[N];
       
       for(int i=0;i<N;i++){
            if(!visited[i]){
                if(checkCycle(i,adj,visited,dfsVis)){
                    return false;
                }
            }
        }
       
        return true;
   }
   
    public boolean checkCycle(int node,ArrayList<ArrayList<Integer>> adj,boolean[] visited, 
        boolean[] dfsVis){
        visited[node] = true;
        dfsVis[node] = true;
        
        for(int it: adj.get(node)){
            if(!visited[it]){
                if(checkCycle(it,adj,visited,dfsVis)){
                    return true;
                }
            }else if(dfsVis[it]){
               return true;
            }
        }
       
        dfsVis[node] = false;
        return false;
   }
    
}
```
