```java
class Solution
{ 
    //Function to find if there is a celebrity in the party or not.
    int celebrity(int M[][], int n)
    {
    	Stack<Integer> st=new Stack<>();
    	for(int i=0;i<n;i++)   st.push(i);
    	
    	while(st.size()>1){
    	    int ec1=st.pop();
    	    int ec2=st.pop();
    	    
    	    if(M[ec1][ec2]==1){
    	        st.push(ec2);
    	    }else{
    	        st.push(ec1);
    	    }
    	}
    	
    	int ec=st.pop();
    	
    	for(int i=0;i<n;i++){
    	    for(int j=0;j<n;j++){
    	        if(i==ec && j==ec && M[i][j]==1){
    	            return -1;
    	        }else if(i==ec && M[i][j]==1){
    	            return -1;
    	        }else if(j==ec && i!=ec && M[i][j]==0){
    	            return -1;
    	        }
    	    }
    	}
    	
    	return ec;
    }
}
```
