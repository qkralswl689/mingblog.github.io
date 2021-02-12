---
layout: post
title: "CodeUp-1066-if"
date: 2021-02-07
category : [Algorithm]
comments: true
---
# CodeUp_기초 100제(1066)

[문제 링크](https://www.codeup.kr/problem.php?id=1066)

▶ JAVA 코드 

```java
import java.util.*;
public class if_1066 {

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in); // 입력 클래스인 Scanner 객체 생성
		int a = sc.nextInt(); // 첫번째 정수 입력 후 a에 저장
		int b = sc.nextInt(); // 두번째 정수 입력 후 b에 저장
		int c = sc.nextInt(); // 세번째 정수 입력 후 c에 저장
		
		String result = ""; // 문자열 결과값 저장 변수 생성
		
		if(a%2==0) { // a의 짝,홀수 여부 판단
			result = "even";
		}else {
			result = "odd";
		}
		System.out.println(result); // a의 판단 결과값 출력
		if(b%2==0) { // b의 짝,홀수 여부 판단
			result = "even";
		}else {
			result = "odd";
		}
		System.out.println(result); // b의 판단 결과값 출력
		if(c%2==0) {// c의 짝,홀수 여부 판단
			result = "even";
		}else {
			result = "odd";
		}
		System.out.println(result); // c의 판단 결과값 출력
	}

}

```

▶ 코드 설명

    1) 입력 클래스인 Scanner 객체 생성
    2) 입력받을 변수 3개 생성
    3) 문자열 결과값 저장 변수 생성
    4) a~c의 짝,홀수 여부 판단
    5) a~c의 판단 결과값 출력

▶ 출력 결과창(Console)
![if_1066](https://user-images.githubusercontent.com/65608960/107143411-42a47c00-6978-11eb-897a-2cf10fedaef1.JPG)



