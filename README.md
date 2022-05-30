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
-리턴 타입이 없다
-클래스 이름과 같아야 한다
-생성자도 일종의 오버로딩
-매개변수가 있는 생성자를 만들거면 기본 생성자도 같이만들고, 안만들거면 아예 만들지 말자

### static 변수
-객페를 만들지 않고 변수나 메소드의 사용이 가능
-보통 간단한 값의 처리시 사용
-main()호출되기 전에 data 영역에 이미 생성 된다
-로딩 되기 전에 이미 필요한 영역을 메모리에 잡아 둔다!!
-메서드안에선 static변수를 선언 할 수 없다(메서드 안에선 무조건 지역 변수만 사용 할 수 있다)

### Garbage Collecting
-필드와 객체에 할당된 메모리르 회수(heap영역에 항당된 메모리)
-heap 영역에 생성된 data를 참조하는 값이 없는 경우 Garbage Collector에 의해 해당 data가 회수 된다!!

### 상속
-자식 객체를 생성하면 부모 객체 또한 자동으로 만들어진다 => 부모의 객체를 접근 할 수 있는 이유!!
-상속의 관계는 위로만 접근 할 수 있다!
-부모 객체를 생성 해도 자식 객채가 자동으로 만들어지진 않는다!!
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

## pojo

