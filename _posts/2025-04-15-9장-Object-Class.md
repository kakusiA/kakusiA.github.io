---
layout: post
title: "9장 Object Class"
date: 2025-04-15 16:34:24
---

## 9장 Object Class

**요약:** 객체지향 공부

# Object class
  - 모든 클래스의 최고 조상, 오직 11개의 메서드만을 가지고 있음
  - notify(),wait() 등은 쓰레드와 관련된 메서드
## class Classs
  - 클래스의 정보를 담기위한 클래스
  - 객체를 생성,객체 정보를 얻을수있음
  ## Reflection API
## equals(Object obj)
  - 객체 자신과 주어진 객체를 비교한다. 같으면 true 다르면 false.
  - Object 클래스의 equals()는 객체의 주소를 비교(참조변수 값 비교)
### 기본

```java
package ch.ch09;

public class ch09_1 {
    public static void main(String[] args) {
        Value va1 = new Value(10);
        Value va2 = new Value(10);
        System.out.println(va1.equals(va2));//참조 변수의 주소 값이 달라서 false
    }
}

class Value{
    int val;
    Value(int val){
        this.val =val;
    }

}
```

### 값비교로 수정

```java
public class ch09_1 {
    public static void main(String[] args) {
        Value va1 = new Value(10);
        Value va2 = new Value(10);
        System.out.println(va1.equals(va2));//참조 변수의 주소 값이 달라서 false
    }
}

class Value{
    int val;
    Value(int val){
        this.val =val;
    }
    public boolean equals(Object obj) {
        if (obj instanceof Value) {
            return this.val == ((Value) obj).val;//값비교
        }
        else return false; // false로해도 상관없음
    }
}
```

## hashCode()
  - 객체의 해시 코드를 반환하는 메서드
  - Object클래스의 hashCode()는 객체의 주소를 int로 변환해서 반환
  - equals를 오버라이딩하면 hashCode도 오버라이딩 필수 
### 기본

```java
class Hashs{
    public static void main(String[] args) {
        Value v1 = new Value(10);
        Value v2 = new Value(10);
        System.out.println(v1.equals(v2));
        System.out.println(v1.hashCode());
        System.out.println(v2.hashCode());
    }
}
```

### hash 오버라이딩

```java
class Value{
    int val;
    Value(int val){
        this.val =val;
    }
    public int hashCode(){//해쉬코드 오버라이딩
        return Objects.hash(val);//hash -> 가변인자
    }
    public boolean equals(Object obj) {
        if (obj instanceof Value) {
            return this.val == ((Value) obj).val;
        }
        else return false; // false로해도 상관없음
    }
}
```

### Objects class ⇒ 객체와 관련된 유용한 메서드를 제공하는 유틸 클래스
## String class
  - String class = 데이터(char[]) + 메서드
  - 내용을 변경할 수 업는 불변 클래스
### String class method s
1. String(String s)
1. String(char[] value)
1. String(StringBuffer buf)
1. char charAt(int index)
1. int compareTo(String str)
1. String concat(String str)
1. boolean contains(CharSequence s) → CharSequence 문자열 형식의 인터페이스 관계
1. boolean endsWith(String suffix)
1. boolean equals(Object obj)
1. bool equalsIgnoreCase(String str)
1. int indexOf(int ch)
1. …

```java
class Str1{
    public static void main(String[] args) {
        String str = new String("abc");//String생성
        System.out.println(str);
        char [] ch ={ 'a', 'b','d'};
        String str1 = new String(ch);//char -> String으로 변경
        System.out.println(str1);
        StringBuffer buf = new StringBuffer("1234");
        String str2 = new String(buf);//버퍼 -> String변환
        System.out.println(str2);
        char ch1 = str.charAt(1);//index 1값 반환
        System.out.println(ch1);
        int i = str.compareTo(str1);//사전에딸라  == 0, > 1, < -1반환
        System.out.println(i);
        String str3 = str.concat(str2);//합치기
        System.out.println(str3);
        boolean bol = str1.contains("bd");//특정 문자열있는지 확인
        System.out.println(bol);
        boolean bol1 = str2.endsWith("34");//로 끝나는 문자열 확인
        System.out.println(bol1);
        String str4 = "abd";
        boolean bol2 = str1.equals(str4);//비교
        System.out.println(bol2);
        String str5 = "ABD";
        boolean bol3 = str4.equalsIgnoreCase(str5);//대소문자 없이 비교
        System.out.println(bol3);
        int i2 = str4.indexOf('b');//문자열에 b의 인덱스값 반환
        System.out.println(i2);
        int i3 = str3.length();//문자열의 길이
        System.out.println(i3);
        String animals = "dog,cat,bear";
        String[] arr = animals.split(",");//정규식으로 짜름
        System.out.println(Arrays.toString(arr));
        boolean bol4 = animals.startsWith("dog");//해당문자로 시작하는지
        System.out.println(bol4);
        String str6 = animals.substring(4,7);//4에서7까지 문자가져오기
        System.out.println(str6);
        String str7 = "ABCD";
        String str8 = str7.toLowerCase();//소문자 변환
        System.out.println(str8);
        String str9 = str8.toUpperCase();//대문자변환
        System.out.println(str9);
        String str10 = "     apple banana       ";
        String str11 = str10.trim();//앞뒤공백제거
        System.out.println(str10);
        System.out.println(str11);
        int a = 10;
        String b = String.valueOf(a);//형변환
        System.out.println(b);
    }
}
```

## 래퍼 클래스(wrapper class)
8개의 기본형을 객체로 다뤄야할때 사용하는 클래스
## 오토방식 & 언박싱
  - 오토박싱(Auto boxing) : int → Integer
  - 언박싱(Unboxing): Integer → int 
  - 둘다 자동으로해줌

```javascript
    public static void main(String[] args) {
        ArrayList<Integer> list =new ArrayList<Integer>();
        list.add(10); //자동으로 컴파일이
        list.add(new Integer(10));//으로 병경으로해줌
        
        int i = list.get(0);//도 자동으로
        int i1 = list.get(0).intValue();//로 자동으로 변경해줌
        
    }
```
