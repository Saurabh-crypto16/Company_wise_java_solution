```java
class Solution {
    public int largestRectangleArea(int[] heights) {
        int n = heights.length; 
        Stack<Integer> st = new Stack<>();
        int maxA = 0; 
        
        for(int i = 0;i<=n;i++) {
            while(!st.isEmpty() && (i==n || heights[st.peek()] >= heights[i])) {
                int height = heights[st.pop()];
                int width; 
                if(st.isEmpty()) width = i; 
                else width = i - st.peek() - 1; 
                maxA = Math.max(maxA, width * height); 
            }
            st.push(i); 
        }
        
        return maxA;
    }
    public int maxArea(int M[][], int n, int m) {
        int currRow[]=M[0];
        int ans=largestRectangleArea(currRow);
        
        for(int i=1;i<n;i++){
            for(int j=0;j<m;j++){
                if(M[i][j]==0){
                    currRow[j]=0;
                }else{
                    currRow[j]++;
                }
            }
            
            ans=Math.max(ans,largestRectangleArea(currRow));
        }
        
        return ans;
    }
}
```
