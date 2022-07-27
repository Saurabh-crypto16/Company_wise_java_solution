```java
class Solution
{
    boolean flag=false;
    void solve(int arr[],int vin,int k,int n,int sssf,int sumSet[], 
            ArrayList<ArrayList<Integer>> li ){
        if(vin==arr.length){
            //sssf means number of filled subsets
            if(sssf==k){
                boolean fl=true;
                for(int i=0;i<k-1;i++){
                    if(sumSet[i]!=sumSet[i+1]){
                       fl=false;
                       break;
                    } 
                }
                if(fl==true)    flag=true;
            }
            return ;
        }
        
            for(int i=0;i<k;i++){
                if(li.get(i).size()>0){
                    //adding in existing subset
                        li.get(i).add(arr[vin]);
                        sumSet[i]+=arr[vin];
                        solve(arr,vin+1,k,n,sssf,sumSet,li);
                        sumSet[i]-=arr[vin];
                        li.get(i).remove(li.get(i).size()-1);
                }else{
                    //adding in new subset
                        li.get(i).add(arr[vin]);
                        sumSet[i]+=arr[vin];
                        solve(arr,vin+1,k,n,sssf+1,sumSet,li);
                        sumSet[i]-=arr[vin];
                        li.get(i).remove(li.get(i).size()-1);   
                        break;
                }
            }
    }
    
    public boolean isKPartitionPossible(int a[], int n, int k)
    {
        if(k==1)return true;
        
        int sum=0; 
        for(int val: a){
            sum+=val;
        }
        if(sum%k!=0)return false;
        
        int sumSet[]=new int[k];
        ArrayList<ArrayList<Integer>> li=new ArrayList<>();
        for(int i=0;i<k;i++){
            li.add(new ArrayList<>());
        }
        
        solve(a,0,k,n,0,sumSet,li);
        return flag;
        
    }
}
```
