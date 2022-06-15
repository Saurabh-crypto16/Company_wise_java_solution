```java
class Solution {
    public ArrayList<ArrayList<Integer>> fourSum(int[] arr, int k) {
        ArrayList<ArrayList<Integer>> ans=new ArrayList<>();
        Arrays.sort(arr);
        
        for(int i=0;i<arr.length-3;i++){
            for(int j=i+1;j<arr.length-2;j++){
                int left=j+1,right=arr.length-1;

                while(left<right){
                    if(arr[i]+arr[j]+arr[left]+arr[right]==k){
                        ArrayList<Integer> curr=new ArrayList<>();
                        curr.add(arr[i]);
                        curr.add(arr[j]);
                        curr.add(arr[left]);
                        curr.add(arr[right]);
                        if(!ans.contains(curr)){
                            ans.add(curr);
                        }
                        left++;
                        right--;
                    }else if(arr[i]+arr[j]+arr[left]+arr[right]>k){
                        right--;
                    }else{
                        left++;
                    }
                }
            }
        }
        
        return ans;
    }
}
```
