```java
public static Node post_order(int pre[], int size) {
    int in[]=pre.clone();
    Arrays.sort(in);
    
    HashMap<Integer,Integer> inMap=new HashMap<>();
    for(int i=0;i<size;i++) inMap.put(in[i],i);
    
    return construct(pre,0,size-1,in,0,size-1,inMap);
} 
public static Node construct(int[] pre,int pStart,int pEnd,int[] in,int iStart,
    int iEnd,HashMap<Integer,Integer> inMap){
    if(pStart>pEnd || iStart>iEnd)  return null;
    
    Node root=new Node(pre[pStart]);
    int inRoot=inMap.get(pre[pStart]);
    int numsLeft=inRoot-iStart;
    
    root.left=construct(pre,pStart+1,pStart+numsLeft,in,iStart,inRoot-1,inMap);
    root.right=construct(pre,pStart+numsLeft+1,pEnd,in,inRoot+1,iEnd,inMap);
    
    return root;
}
```
