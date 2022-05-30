```java
class Solution{
    //Function to find largest rectangular area possible in a given histogram.
    public static long getMaxArea(long hist[], long n){
        long maxA=0;
        //stack should store indexes of element of array in increasing order
        Stack<Integer> st=new Stack<>();
        
        for(int i=0;i<=(int)n;i++){
            while(!st.isEmpty() && (i==n || hist[st.peek()]>=hist[i])){
                //for each index i if hist[st.peek()] < hist[i]
                //then i becomes left boundary and top element becomes height 
                //and second top becomes left boundary
                long height=hist[st.pop()];
                long width;
                
                //if stack is empty then entire array till i is the width
                if(st.isEmpty())    width=i;
                else    width=i-st.peek()-1;
                
                maxA=Math.max(maxA,height*width);
            }
            st.push(i);
        }
        
        return maxA;
    }
}
```
