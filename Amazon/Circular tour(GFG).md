```java
class Solution
{
    //Function to find starting point where the truck can start to get through
    //the complete circle without exhausting its petrol in between.
    int tour(int petrol[], int distance[])
    {
	    int defecit=0,balance=0,start=0;
	    
	    for(int i=0;i<petrol.length;i++){
	        balance+=(petrol[i]-distance[i]);
	        
	        if(balance<0){
	            start=i+1;
	            defecit+=balance;
	            balance =0;
	        }
	    }
	    
	    if(defecit+balance>=0){
	        return start;
	    }else{
	        return -1;
	    }
    }
}
```
