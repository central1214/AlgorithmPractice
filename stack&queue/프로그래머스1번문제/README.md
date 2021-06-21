```java
import java.util.*;
class Solution {
    public ArrayList solution(int[] progresses, int[] speeds) {
         ArrayList<Integer> list = new ArrayList<Integer>();
		 int[] product = new int[100];
		 int max = 0;		 
		 
		 Queue<Integer> qq = new LinkedList<Integer>();
		 for(int i = 0; i < progresses.length; i++) {
			 progresses[i] = (int)Math.ceil((double)(100 - progresses[i]) / (double)speeds[i]);
		 }
		 
		 for(int i : progresses) {
			 qq.add(i);
			 
		 }
		 
		 max = qq.poll();
		 product[0] = 1;
		 int i = 0;
		 while(qq.isEmpty() == false) {
			 if(max >= qq.peek()) {
                 qq.poll();
				 product[i]++;		
				 
			 }
			 else {
                 max = qq.poll();
				 i++;
				 product[i]++;
			 }
		 }
		 for(int j : product) {
			if(j == 0) {
				break;
			}
			
			 list.add(j);
		 }
		
        
        return list;
    }
}
```
