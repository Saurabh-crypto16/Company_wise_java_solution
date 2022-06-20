```java
class GfG
{
    int minEle=Integer.MAX_VALUE;
    Stack<Integer> st=new Stack<>();
    //st.push(minEle);

    /*returns min element from stack*/
    int getMin()
    {
    	return st.isEmpty() ? -1 : minEle;
    }
    
    /*returns poped element from stack*/
    int pop()
    {
    	if(st.isEmpty())    return -1;	
    	
    	if(st.peek()==minEle){
    	    int poped=st.pop();
    	    minEle=st.pop();
    	    return poped;
    	}else{
    	    return st.pop();
    	}
    }

    /*push element x into the stack*/
    void push(int x)
    {
	    if(minEle==Integer.MAX_VALUE){
	        st.push(minEle);
	        st.push(x);
	        minEle=x;
	    }else if(x<=minEle){
	        st.push(minEle);
	        st.push(x);
	        minEle=x;
	    }else{
	        st.push(x);
	    }
    }	
}


```
