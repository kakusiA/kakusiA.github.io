---
layout: post
title: "04-09공부 정리"
date: 2025-04-09-12-34-13
---

## 오늘공부

**요약:** 객체지향 언어는 코드의 재사용성과 유지보수 용이성을 높이기 위해 설계된 프로그래밍 언어로, 객체지향 프로그래밍(OOP)의 핵심 개념에는 캡슐화, 상속, 추상화, 다형성이 포함됩니다. 클래스는 객체를 정의하는 설계도로, 객체는 클래스의 인스턴스이며 속성과 기능을 가지고 있습니다. 객체의 생성과 사용은 변수 선언 후 `new` 키워드를 통해 이루어지며, 메서드는 반복되는 코드의 중복을 줄이고 관리하기 쉽게 만듭니다.

메서드는 선언부와 구현부로 구성되며, 메서드 호출 시 반환값을 가질 수 있습니다. 기본형 매개변수는 값 읽기만...

## 객체지향언어란
- 프로그래밍 언어 + 객체지향(규칙)로 코드의 재사용성을 높고 유지보수에용이하고, 중복코드를 제거하기위해 만들어짐
## 객체지향의 핵심 개념 OOP(object orianted programming)
1. 캡슐화
1. 상속
1. 추상화
1. 다형성
# 객체와 클래스
class → 설계도 object → 제품
## 클래스(class)
### 클래스의 정의
- 객체를 정의해 놓은것
### 클래스의 용도
- 객체를 생성하는데 사용
### 왜필요한가 Why?
- 객체를 중복으로 생성하기위해서 설계도를 작성하는것
## 객체(object)
### 객체의정의
- 실제로 존재하는것,사물또는 개념
### 객체의 용도
- 객체가 가지고있는 기능과 속성에따라 다름
### 객체를 사용한다는것은?
- 객체가 가진 속성과 기능을 사용하는것
### 객체 = 속성(변수) + 기능(메서드)
EX) TV
## 객체와 인스턴스
- 객체 → 모든 인스턴스를 대표하는 일반적인 용어
- 인스턴스 → 특정 클래스로부터 생성된 객체 TV class 로부터 생성된 객체 → TV인스턴스
### 인스턴스화
- class → 인스턴스(객체)
## 하나의 소스파일에 여러클래스 작성
1. public class가있는경우 반드시 소스파일이름과 class이름이 같아야함
```java
public class Hello2{}
class Hello3{}
```
1. public class가 없는 경우 상관X
```java
class hello2{}
class hello3{}
```
1. public class가 2개 이상 존재할수없음
```java
public class hello2{}
//public class hello3{} //2개이상 존재하면안됨
```
1. public class에 이름과 소스파일에 이름이 완전히 동일해야함
## 객체의 생성과 사용
```java
//변수 선언없이는 객체 생성을 할수없음
        TV tv1 = new TV();//변수 선언및 객체 생성
        TV tv2 = new TV();
        tv1.channel = 10; //tv1에 channel변수의 값을 넣어라
        tv2.channel = 20;//변수
        tv1.channelDown();//메서드
        System.out.println(tv1.channel);
        System.out.println(tv2.color);
        System.out.println(tv1.power);
        System.out.println(tv2.channel);
        //tv1객체의 변수를 tv2변수에 넣어라 tv1주소로 변경 기존 tv2참조 주소는 삭제됨
        tv2 = tv1;
        System.out.println(tv2.channel);
```
## class
1. 설계동
1. 클래스 ==  데이터 + 함수
1. 사용자 정의 타입 

### 배열,변수,구조체의 차이점
1. 변수 ⇒ 하나의 데이터를 저장할수있는 공간
1. 배열 ⇒ 같은 종류의 여러 데이터를 하나로 저장할수있는 공간
1. 구조체 ⇒ 서로 관련된 여러 데이터를 하나로 저장할 수 있는 공간
1. 클래스 ⇒ 데이터와 함수의 결합(구조체 + 함수)

