```java

class Solution {
    static int findDistance(int x1, int y1, int x2, int y2){
        return (x2-x1)*(x2-x1)+(y2-y1)*(y2-y1);
    }
    static String isSquare(int x1, int y1, int x2, int y2, int x3, int y3, int x4, int y4) {
        Map<Integer,Integer> map=new HashMap<>();
        
        int d1=findDistance(x1,y1,x2,y2);
        map.put(d1,map.getOrDefault(d1,0)+1);
        
        int d2=findDistance(x1,y1,x3,y3);
        map.put(d2,map.getOrDefault(d2,0)+1);
        
        int d3=findDistance(x1,y1,x4,y4);
        map.put(d3,map.getOrDefault(d3,0)+1);
        
        int d4=findDistance(x2,y2,x3,y3);
        map.put(d4,map.getOrDefault(d4,0)+1);
        
        int d5=findDistance(x2,y2,x4,y4);
        map.put(d5,map.getOrDefault(d5,0)+1);
        
        int d6=findDistance(x3,y3,x4,y4);
        map.put(d6,map.getOrDefault(d6,0)+1);
        
        return map.size()==2 ? "Yes" : "No";
    }
};
```
