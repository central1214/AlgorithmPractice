# 기능 개발


```java
import java.util.*;
class Solution {
    public ArrayList solution(int[] progresses, int[] speeds) {
         ArrayList<Integer> list = new ArrayList<Integer>();
		 int[] product = new int[100];
		 int max = 0;		 
		 
		 Queue<Integer> qq = new LinkedList<Integer>();
		 for(int i = 0; i < progresses.length; i++) {
			 progresses[i] = (int)Math.ceil((double)(100 - progresses[i]) / (double)speeds[i]); // Math.ceil (올림)
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
- 큐스택 관련 문제라 억지로 큐를 사용했다 (굳이 쓰지 않아도..)
- qq.poll()은 qq객체에서 요소를 꺼내서 반환하기 때문에 26line의 조건문에서는 삭제없이 요소를 읽어오는 qq.peek()을 사용했다

### 프로그래머스에서 가장 추천을 많이 받은 답
```java
import java.util.ArrayList;
import java.util.Arrays;
class Solution {
    public int[] solution(int[] progresses, int[] speeds) {
        int[] dayOfend = new int[100];
        int day = -1;
        for(int i=0; i<progresses.length; i++) {
            while(progresses[i] + (day*speeds[i]) < 100) {
                day++;
            }
            dayOfend[day]++;
        }
        return Arrays.stream(dayOfend).filter(i -> i!=0).toArray();
    }
}
```
- 람다를 이용해서 풀었다
- 람다를 공부하자...
- but 효율성 면에서는 아주 안 좋다고 한다