### 변수의 종류
1. IV ⇒ 인스턴스 변수
  - 클래스 영억에서 인스턴스가 생성될때 생성
1. CV ⇒ 클래스 변수
  - 클래스영역에서 클래스가 메모리에 올라갈때
1. LV ⇒ 지역변수
  - 변수 선언 문이 수행되었을  때
```java
{
	int iv; //인스턴스 변수
	static int cv;//클래스변수(static변수,공유변수) static + iv
	
	void method(){
		int lv = ;//지역변수
	}
}
```
## 메서드란
1. 문장들을 묶어 놓은것 
1. 값을 받아서 처리하고, 결과를 반환함
```java
    public static void main(String[] args) {
        int []a = new int[10];
        printarr(a);
        System.out.println();
        for (int i = 0; i < 10; i++) {
            a[i] = (int) (Math.random() * 100)+1;
        }
        printarr(a);//메서드 호출

    }
    // void
    static void printarr(int [] numArr){
        for (int i = 0; i < numArr.length; i++) {
            System.out.print(numArr[i] + " ");
        }
    }
    // 반환값이 있음
    int  sum(int x,int y){
        int result = x+y;
        return result;
    }
```
## 메서드의 장점
- 코드의 중복을 줄일 수 있다.
- 코드의 관리가 쉽다.
- 코드를 재사용할 수 있다.
- 코드가 간결해서 이해하기 쉬워진다.
## 메서드의 작성
- 반복적으로 수행되는 여러 문장을 매서드로 작성
- 하나의 매서드는 한가지 기능만 수행하도록 작성
## 메서드 구조
- 메서드 = 선언부+구현부
```java
int add(int a,int b)//선언부 [반환타임 메서드이름 (타입 변수명,타입 변수명)
{ //구현부 메서드 호출시 수행될 코드
	int result = a+b;
	return result;
}
```
## 메서드 호출
```java
//메서드이름(값1,값2,값3);
print99danAll();
int result = add(3,5);
```
## return문
- 실행중인 메서드를 종료하고 호출한 곳으로 되돌아 간다.
```java
    // void
    void printGuGudan(int a){
        System.out.println("Gugudan");
        if(!(2<=a && a<=9)){
            return;//2~9사이가 아닐때 메서드 종료
        }
        for(int i=1;i<=a;i++){
            for(int j=1;j<=9;j++){
                System.out.print(i*j+" ");
            }
            System.out.println();
        }
    }//void 일때는 return 생략가능
    // 반환값이 있음
    int  sum(int x,int y){
        int result = x+y;
        return result;//void가 아니면 반드시 return값을 반환해야함
    }
```
## 호출 스택(call stack)
### 스택(stack)
-  밑이 막힌 상자 위에 차곡차곡 쌓인다. Ex)상자
### 호출스택
- 메서드 수행에 필요한 메모리가 제공되는 공간
- 메서드가 호출되면 호출 스택에 메모리 할당,종료되면 해제
## 기본형 매개변수
### 기본형 매개변수
- 변수의 값을 읽기만 할 수 있다(only read)
```java
class Date{int x;}
class Ex6_6{//기본형 매개변수
    public static void main(String[] args) {
        Date dt = new Date();
        dt.x = 10;
        System.out.println(dt.x);
        change(dt.x);
        System.out.println(dt.x);

    }
    static void change(int x){
        x = 1000;
        System.out.println("x = " +x);
    }
}
```
### 참조형 매개변수
- 변수의 값을 읽고 변경할 수있다.(Read & Write)
```java
class Date2{int x;}
class Ex6_7{//참조 매개변수
    public static void main(String[] args) {
        Date2 dt = new Date2();
        dt.x = 10;
        System.out.println(dt.x);
        change2(dt.x);
        System.out.println();
        System.out.println(dt.x);
    }
    static void change(Date2 dt){//dt의 참조변수의 주소를 들고옴
        dt.x = 1000;
        System.out.printf("x = " +dt.x);
    }
}
```
## Static메서드 와 인스턴스 메서드
```java
class a{
	long x,y;
	
	long add(){//인스턴스 메서드
		return x+y;
		}
		
		static long add(long x,long y){//static메서드
			return x+y;
		}
	}
```
### 인스턴스메서드
- 인스턴스 생성후 참조변수.메서드이름()으로 호출
- 인스턴스 멤버와 관련된 작업을 하는 메서드
- 메서드 내에서 인스턴스 변수(iv) 사용가능
### static메서드
- 객체 생성없이 클래스이름.메서드이름()으로 호출
- 인스턴스 멤버와 관련없는 작업을 하는 메서드ㄴ
- 메서드 내에서 인스턴스 변수 사용불가능 
```java
class TestClass2{
    int a;
    static int b;
    
    void print01(){
        System.out.println("a = " + a);//인스턴스 메서드는 iv 사용가능
        System.out.println("b = " + b);
    }
    static void print02(){
//        System.out.println(a);//iv여서 오류발생
        System.out.println(b);
    }
}
class TestClass3{//static메서드는 im도 사용불가
    int a;
    void print03(){}
    static void print05(){}
    void print04(){
        print03();//인스턴스
        print05();//static
    }
    static void print06(){
//        print03();//인스턴스 메서드 불가
        print05();
    }
}
```
### 인스턴스 메서드와 static메서드 사용여부
- Iv를 사용하지 않을때 static를 붙인다.
## Overloading 
- 하나의 클래스안에 같은 이름의 메서드가 여러개 정의되어있는것 ⇒ 과적합
```java
void println()
void println(boolean x)
void println(char x)
void println(char[] x)
//....
```
### 오버로딩 성립조건
1. 메서드 이름이 같아야한다.
1. 매개변수의 개수 또는 타입이 달라야한다.
1. 반환 타입은 영향없다.
```java
    int asd(int a, int b){return a +b;}
//    int asd(int x, int y){return x+y;}//중복 정의
//    long asd(int a, int b){return (long)(a +b);}//중복 정의 반환 타입이 같아도 중복정의이다.
    long asd(int a, long b){return a +b;}
    long asd(long a, int b){return a +b;}
```
### 오버로딩의 올바른예
- 매개변수는 다르지만 같은 의미의 기능수행
## 생성자(constructor)
- 인스턴스가 생성될때 마다 호출되는 인스턴스 초기화 메서드
```java
class Car{
    Car(){//생성자

    }
    Car(String color){

    }
}
```
### 생성자 규칙
- 이름이 클래스 이름과 같아야한다.
- 리턴값이 없다.
- 모든 클래스는 반드시 생성자를 가져야 한다. ⇒ 없으면 컴파일러가 자동으로 생성함
### 기본 생성자(defult constructor)
- 매개변수가 없는 생성자
- 생성자가 하나도 없을때만 컴파일러가 자동 추가
```java
class Date_1{
    int value;
}
class Date_2{
    int value;
    Date_2(int x){
        value = x;
    }
}
class Dat1{
    public static void main(String[] args) {
        Date_1 d1 = new Date_1();
//        Date_2 d2 = new Date_2();// 컴파일러 에러 발생
    }
```
### 생성자this()
- 생성자에서 다른 생성자를 호출 할떄 사용
- 다른 생성자 호출시 첫 줄에서만 사용가능
```java
class Date12{
    int hour;
    int minute;
    int second;
    Date12(){
        this(0,0,0);//생성자 this()//Date12()대신 사용
    }
    Date12(int a, int b, int c){
        hour = a;
        minute = b;
        second = c;
    }
}
```
## 참조 변수 this
- 인스턴스 자신을 가리키는 참조변수
- 인스턴스 (생성자 포함)에서 사용가능
- 지역변수와 인스턴스 변수를  구별할 때 사용
- 클래스 메서드에서는 사용 불가능
```java
    Date12(int hour, int minute, int second){
        this.hour = hour;//this.hour -> IV hour -> LV
        this.minute = minute;//this 참조변수의 주소가 들어가있음 객체자신을 지칭함
        this.second = second;
    }
```

