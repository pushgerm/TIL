# python
    * C++을 했기 때문에  새로운, 다른 내용만 기록

## 주석
* '#': 한 줄만 주석처리
* ' """ ' : 시작과 끝을 지정해 해당 지역 주석처리

## 연산
* a**b : a의 b승

## 변수
* 파이썬은 C++과 다르게 데이터 타입의 정의를 해주지 않는다.

## 문자열(string)
* 문자열의 문자 참조 방법
    *     c="cats"[0]
* string methods
    * len() : 문자열의 길이
        *     len("string")
    * lower() : 일시적으로 문자열의 대문자를 소문자로 바꿈
        *    string.lower()
    * upper() : 일시적으로 문자열의 소문자를 대문자로 바꿈
        *    string.upper()
    * str() : 비문자열을 문자열로 바꿈
        *    str(2) # 2 -> "2"
    * \+ : 문자열들을 이어 붙인다(문자열 끼리만 가능, 자료형이 문자열이 아니면 str() 이용)
    *      print("Let's not go to %s. It is a silly %s." % (string_1, string_2))

## The datetime Library
*     from datetime import datetime
      time = datetime.now()
      print(time)
      print("%s/%s/%s %s:%s:%s" %(time.year, time.month, time.day, time.hour, time.minute, time.second))
      """ 
      2017-11-04 10:24:50.430585
      2017/11/4 19:34:17
      """

## boolean
 * not -> and -> or

## Conditional Statement
*     if a>0:
            print("1")
          elif a<0:
            print("-1")
          elif a==0:
            print("0")

## Input
*     a = raw_input("Enter a word : ")
          # "Enter a word : "를 출력하고 입력을 받아 a에 저장

## 함수
*     def fName(parameter):
      #괄호 없이 열 맞춰서
      return para

### import
* C++에서 헤더를 포함하듯 import를 통해 함수 집합을 불러올 수 있다. 이 중에서 원하는 함수만 불러오려면 from [module] import [function]으로 불러온다. 모든 변수 및 함수를 import 하려면 from [module] import * 을 해준다.  
모듈의 함수이름과 같은 함수가 이미 정의되어 있을 때 import [module]은 안전하다. func()와 module.func()가 있기 때문이다. 하지만 from [module] import * 는 이름이 겹치게 된다.
* module 열어보기
    *     import module
          a=dir(module)
          print(a)


## 참고
* .isalpha() : 알파벳인지 아닌지
*     s="Charlie"
      print(s[1:4])
      # har index 1부터 4 앞 까지
* max(1,2,3....) : 매개변수중 가장 큰 값을 반환
* min(1, 2, ....) : 매개변수중 가장 작은 값을 반환
* abs(num) : 절댓값 반환
* type(t) : 자료형 반환

## 배열
* .append() 를 통해 배열 확장 가능.
* .insert(index, "  ") : 배열의 index위치에 삽입
* .index(" ") : ( ) 에 일치하는 index 반환
* for i in List : List에 있는 값이 하나씩 i에 넣어져 실행됨
* .sort() : 배열을 오름차순으로 정렬
* arr=['key1' : 1, 'key2' : 2] : 배열에 키값을 줘 값을 정할 수 있음. index값에 key값을 입력하면 대응 값을 반환
* del arr['key'] : 해당 키 pair 삭제
* .remove('  ') : 해당 원소 삭제
