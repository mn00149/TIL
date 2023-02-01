# TIL

## 22.04.13

기억 해야 될 메모리 영역(코드, 힙, 스택, 데이터)
객체,배열 => 힙
지역변수, 객체 나 배열을 가리 키는 해쉬 값 => 스택
스태틱 (변수) =>데이터
메서드, 로딩 될때 => 코드

자바의 데이터 형 => 참조(레퍼런스) 형 타입, 데이터 타입
문자열 비교는 equals로 하자!!

오버로딩 => 같은 클래스내에서 갘은 이름의 메서드를 여러개 선언 하는 것(단 매개변수는 달라야 한다!!
리턴은 같아도 된다)ex:println()

### 생성자

-리턴 타입이 없다 -클래스 이름과 같아야 한다 -생성자도 일종의 오버로딩 -매개변수가 있는 생성자를 만들거면 기본 생성자도 같이만들고, 안만들거면 아예 만들지 말자

### static 변수

-객페를 만들지 않고 변수나 메소드의 사용이 가능 -보통 간단한 값의 처리시 사용
-main()호출되기 전에 data 영역에 이미 생성 된다 -로딩 되기 전에 이미 필요한 영역을 메모리에 잡아 둔다!! -메서드안에선 static변수를 선언 할 수 없다(메서드 안에선 무조건 지역 변수만 사용 할 수 있다)

### Garbage Collecting

-필드와 객체에 할당된 메모리르 회수(heap영역에 항당된 메모리)
-heap 영역에 생성된 data를 참조하는 값이 없는 경우 Garbage Collector에 의해 해당 data가 회수 된다!!

### 상속

-자식 객체를 생성하면 부모 객체 또한 자동으로 만들어진다 => 부모의 객체를 접근 할 수 있는 이유!! -상속의 관계는 위로만 접근 할 수 있다! -부모 객체를 생성 해도 자식 객채가 자동으로 만들어지진 않는다!!
-private 선언된 부모의 필드는 자식도 접근 불가, 접근 할려면 setter or getter로 할 것
-private은 선언된 class를 벗어나면 접근 할 수 없다.

### 업캐스팅

업캐스팅은 실제 실무에서도 많이 쓰인다

기본형 ->class 로 변환: boxing(반대는 당연히 unboxing) => 레퍼와 기본형 타입에서만 가능하다

Collections Framework

- 배열의 단점을 개선한 클래스로 객체만 저장할 수 있다. => 해쉬 값이 저장된다
- 배열의 단점인 메모리 낭비를 피할수 있는 구조이다.
- 동적인 크기 변경이 가능합니다.
- 자료를 효율적으로 정리하는것을 자료구조(Data structure)라 한다.
- 자료구조 방법에는 Set계열, List계열, Map계열이 있다.
- java는 java.util 패키지의 자바 컬렉션(JCF)에서 자료구조 방법을 제공한다

### Set

- 순서가 없고 중복안됨 => 인덱스가 없다 => 중복이 안된다 =>순서가 있는 list 는 중복이 가능하다
- HashSet, TreeSet

List타입은 인터페이스 ArrayList가 업캐스팅 가능!!

### Map 
   - Key, value 한쌍 
   - HashMap, Hashtable  
   - put 메서드로 입력합니다. 
   - 중복된 키 값을 허용하지 않습니다(index가 없다). 
	만약 사용하게되면 기존의 값이 삭제된다(덮어쓰기가 된다).
      -중복된 value는 허용 한다 
   - 검색 결과가 없으면 null을 리턴한다. 
Properties를 쓰는 이유=>가끔 설정파일로 쓰느 경우가 있어서 이를 객체로 변환 하여 읽을 때 사용 한다

# 22.05.13
### Dom 
- document.getElementById(id) => 1개
- document.getElementByTagName(name) => 배열
- document.getElementByClassName(name) => 배열
- document.querySelector() => 1개
- document.querySelectorAll() => 배열
### Map

- Key, value 한쌍
- HashMap, Hashtable
- put 메서드로 입력합니다.
- 중복된 키 값을 허용하지 않습니다(index가 없다).
  만약 사용하게되면 기존의 값이 삭제된다(덮어쓰기가 된다). -중복된 value는 허용 한다
- 검색 결과가 없으면 null을 리턴한다.
  Properties를 쓰는 이유=>가끔 설정파일로 쓰느 경우가 있어서 이를 객체로 변환 하여 읽을 때 사용 한다

## 22/04/21 TIL

### Class

프로그래밍은 어떤 자료형으로 변수를 선언하여 그변수에 값을 할당하는 것의 연속이다
자료형은 자바에서 자동으로 제공해주는 기본 자료형과 그때프로그램에 따라 개발자가 만드는 사용자정의 자료형이 있다
클래스는 내가 만들어내는 사용자정의자료형이다
사용자정의자료형(UDDT) : 객체 자료형(Object DataType)

