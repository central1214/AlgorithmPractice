# 문자열 자르기 substring
 - 사용법
 ```java
 String.substring(start) //문자열  start위치부터 끝까지 문자열 자르기
String.substring(start,end) //문자열  start위치 부터 end전까지 문자열 발췌
		


String str = "ABCDEFG"; //대상 문자열
/*A=0 B=1 C=2 D=3 E=4 F=5 G=6의 index를 가진다.*/
		
str.substring(3); 
/*substring(시작위치) 결과값 = DEFG*/

str.substring(3, 6); 
/*substring(시작위치,끝위치) 결과값 = DEF*/
```
- 활용
```java
//1. 마지막 3글자 자르기
String str = "ABCDEFG"; 
String result = str.substring(str.length()-3, str.length());
System.out.println(result)
 //결과값EFG



//2. 특정문자 이후의 문자열 제거
String str = "ABCD/DEFGH";
String result = str.substring(str.lastIndexOf("/")+1);
System.out.println(result); 
//결과값 DEFGH



//3. 특정단어(부분)만 자르기
String str = "바나나 : 1000원, 사과 : 2000원, 배 : 3000원";
String target = "사과";
int target_num = str.indexOf(target); 
String result; result = str.substring(target_num,(str.substring(target_num).indexOf("원")+target_num));
System.out.println(result+"원"); 
//결과값 : 사과 : 2000원
```
