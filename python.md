# Python

## 자료형
* 숫자형
    * 숫자형은 어떻게 만들고 사용할까?

        1. 정수형  
            a = 123  
            a = -178  
            a = 0  
    
        2. 실수형  
            a = 1.2  
            a = -3.45  
            a = 4.24E10  
            a = 4.24e-10  

        3. 8진수  
            a = 0o177  

        4. 16진수  
            a = 0x8ff  
            b = 0xABC

    * 숫자형을 활용하기 위한 연산자
        1. 사직연산 : + - * / 그대로 사용하면 된다  

        2. ** : 제곱을 나타냄.  
            3 ** 4 = 81  
            2 ** 3 = 8  
        3. % : 나눗셈 후 나머지를 반환하는 연산자  
            3%7 = 3  
            7%3 = 1

        4. // : 나눗셈 후 소수점 아랫자리를 버리는 연산자  
            7 // 4 = 1
            -7 // 4 = -2 (결과값보다 작은 정수 중, 가장 큰 정수를 리턴한다.)


* 문자열
    * 문자열은 어떻게 만들고 사용할까
        
        1. 큰따옴표로 양쪽 둘러싸기  
        "Hello word"  
        2. 작은따옴표로 양쪽 둘러싸기  
        'Hello word'
        3. 큰따옴표 3개를 연속으로 써서 둘러싸기  
        """Hello world"""
        4. 작은 따옴표 3개를 연속으로 써서 양쪽 둘러싸기  
        '''Hello world'''  
    * 문자열 안에 작은따옴표를 포함시키고 싶을 때  
        1. 큰따옴표로 문자열을 감싼다.  
        "I'm yours"  
        큰따옴표를 포함시키고 싶다면 문자열을 반대로 작은따옴표로 감싼다.
        2. 백슬래시\를 이용한다  
        'python\'s favorite food is perl'  
    * 여러 줄인 문자열을 변수에 대입하고 싶을 때
        1. \n 삽입
        2. 연속된 작은따옴표 또는 큰따옴표 3개  
        '''my name  
        is  
        Brandon  
        '''
    * 이스케이프 코드 : 프로그래밍할 때 사용할 수 있도록 미리 정의해 둔 "문자 조합"이다. 주로 출력물을 보기 좋게 정렬하는 용도로 이용된다.  
    \n : 개행  
    \t : 수평 탭  
    \두번 : \
    \' : 작은따옴표
    \" : 큰따옴표  
    \r : 캐리지 리턴(활성 위치를 현재 라인의 시작으로)  
    \f : 폼 피드(활성 위치를 다음 페이지의 시작으로)  
    \a : 벨 소리  
    \b : 백 스페이스(활성 위치를 현재 위치에서 한 스페이스 뒤로 옮김)  
    \000 : 널문자

    * 문자열 연산하기
        1. 문자열 더하기  
        head = 'Python'  
        tail = 'is fun!'  
        head + tail
        -> python is fun!

        2. 문자열 곱하기 : 연속으로 출력된다  
        a = 'python'
        a * 2  
        -> pythonpython  
        '=' * 50
        -> ===========쭈욱

    * 문자열 인덱싱과 슬라이싱  
        * 인덱싱 : 문자열 내 특정한 값을 뽑아냄  
        a = 'Life is too short'  
        a[3]은 e이다
        a[-1]은 n이다. 음수는 뒤에서부터 센다  
        * 슬라이싱 : 범위 내의 문자를 뽑아냄  
        a[0:3] : 0부터 3미만의 인덱스에 해당하는 문자를 슬라이싱  
        a[val1 : val2] :의 형식으로 가며  
        val1 <= a < val2 에 해당하는 문자를 가져온다.
        앞번호를 생략 시 처음부터 가져오고 끝번호를 생략 시 끝까지 가져온다.  
        a = '20171218sunny'  
        year = a[:4]  
        month = a[4:6]  
        day = a[6:8]  
        weather = a[8:]  
        다음과 같이 문자열을 나눌 수 있다.

    * 문자열 포매팅 : 문자열 안에 어떤 값을 삽입하는 방법
        1. 숫자 바로 대입  
        ' I eat %d apples' % 3  
        -> I eat 3 apples  

        2. 문자열 바로 대입  
        ' I eat %s apples' % 'five'  
        -> I eat five apples  

        3. 숫자 값을 변수로 대입  
        a = 3  
        'I eat %d apples' % a  
        -> I eat 3 apples  

        4. 2개 이상의 값 넣기  
        number = 10  
        day = 2  
        'I ate %d apples in %d days' % (number, day) 

    * 문자열 포맷 코드  
    %s : 문자열(string)  
    %c : 문자 1개(character)  
    %d : 정수(integer)  
    %f : 부동소수(floating-point)  
    %o : 8진수  
    %x : 16진수  
    %% : Literal%(문자 %자체)  
    ** %s 는 어떤 형태의 값이든 변환해 넣을 수 있다.

    * 포맷 코드와 숫자 함께 사용하기
    
    1. 정렬과 공백  
    "%10s" % "hi"  
    ->           hi : 10칸의 공간에서 hi를 오른쪽으로 정렬하고 나머지는 공백    
    '%-10sjane" % "hi"  
    ->hi          jane : 10칸의 공간에서 hi를 왼쪽으로 정렬하고 공백  
    2. 소숫점 표현하기  
    "%0.4f" % 3.141592  
    -> 3.1415  
    정수부는 위 처럼 공백을 나타대고 소수점 이하 부분은 몇자리의 소수점을 나타낼지 정한다.  

    * 문자열 관련 함수들
        1. count : 문자 갯수 세기  
        a = "hobby"  
        a.count('b')  
        -> 2  
        2. find : 처음 나온 위치 알려주기  
        a.find('o')  
        -> 1  
        a.find('z')  
        -> -1 : 없을 경우 -1 반환  
        3. index : find와 비슷하지만 찾는 문자열이 없다면 오류발생  
        a.index('z')
        -> 에러!!!!!!!!  

        4. join : 변수의 문자를 괄호 안의 문자열의 각 문자 사이에 삽입  
        a = ", "  
        a.join('abcd')  
        -> a,b,c,d  

        5. upper : 소문자를 대문자로 바꾸기  
        a = 'hi'  
        a.upper()  
        -> HI  

        6. lower : 대문잘르 소문자로 바꾸기  
        a = "HI"  
        a.lower()  
        -> hi  

        7. lstrip : 왼쪽 공백 지우기  
        a = "  hi"  
        a.lstrip()  
        -> hi  
        
        8. rstrip : 오른쪽 공백 지우기  
        7번과 같은 방식   
        9. strip : 양쪽 공백 지우기  
        7번과 8번 합  

        10. replace : 문자열 바꾸기  
        a = 'Life is too short'  
        a.replace("Life", "your leg")  
        -> your leg is too short  
        11. split : 괄호안의 값을 기준으로 하나씩 나누어 리스트에 들어간다. 아무것도 없을시 띄어쓰기에 의해 나뉜다  
        a = 'Life is too short'  
        a.split()  
        ->[Life, is, too, short]  
        a = 'a:b:c:d'  
        a.split(:)  
        -> [a, b, c, d]  

    * 고급 문자열 포매팅
        1. 숫자 바로 대입  
        "I eat {0} apples".format("five")  
        -> I eat five apples  
        변수로 치환가능  

        2. 두 개 이상의 값 넣기  
        number = 3  
        day = 2  
        'I eat {0} apples in {1} days'.format(number, day)  
        3. 이름으로 넣기  
        'I ate {number} apples in {day} days'.format(number = 3, day = 2)  
        -> I ate 3 apples in 2 days  

        4. 혼용해서 넣기
        "I ate {0} apples. so I was sick for {day} days.".format(10, day=3)  
        I ate 10 apples. so I was sick for 3 days.

        5. 왼쪽 정렬/오른쪽 정렬/ 가운데 정렬  
        "{0:<10}".format("hi")  
        hi          
        "{0:>10}".format("hi")  
                hi  
        "{0:^10}".format("hi")  
            hi      
        
        6. 공백채우기  
        "{0:=^10}".format("hi")  
        ====hi====  
        "{0:!<10}".format("hi")  
        hi!!!!!!!!  
        '><^'바로앞에 넣는다. 

        7. 소숫점 표현하기  
        y = 3.42134234  
        "{0:0.4f}".format(y)  
        3.4213  

        "{0:10.4f}".format(y)  
            3.4213  
        앞서 살펴본 형식과 같다.  

        8. { } 표현하기  
        "{{ and }}".format()  
        { and }  
        그냥 두 번 사용하면 된다.


















# python
    * C++을 했기 때문에  새로운, 다른 내용만 기록

## 주석
* '#': 한 줄만 주석처리
* ' """ ' : 시작과 끝을 지정해 해당 지역 주석처리

## 연산
* a**b : a의 b승

## 변수
* 파이썬은 C++과 다르게 데이터 타입의 정의를 해주지 않는다.
* 띄어쓰기, 숫자번저시작 안된다.

## 자료형


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
* formating


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
        input() # 괄호 안에 있는 내용을 출력하고 입력을 받는다.
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


## 튜플
* 소괄호를 사용하고 값을 바꿀 수 없다.

## 딕셔너리
* 중괄호를 사용
* my_dict = {'헤흐': '남'}  키를 넣어주면 값을 반환
* my_duct['헤흐'] = '여' 바꿀수있음

type(val)  # val의 타입을 알려줌

float(val) # val 의 자료형을 float으로 바꿈
str(val) # 숫자를 문자열로 바꿀수도있다
list(val) #문자열을 하나씩 배열로 바꿀수도 있음