- 필요에 의해서 새롭게 만들어 사용하는 자료형
- 만드는 도구, 설계하는 도구, 모델링하는 도구 가 필요하다. : class

## JAVA JSP
### 자바의 요청 방식(get, post)
#### get방식의 특징
- url에 변수(데이터) 를 포함하여 요청한다 따라서 데이턱 노출 되어 보안상 취약점이 존제 한다.
- 데이터는 헤더에 포함되어 전송 된다
- 캐싱 할 수 있다
#### post방식의 특징
- url에 데이터를 노출 시키지 않는다. 따라서 기본 보안은 된다
- 데이터는 body에 포함되어 전송 된다
- 캐싱 할 수 없다
- 회원 가입, 글쓰기, <form>등 노출 되선 안되는 데이터를 전송 할 떄 쓰인다
### Servlet 의 request , response
#### request 
request에는 클라이언트에 대한 기본 정보(ip나 port정보등)가 포함된다
또한 body에 변수(데이터)가 포함된다
#### response
response 에느 클라이언트를 식별 할 수 잇도록 header에 대한 정보가 들어있다
<<<<<<< HEAD

## pojo





클로져를 많이 쓰게되면 지역변수가 메모리에서 사라지지 않는 경우가 생겨 많이 쓰는건 둰장 되지 않는다
클로져는 지역변수를 꼭 남겨야 할때만 쓰자

프로토 타입
- 프로토타입은 생성자함수로 생성된 객체가 공통으로 가지는 공간이다.
- 프로토타입을 사용하지 않고 메소드를 만들경우는 객체가 생성될때 마다
  속성과 메소드를 계속 만들어 메모리가 비효율적이 된다.

## 소셜 로그린

OAuth => 인등을 검증된 다른 사이트에 맡김



## MessageConverter

- 각 언어 마다 Data를 전송하는 객체가 다름 => 통일된 Data 전송 매체가 필요
- 과거엔 xml, 최근엔 json이 많이 쓰임
- java object를 json으로 json을 java object롤 변환해주는 것이 바로 Message Converter

 

## Ioc

- 스프링 부트의 특징 중 하나로 제어 권을 스프링이 갖는것
- 내가 들고있는 클래스들을 스캔하여 힙 메모리 영역에 등록해준다

## docker

- 도커를 사용하는 이유 -> 프로그램 다운이 편리 하다 또한 에러가능성도 적다
- 도커란 -> 컨테이너를 이용하여 응용 프로그램을 더 쉽게 배포하고 실행 할 수 있도록 서계된 도구
- 컨테이너란 -> 다양한 프로그램의 실행 환경을 추상화 한것

## DI(의존성 주입)

- IOC를 통해 스캔된 객체들을 쓸때마다 생성 하지 않고 싱글톤으로 쓸수 있게 된다

## git pull 댕기는법
1. 자신의 로컬 master branch로 이동(맨처음 플젝시작시 환경 설정한 부분만 세팅되어있음)
2. 자신의 로컬 마스터 브랜치에서 새로운 로컬 브랜치를 생성
3. 새로 생성한 브랜치로 이동(환경 세팅만 되어있는 master branch 와 같은 상태)
4.새로 생성한 로컬 브랜치에서 origin의 woong 브랜치를 pull
만일 본인의  로컬master브랜치에서 작업을 한 내역이 있어서 conflict이 날경우
1. 새로 폴더를 만들어서 github daymood 래퍼지토리의 master 브랜치를 클론
2. 클론이 되면 자동으로 git init과 git remote등록이 되어있는 상태임
3. 나머지는 위의 방법(1~4)과 동일하게 진행하면됨

## AWS 탄력적 ip
- aws에서 프리티어 버전으로 인스턴스 생성시 public ip를 제공받느데 이 ip는 유동적인 ip이다
- 따라서 고정 ip가 피요한데 이떄 탄력적 ip를 생성 하여 연결 해주면 된다
- 주의점
 1. 프리티어 버전에서 탄력적 ip는 1개만 무료이다
 2. 할당받은 탄력적ip를 쓰지않으면 과금된다
 3. 즉 프리티어 버전으로 사용시 탄력적ip를 할당받으면 꼭 쓰던지 아니면 아예 받지를 말자!!
 
 ## 알고리즘 공부
 정렬 알고리즘
 - 퀵 정렬
 - 삽입정렬
 - 선택 정렬
 - 계수 정렬
## 그래프 이론 정리

## 스프링 
스프링의 가치 -> 객체지향 
