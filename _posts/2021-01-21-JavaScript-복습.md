---
layout: post
title: "JavaScript - 복습"
date: 2021-01-21
study : [HTML+CSS+JavaScript]
comments: true
---

### * 배열

```
- 배열 : 인덱스를 이용해 n개의 데이터를 하나의 변수에 담고있는 형태 -> 많은 데이터를 하나의 변수에 담아 관리한다

     -> 변수 =  데이터 | 데이터 | 데이터  | 데이터  | ... | 데이터
              index:0 |index:1| index:2 |index:3 | ... | index:n

        * 인덱스는 0부터 시작한다
        * 데이터 : 숫자,문자열,불리언,함수,객체,undifined(선언만 하고 초기화 되지않은것)

  - 배열 객체 생성 방법
      - 1. let letArr1 = new Array(); => 크기를 지정하지 않은 배열 객체 생성
        => 배열안에 데이터 넣는 방법 : letArr1[0] = "A"; -> letArr1 배열 인덱스 0 자리에 문자열 A를 데이터로 넣는다
        2. let letArr2 = new Array(5); => 5개(0~4)의 인덱스를 가진 배열 객체 생성
        3. let letArr3 = new Array(123, "ABC", ture); => 배열생성과 데이터 저장을 동시에
        4. let letarr4 = [123, "ABC", true, {}]; => 배열생성과 데이터 저장을 동시에 => new 사용하지 않고 대가로 [] 사용

  - 배열 크기(길이) : length
    EX) let letArr3 = new Array(123, "ABC", ture);
        console.log(letArr3.length);
        => 출력 : 3

  ★ index : 0 1 2
     length : 3

  - 배열 메소드
      - 1. indexOf() : 인덱스 검색 -> 내가원하는 자료데이터가 어느 인덱스에 있는지 알려준다
                    => 중복된 인덱스가 있을경우 가장 처음에 있는 인덱스를 찾아준다
        * lastIndexOf() : 중복된 인덱스가 있을경우 가장 뒤에 있는 인덱스를 찾아준다     

          EX1) let letArr3 = new Array(123, "ABC", ture, 123);
                console.log(letArr3.indexOF(123));
                => 출력 : 0
          EX1) let letArr3 = new Array(123, "ABC", ture, 123);
                console.log(letArr3.lastIndexOF(123));
                => 출력 : 3
          ★ 찾는 데이터가 배열에 없을경우 -1이 출력된다
      - 2. concat() : 서로다른 두개의 데이터를 연결해준다
            EX1) let letArr3 = new Array(123, "ABC", ture, 123);
                 let letArr4 = new Array(123, "ABC");
                 let letArr5 = letArr3.concat(letArr4);
                  console.log(letArr5);
                  => 출력 : 123, "ABC", ture, 123, 123, "ABC"
      - 3. join() : 배열 데이터를 문자열로 반환
      - 4. sort() : 배열 정렬 : 알파벳 순서대로 배열을 정렬한다
                => sort 메소드로 정렬하고 난 후 해당데이터는 정렬된 상태로 저장된다
      - 5. reverse() : 배열 순서 반전 : 알파벳 순서가 아닌 해당 데이터 순서자체를 반대로 반전시킨다
      - 6. push() : 데이터 추가 : 데이터를 추가 한다
           EX) let letPush = new Array(123, "ABC");
               let letPush = letPush.push(222, "AAA");
                console.log(letPush);
                => 출력 : 123, "ABC", 222, "AAA"
      - 7. shift(),pop() : 첫번째,마지막 인덱스의 데이터 삭제
         * unshift() : 첫번째 인덱스에 데이터 추가
         * length() : 배열의 데이터 갯수에 맞춰 인덱스에 데이터추가
            EX) letArrShift = new Array(1, 2, 3); => letArrShift의 length는 3 index는 2
                letArrShift[letArrShift.length] = "가나다"; =>index 3자리에 데이터 추가
                console.log(letArrShift)
                => 출력 : 1, 2, 3, "가나다"

```

