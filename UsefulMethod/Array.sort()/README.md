# Array.sort()
### 자바에서 기본적으로 제공 해주는 배열을 정렬할 때 사용하는 함수
 - int형 자료들이야 각 요소들의 대소를 비교하여 오름차순, 혹은 내림차순으로 정렬이 되지만 문자열의 경우 어떻게 정렬할까?

### 사용법
#### int 배열정렬
  - default는 오름차순이다.
```java
int[] arr = {1, 26, 17, 25, 99, 44, 303};

Arrays.sort(arr);

System.out.println("Sorted arr[] : " + Arrays.toString(arr));
```
```java
Sorted arr[] : [1, 17, 25, 26, 44, 99, 303]
```

  - 내림차순으로 하려면 sort()의 인자에 Collections.reverseOrder()를 전달한다.
```java
Integer[] arr = {1, 26, 17, 25, 99, 44, 303};

Arrays.sort(arr, Collections.reverseOrder());

System.out.println("Sorted arr[] : " + Arrays.toString(arr));
```
```java
Sorted arr[] : [303, 99, 44, 26, 25, 17, 1]
```   <br>

#### 부분정렬
   - 배열 전체가 아닌 지정된 범위 안에서만 정렬이 가능하다.
   - sort()의 인자에 원하는 index범위를 전달한다.
```java
int[] arr = {1, 26, 17, 25, 99, 44, 303};

Arrays.sort(arr, 0, 4);

System.out.println("Sorted arr[] : " + Arrays.toString(arr));
```
#### String형 정렬
  - int형 정렬과 같다.
  - 알파벳의 아스키 값으로 비교를 하여 정렬을 한다.
```java
String[] arr = {"Apple", "Kiwi", "Orange", "Banana", "Watermelon", "Cherry"};

Arrays.sort(arr);

System.out.println("Sorted arr[] : " + Arrays.toString(arr));
```
```java
Sorted arr[] : [Apple, Banana, Cherry, Kiwi, Orange, Watermelon]
```
#### 다양한 문자열 비교 
- 길이가 같을 경우 첫 글자부터 비교후 정렬, 그후 2번째 글자들끼리 정렬한다
```java
String[] num = {"12", "13", "11", "10", "22","20", "21",};
		Arrays.sort(num);
		System.out.println("Sorted arr[] : " + Arrays.toString(num));
```
```java
Sorted arr[] : [10, 11, 12, 13, 20, 21, 22]
```
- 길이가 다를 경우 char형 비교후 길이가 짧은 순서대로 정렬한다
```java
String[] num = {"12", "13", "11", "10", "22","20", "21", "123", "124","125","126", "112", "113","114","11222","11322"};
		Arrays.sort(num);
		System.out.println("Sorted arr[] : " + Arrays.toString(num));
 ```
```java
Sorted arr[] : [10, 11, 112, 11222, 113, 11322, 114, 12, 123, 124, 125, 126, 13, 20, 21, 22]
```
