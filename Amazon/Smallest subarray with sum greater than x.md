```java
class Solution {

    public static int smallestSubWithSum(int a[], int n, int x) {
        int i=0,j=0,sum=0,ans=Integer.MAX_VALUE;
        
        while(i<=j && j<n){
            while(sum<=x && j<n){
                sum+=a[j++];
            }
            while(sum>x && i<j){
                ans=Math.min(ans,j-i);
                sum-=a[i++];
            }
        }
        
        return ans;
    }
}