### * 함수
```
- 함수 : 특정한 기능(들)을 모아 놓고 필요에 따라서 명령하면 답하는 기계
   - 1. 명시(선언)적 함수 : 함수 이름이 있다
        => 형태 : function 함수이름() {
                   실행문;
                  }
        => 호출 : 함수이름();

   - 2. 익명 함수 : 함수 이름이 없다 -> 이름이 없기 때문에 변수에 담아서 사용하기도 한다
        => 형태 : let 변수이름 = function() {
                    실행문;
                 }
        => 호출 : 변수이름();

- 명시적 함수와 익명함수의 실행순서 : 명시(선언)적 함수가 먼저 실행된다
   - 1. 명시(선언)적 함수 : html 문서가 실행될때 가장먼저 실행된다
   - 2. 익명함수 : html문서가 실행될때 위에서 부터 순차적으로 실행된다

   EX) fun1();  // 정상 실행 -> 명시적 함수가 html 문서 실행될때 바로 실행 되기 때문에 정상 실행
       fun2();  // 오류 발생 ->함수가 생성되기 전에 호출했기 때문에 오류 발생

       function fun1() {  // 명시(선언)적 함수 생성
          console.log(1);
       }

       let fun2 = function() { // 익명 함수 생성
         console.log(2);
       }

       fun2(); // 정상 실행

- 매개변수와 리턴(반환)값
    - 매개변수 : 동작에 필요한 데이터를 전달 => 함수 호출시 매개변수는 있을수도, 없을수도 있다
    - 반환(리턴)값 : 함수실행 결과값을 호출부에 전달 => 반환값은 있을수도, 없을수도 있다
    EX) 엄마가 콩나물 사오라고 돈을준 상황
        - 돈 : 매개변수
        - 반환(리턴)값 : 콩나물

=> EX) function funName(x, y) {  // 매개변수 x, y

       let result = x * y ;      // 지역변수

       return result;           // 반환값 result
      }
      let letResult = 0;        // 전역변수

      letResult = funName(2,4);
      console.log(letResult);
      => 출력 : 8

- arguments : 매개변수를 이용한 배열 객체
    => function 함수이름(매개변수1, 매개변수2, ... 매개변수n){
        arguments = [매개변수1, 매개변수2, ... 매개변수n)]  //내가 넣은 매개변수 데이터를 배열로 관리하고 있는 객체
        }

```
### * 객체
```
- 객체 : 속성과 기능을 가지고 있는 프로그램 덩어리
    EX) {계산기 객체} - 속성 : 숫자 / 기능 : 4칙연산
        {제과점 객체} - 속성 : 밀가루,생크림 / 기능 : 빵굽기,케익만들기
* 객체지향 프로그램 : 모든기능을 객체로 만들어 객채들을 연결해 프로그램을 만드는 것

- 객체 생성 : let 객체변수명 = {  // {} 을 이용해서 객체 생성
             name1 : value1,    // name : value OR key : value 를 이용
             name2 : value2,    // ',' 를 이용해서 구분
             ...
             };                 // {} 을 이용해서 객체 생성

- 속성과 메소드(함수)
   - 속성 : 값
   - 메서드 : 객체 안에 들어가있는 함수 -> 기능
   EX) let objCar = {
       width : "3m",  // "3m" -> 속성
       energy : 100,
       speed : function(power) { // function(power) -> 메소드
          return this.energy * power;  // this.energy -> objCar객체 안에 있는 energy 속성을 가르킨다.
        }
     };
     console.log(objCar.speed(2));
     => 출력 : 200
 ★ this : 객체 내부를 가리키는 키워드 => 객체 내부의 속성을 이용할 대 반듯이 명시해 줘야 한다.

 - 객체 접근 : '.' 을 이용한 접근 => objCar.speed

 - 객체를 만드는 다양한 방법
    - 1. 기본적인 객체 생성 : {} 이용하는 방법
       : let objCar = {
           width : "3m",  
           energy : 100,
           speed : function(power) {
              return this.energy * power;  
            }
         };

    - 2. 함수를 이용한 객체 생성
       : function creatCar(name, color, speed) { // 함수 생성 (받을 매개변수 입력)
          let carObj = {  // 객체 생성
            name : name,
            color : color,
            speed : speed,
            run : function() {
              return this.speed
            }
         };
         return carObj; // 객체 리턴
       };
       let sorento = createCar("sorento", "grey", 220); // sorento 라는 변수 안에 carObj 객체가 들어간다
       console.log(sorento.run());
       => 출력 : 220

    - 3. 생성자를 이용한 객체 생성
      * 생성자 함수는 첫글자를 대문자로 쓴다 (가시성을 높이기위해)
       : function Airplane(name, color, speed) { // 함수 생성 (받을 매개변수 입력)
          this.name = name;                      
          this.color = color;
          this.speed = speed;
          this.fly = function() {
            return this.speed
          };
       };
       let boeing747 = new Airplane("boeing747", "blue", "600km/h")  // new -> 객체를 새로 생성하는 키워드
       console.log(boeing747.color);
       => 출력 : blue

 - prototype(프로토타입) : 공유된 공간 -> 메서드를 prototype이란 공유된 공간에 하나만 생성해서 사용한다
                      => 메모리상 자원낭비를 줄일 수 있다
      : 기본타입 => function Scoring(player, scoreFirst, scoreSecond) {
                    this.player = player;
                    this.scoreFirst = scoreFirst;
                    this.scoreSecond = scoreSecond
                    this.getTotal = function() {
                      return this.scoreFirst + this.scoreSecond;
                    };
                    this.getAverage = function() {
                      return (this.getTotal() / 2).toRized(2);  // tFixed(2) -> XX.12 까지 표현
                    };
                  };

                  let player1 = new Scoring("홍길동", 99, 90);
                  console.log(player1.player + "의 총첨 : " + player1.getTotal());
                  console.log(player1.player + "의 평균 : " + player1.getAverage());

                  let player2 = new Scoring("메니", 80, 90);
                  console.log(player2.player + "의 총첨 : " + player2.getTotal());
                  console.log(player2.player + "의 평균 : " + player2.getAverage());

      : 프로토타입 => function Scoring(player, scoreFirst, scoreSecond) {
                      this.player = player;
                      this.scoreFirst = scoreFirst;
                      this.scoreSecond = scoreSecond

                    };

                    Scoring.prototype.getTotal = function() {   // prototype 공간생성
                      return this.scoreFirst + this.scoreSecond;
                    };
                    Scoring.prototype.getAverage = function() { // prototype 공간생성
                      return (this.getTotal() / 2).toRized(2);
                    };


                    let player1 = new Scoring("홍길동", 99, 90);
                    console.log(player1.player + "의 총첨 : " + player1.getTotal());
                    console.log(player1.player + "의 평균 : " + player1.getAverage());

                    let player2 = new Scoring("메니", 80, 90);
                    console.log(player2.player + "의 총첨 : " + player2.getTotal());
                    console.log(player2.player + "의 평균 : " + player2.getAverage());

```
