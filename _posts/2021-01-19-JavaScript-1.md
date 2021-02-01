---
layout: post
title: "JavaScript - 1"
date: 2021-01-19
study : [HTML+CSS+JavaScript]
comments: true
---

### * JavaScript

- JavaScript는 HTML 내용을 변경할 수 있다
##### - 자바스크립트 기본문법

```
  1. 변수
   - 변하는 수(값)
   - 임시로 값을 담는 공간(그릇)
   - $, _ 기호를 변수이름 앞에 붙여서 사용가능하다
   EX) var a = 5; ( = : 대입연산자 ) : ES5버전 까지의 방식

       let a = 5; : ES6버전
       const b = 5; : ES6버전 ( 상수 : 변하지 않는 수 )

   - 변수 스코프(적용 범위)
    : 전역 범위 - 프로그래밍 전체 영역에 선언되는 변수의 범위
    : 지역 범위 - 프로그래밍 영역에서 작은 그룹 영역에 선언되는 변수의 범위
      1. 함수 범위 : 함수 내부 영역에 선언되는 변수의 범위
      2. 블럭 범위 : if, for 같은 구문 블럭 내부 영역에 선언되는 변수의 범위

```
![js문법](js문법.JPG)
```
   2. 연산자
    - 산술 연산자
      - ** : 제곱 연산자(ES2016버전부터)
      - ++, -- : 증감 연산
      -  EX) a = 1;
          a += 2; => a = 1,3, 5, 7, 9 ...
          a -= 2; => a = 1, -1, -3, -5 ...
          ** a += 1; => a = 1, 2, 3, 4, 5 ...
          ** a -= 1; => a = 1, 0, -1, -2 ...
              : 프로그래밍 언어에서 카운트의 개념으로 사용
              a++ ( a += 1 )
              a-- ( a -= 1 )
        
    - 할당 연산자
      - = : 할당 연산자(변수에 값을 넣어줌)
      - +=, -=, *=, /= : 산술연산자  + 할당연산자
        -> 산술 연산을 한 후에 결과를 변수에 재 할당 연산
    - 문자열 연산
      - 문자(1개) : character, 문자열(여러개) : string
      - 문자1 + 문자2 : 문자1문자2
      - 문자데이터 : '' 로 묶어서 표현
      - 숫자 +문자 = 숫자문자(연결됨)
      EX)'abc' + 'qwe' = 'abcqwe'
    - 비교 연산자
      - 비교 연산의 결과값은 참 또는 거짓 중 하나
      - 결과 표현 방법 : 1(참) / 0(거짓) , True/false, 참/거짓

          a == b (같다, 값)
          a === b (같다, 값 & 종류(type))
          a != b (다르다, 값)
          a !== b (다르다), 값 & 종류(type))
          EX1) 5 == '5' : true
          EX2) 5 === '5' : false ★ -> 사용권장
          EX3) 5 != '5' : false
          EX4) 5 !== '5' : true ★ -> 사용권장
```          
  
