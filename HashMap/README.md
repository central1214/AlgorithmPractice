# HashMap이란?

![HashMap 구조](https://blog.kakaocdn.net/dn/cfpMTT/btqEvxLt6qb/MXYNWUvXCKfRvNWjDMZoq0/img.png)

이미지출처 - https://coding-factory.tistory.com/
 - Java Collections Framework에 속한 구현체 클래스이면서, Map [인터페이스](https://limkydev.tistory.com/197)를 구현한 함수이다. 
따라서 데이터의 저장은 key, value 형태가 된다.  key 값의 hashCode를 index로 Array에 값을 저장한다. __따라서 검색속도는 매우 빠르다.__
그리고 해싱(Hashing) 검색을 사용하기 때문에 대용량 데이터 관리에도 좋은 성능을 보여주고 있다. 
__key 값은 중복이 되지 않고, value 값은 허용__ 이 된다. (파이썬의 딕셔너리와 유사)

## 사용방법
### 데이터 넣기
  - put() 함수 사용
  - 첫번째 인수 : key 값 | 두번째 인수 : value 값
```java
  // 해쉬맵
HashMap<Integer, String> map = new HashMap<Integer, String>();
// 값넣는 방법
map.put(1, "정훈");
map.put(2, "우영");
map.put(3, "예진");
map.put(3, "커피"); // 3번 키값은 중복이므로 마지막에 입력한 값이 덮어 씌워진다.
// map.put(4.0, "쥬스"); // 컴파일 에러 (key값에 실수를 넣으면 에러)
System.out.println(map);
```
```java
// 출력
{1=정훈, 2=우영, 3=커피}
```


### 값 가져오기
  - get() 함수 사용
```java
String val = map.get(2).toString();
System.out.println("key값 2의 데이터 : " + val);
```
```java
// 출력
key값 2의 데이터 :  우영
```
### 저장된 데이터 지우기
  - 모든 데이터 지우기
   - clear() 함수 사용
```java

System.out.println(map);
map.clear(); // 삭제
System.out.println(map);
```
```java
/ 출력
{1=정훈, 2=우영, 3=커피}
{}
비어 있는지 체크: true
```
  ### 특정 키값 지우기
  - remove(key값) 함수 사용
```java
// 특정 값 삭제하기
map.put(1, "정훈");
map.put(2, "우영");
map.put(3, "예진");
 
Object value = map.remove(3); //3번 key
System.out.println("Key 값 삭제후 데이터 리턴받은 결과 : " + value);

```
```java
// 출력
Key 값 삭제후 데이터 리턴받은 결과 :  예진 // remove함수는 지정한 key를 삭제함과 동시에 value를 리턴한다
```
