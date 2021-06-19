# 효율성 테스트 실패~!~!~!!~!~~!

```java
import java.util.HashMap;
    class Solution {
    public boolean solution(String[] phone_book) {
       
        
		HashMap<Integer, String> map = new HashMap<Integer, String>();
		for(int i = 0; i < phone_book.length; i++) {
			map.put(i, phone_book[i]);
		}
		for(int i = 0; i < map.size(); i++) {
			for(int j = 0; j < map.get(i).length(); j++) {
				if(map.containsValue(map.get(i).substring(0,j))) {
					return false;
					
				}
			}
		}
        return true;
    }
}
```
- 효율성 테스트에서 2/4만 통과하고 실패한 코드
- 배열을 이용하기 싫어서 억지로 해쉬로 했다.

# 효율성 테스트 까지 통과한 코드

```java
import java.util.Arrays;
class Solution {
	public boolean solution(String[] phone_book) {
		
		Arrays.sort(phone_book);
		
		for (int i = 0; i < phone_book.length - 1; i++) {
			if (phone_book[i + 1].startsWith(phone_book[i])) {
				return false;
			}
		}
		return true;
	}
}
```
- Arrays.sort() 함수를 이용했다. <- Arrays.sort()함수의 특성은 [여기로](https://github.com/central1214/AlgorithmPractice/tree/main/UsefulMethod/%EB%AC%B8%EC%9E%90%EC%97%B4%20%EC%9E%90%EB%A5%B4%EA%B8%B0)
- 덕분에 for문을 1회만 써서 효율성 테스트에 성공!

# 효율성 테스트 성공 & 해쉬맵을 쓴 코드

```java
import java.util.Arrays;
import java.util.HashMap;
class Solution {
	public boolean solution(String[] phone_book) {
	Arrays.sort(phone_book);
	HashMap<Integer, String> map = new HashMap<Integer, String>();
	for(int i = 0; i < phone_book.length; i++) {map.put(i, phone_book[i]);}
	for(int i = 0; i < map.size()-1; i++) {				
		if(map.get(i).length() <= map.get(i+1).length()) {
		if(map.get(i).equals(map.get(i+1).substring(0,map.get(i).length()))) {return false;}
			}
		} return true;
	}
}
```
- Arrays.sort() 함수를 해쉬맵에도 적용해서 풀었다
- 효율성 테스트에서도 근소하지만 더 좋게 나왔다!