![boolean](boolean.JPG)
```    
    - 논리연산자
      - &&(AND), ||(OR), !(NOT)
      - AND, OR 논리 연산 : 비교 연산자들을 연결
        - AND : 연결된 비교 연산 결과가 모두 참일 때 최종 결과가 참이 된다
        - OR : 연결된 비교 연산 결과 중 하나만 참이여도 최종 결과가 참이 된다
      - NOT 논리 연산 : 연산 결과를 반대로 만들어 준다
      EX1) 5>3 && 10>5 => true $$ true => true
      EX2) 5<3 && 10>5 => false && true => false
      EX3) 5<3 || 10>5 => false || true => true
      EX4) !(5<3 || 10>5) => !(false || true) => !(true) => false

```
```
  3. 분기문(조건문)
    - 조건식을 사용해서 조건 비교 연산 후에 결과가 참 또는 거짓일때 각각 다른 실행을 할 수 있도록 분기해주는 구문
    - 조건 비교 : ~이면(하면)

    ☆ if구문 예제
    EX) 현재 시간이 저녁 6시 이전이면 '좋은하루' 문구를 표시한다.
    -> 1. : 조건식 - time < 18
    -> 2. : if(time < 18) {
       console.log('좋은하루'); // 조건식의 결과가 참일때 실행
      }
    EX) 현재 시간이 저녁 6시 이전이면 '좋은하루' 문구를 표시하고, 그렇지 않으면 '좋은저녁' 문구를 표시한다
        -> if(time<18){
          console.log('좋은하루');
        } else{
          console.log('좋은저녁');
        }
    EX) 현재 시간이 점심 12시 이전이면 '좋은아침' 문구를 표시하고, 저녁 6시 이후이면 '좋은오후' 문구를 표시하고, 그렇지 않으면 '좋은저녁' 문구를 표시한다
        -> if(time<12) {
          console.log('좋은아침');
        }  else if(time<18) {
          console.log('좋은오후');
        } else {
          console.log('좋은저녁');
        }

    - switch 구문
      - 조건식이 아닌 표현식(수식)을 사용
      - 표현식 결과값 수에 따라 여러 분기 실행을 할 수 있다

      ☆ switch 구문 예제
          EX) 요일코드(0~6)에 따른 요일 이름 표시
          -> switch(date){
            case 0:
              console.log('sun');
              break; //실행 정지          
           case 1:
              console.log('mon');
              break;
           case 2:
              console.log('tue');
              break;
           case 3:
              console.log('wed');
              break;
           case 4:
              console.log('thu');
              break;
           case 5:
              console.log('fri');
              break;
           case 6:
              console.log('sat');
              break;
            }
```
```
    4. 조건
      - 비교 연산자를 사용해서 만들수 있는 비교식(조건식)
      - 결과값은 true/false의 boolean 데이터 형식

    5. 반복문
      - 구문(코드) 블럭을 반복 실행

    * for : 반복횟수를 정해서 정해진 횟수만큼만 반복하는것
   -> for(구문1; 구문2; 구문3) {

      }
  => EX) for(i=0; i<10; i++){
         반복 실행 코드
        }
        - i=0 : 한번 실행
        - i<10 : 반복 실행과 연관된 조건식
        - i++ : 매 반복 실행시 실행

        => 1) i=0 실행 : i값은 0으로 할당
           2) 실행코드 실행(1)

           3) i++실행 : i값 1 증가된 값으로 할당(1, 2, 3, 4, 5, 6, 7, 8, 9, 10 )
           4) i<10 조건 비교
           5) 실행코드 실행                    (2, 3, 4, 5, 6, 7, 8, 9, 10 )

           => i<10 조건이 참인동안 3),4),5) 반복
           => 10번 반복 실행

           1. for(i=1; i<=10; i++){}
           2. for(i=0; i<=9; i++){}  
           3. for(i=0; i<10; i++){} : index number, 데이터 개수 고려

      * 구문1 : 코드블록이 실해오디기 전 "한번"실행
      * 구문2 : 코드블록이 실해오디기 위한 조건을 정의
      * 구문3 : 코드블록이 실행된 후 "매번"" 실행

    * while loop : 조건식의 결과가 참인 동안 반복

   -> while(조건식){
       실행코드
     }

     EX) 조건부 무한루프

        while(true){

          실행코드

          if(조건식) {
            break;
          }

        }

      //특정 문자가 입력될때까지 반복
    =>  let exit = 'n';
        while(exit === 'n'){

          실행코드

          종료하시겠습니까?(y/n) // 사용자에게 키보드로 입력을 받음

      }
```
```
    6. 함수
      - 특정 작업을 수행하도록 설계된 코드 블록
      : 코드 재사용이 가능하다, 다른 인수로 동일한 코드를 여러번 사용하여 다른 결과를 생성 할 수 있다
       Ex)
      - 함수 정의 : function functionName(){

                  }

      - 함수 호출 : functionName()

      * 매개변수(Parameter) : 외부의 값을 입력받아 사용

       EX)
       function sum(a, b){

        console.log(a+=b);

      }
        sum(5,3); => 출력 값 : 8

        sum(2,7); => 출력 값 : 9

     - return : 1. 반환값을 계산한다.
                2. 리턴문에 도달하면 함수 실행이 중지된다
       EX)
       function equalNumber(n){ // 함수생성
          if(n == 20){ // n이 20과 같으면
            return true; // 같으면 true 리턴
          }else {
            return false; // 다르면 false 리턴
          }
        }
        if(equalNumber(20)){ // 20 ->매개변수
          console.log('equal');

        }else {
         console.log('not equal');
        }
        => 출력값 : "equal"
```
```
    7. 배열(리스트)
      - 여러개의 데이터를 하나의 변수 이름으로 저장하는 변수 -> 데이터가 하나의 그룹으로 묶여서 나열되어있다
      - 만드는 방법 : 1. 배열 리터럴(Array Literal) => 변수 배열이름 = [item1,item2,item3 ...]; -> Ex) let cars = ["ming","ki"]; -> "ming","ki" :매개변수
                     2. 예약어 사용 => 변수 배열이름 = new Array(item1,item2...); => let cars = new Array("ming","ki"); -> "ming","ki" :매개변수
                     * Array : 객체,클래스 -> 대문자로 시작
      - 베열변수 변경 : 인덱스 번호를 사용하여 데이터 접근 -> EX) let cars = ["ming","ki"]; -> car[1] = "ji"; => var cars = ["ming","ji"];
                     * 인덱스 번호는 0부터 시작한다

      => let array = [1,2,3];
         let array = new Array(1,2,3);
         array[0] : 0번 인덱스에 있는 데이터 접근
```
```
    8. 객체
       - property와 method의 집합체(container)
       - .을 사용해 포함된 객체와 원소 이름을 연결해서 사용
       - 객체를 생성하게 되면 기본적인 Property와 Method가 자동으로 객체에 포함된다

        : Object(property,method) -> 객체 안에 속성과 기능이 포함된다
        EX)
        - 객체(Object) => 자동차 자체(집합체) -> 제작된 상품
        - 속성(Property) => 정적인 성격(형태) -> (자동차의)이름,무게,모델,색,차의길이 등..
        - 기능(Method) => 정의된 동작 -> 출발,감속,좌회전,우회전 등..

         EX) let car = { type : "Fiat", model : "500", color : "white"};
            -> 객체 안에 데이터를 넣어줄 때에는 name:value(key:value) 으로 쓴다

        - 객체 사용방법 : objectName.propertyName / objectName.methodName           
        * String,Number,Boolean을 객체로 선언하지 않느게 좋다 => 코드가 복잡해지고 실행속도가 느려진다
```
```
    9. 클래스
        - 객체를 만들수 있게 하는 설계도
        - property,method로 구성

        EX) class CarInfo{  //단어의 첫글자는 꼭 대문자 여야 한다

            constructor(name, year){ // constructor 함수를 꼭 써야한다 -> 생성자 함수 : 변수를 초기화 한다
                this.name = name; // 클래스 멤버변수(객체 프로퍼티) : this 키워드 사용
                this.year = year;

              }
                age(){ // 클래스 메소드 선언
                return (2021 - this.year);
              }

            }
            let volvo = new CarInfo('volvo', 2018); // new 사용하여 새로운 객체 생성
            let benz = new CarInfo('benz', 2020);
            let sonata = new CarInfo('sonata', 2021);

            console.log(volvo);
            => 출력: Object {
                      name: "volvo",
                      year: 2018
                    }

            console.log(benz);
            => 출력: Object {
                      name: "benz",
                      year: 2020
                    }

            console.log(sonata);
            => 출력: Object {
                      name: "sonata",
                      year: 2021
                    }
         * <Class Method>
            console.log(volvo.age());
            => 출력 : 3
            console.log(benz.age());
            => 출력 : 1
            console.log(sonata.age());
            => 출력 : 0



    10.이벤트  
        - 프로그래밍 방식: 동기/비동기 방식
        - 자바스크립드 : 비동기 방식
        - 비동기 방식 : 이벤트 사용
        - 이벤트 : 동작이 시작될 수 있게 하는 신호(알림)
        - 이벤트의 종류 : 클릭, 키보드입력, 스크롤 등
        - 이벤트 리스닝/핸들링
          : 리스닝 - 이벤트가 발생했는지 감지
          : 핸들링 - 해당 이벤트가 발생되었을 때 필요한 동작 실행

      EX) document.querySelector('.button').addEventListener('click', function(){
            alert('버튼을 클릭하였습니다.'); // 클릭시 알림창 뜨게 하는것
          });

        - 이벤트 리스너 -> .addEventListener('click'
        - 이벤트 핸들링 ->                                 function(){
                          alert('버튼을 클릭하였습니다.');


```
