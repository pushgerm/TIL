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


## 참고
    * .isalpha() : 알파벳인지 아닌지
    *     s="Charlie"
          print(s[1:4])
            # har index 1부터 4 앞 까지
