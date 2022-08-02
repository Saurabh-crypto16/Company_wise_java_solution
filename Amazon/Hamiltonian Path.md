```java
class Solution { 
    boolean check(int n, int M, ArrayList<ArrayList<Integer>> Edges){ 
        ArrayList<ArrayList<Integer>>graph = new ArrayList<>();
        for(int i=0; i<n; i++)  graph.add(new ArrayList<Integer>());
           
        for(ArrayList<Integer> edge : Edges){
            graph.get(edge.get(0)-1).add(edge.get(1)-1);
            graph.get(edge.get(1)-1).add(edge.get(0)-1);
        }
        
        Set<Integer> vis = new HashSet<>();
        for(int i=0; i<n; i++)
           if(dfsHamiltonianPath(i, n, vis, graph))  return true;
           
        return false;
    }
    
    boolean dfsHamiltonianPath(int node, int n, Set<Integer> vis, 
                    ArrayList<ArrayList<Integer>>graph){
       if(vis.size() == n-1 && !vis.contains(node))   return true;
       
       vis.add(node);
       
       boolean path=false;
       for(int nbr : graph.get(node))
            if(!vis.contains(nbr)){
                path = (path || dfsHamiltonianPath(nbr, n, vis, graph));
                if(path)    break;
            }
       
       vis.remove(node);
       
       return path;
    }
} 
```
