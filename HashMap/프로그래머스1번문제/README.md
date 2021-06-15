# Array.sort를 이용하여 푼 풀이
  
```java
import java.util.Arrays;


class Solution {
   public static String solution(String[] participant, String[] completion) {

		String answer = "";
		Arrays.sort(participant); //순서대로 정렬
		Arrays.sort(completion);
		String[] man = participant;
		String[] fin = completion;
		for (int i = 0; i < fin.length; i++) {
            
			if (man[i].equals(fin[i])) {
                answer = man[i+1];
			} else {
				answer = man[i];
				break;
			}

		}

		return answer;
	}
}
```
- 주의사항 
  - java에서 == 비교 연산자는 String형일 경우 주소값을 비교하기 때문에 .equals를 사용해야 한다
  - for문을 이용할 때는 index가 오버플로우되지 않도록 처음부터 범위를 잘 생각하자!
