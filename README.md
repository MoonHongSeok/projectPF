# KH정보교육원 수료

# 교육기간 2019년 08월 16일 ~ 2020년 01월 23일
## 작성자 : 김현진

### JAVA 프로그래밍
- 기본문법 및 객체지향에 대한 개념과 이해, Collection, List,Set, Map, Exception Handling, 다형성 학습

- Oracle
DML, DDL, DCL, subquery, join, view, PL/SQL , 기본문법 학습

### JDBC
- JDBC연동순서, 각 클래스의 역할, Type별 driver 특징 설명, transaction의 처리방법 학습

### JavaScript / HTML 5 / CSS3 
 - JavaScript 기본 문법, function, 웹표준 기반의 HTML5 마크업, CSS3스탕일링

### jQuery / Bootstrap / Ajax / JSON / XML
- jQuery웹서비스 활용, Ajax XMLHttpRequest서버와의 통신 이해, GoogleMap등 오픈API활용, JSON 파싱 학습

### Servlet / JSP / JSTL / EL
- MVC기반 Web serivce구현, Container의 사용법, Java Web Service시 폴더구성,
- Servlet 작성법 및 요청과 응답의 사용(HttpServletRequest, HttpServletResponse), EL, JSTL 학습

### Spring / myBATIS
- Spring의 특징 및 이해와 실습, Spring MVC처리, MyBATIS 연동
#

# Spring MVC패턴 기반의 "fifteenGG" 프로젝트

- 듀오찾기 게시판으로 같이 플레이할 유저를 매칭합니다.
- 게임 빅데이터를 활용하기 위한 Riot API(Rest API)를 사용하여 데이터를 수집했습니다.
- 빅데이터를 기반으로 통계수치화 및 시각화 하였습니다.

![개발일정15gg](https://user-images.githubusercontent.com/53084458/82660573-9265da80-9c65-11ea-9fec-b4365a025c15.jpg)



### 2019년 12월 23일 ~ 2020년 1월 23일.

#

![사용 툴](https://user-images.githubusercontent.com/53084458/83226348-c3da2b00-a1bc-11ea-8263-09bcc5800b0c.jpg)

- 사용 언어 : JAVA, JavaScript
- 툴 : Spring, Oracle
- 서버 : apache Tomcat 
- 홈페이지는 HTML기반이며 디자인은 css, 부트스트랩4 사용
- 사용 API : Riot Games의 Rest API 사용
- JDBC : myBaits 프레임워크
- 라이브러리 : gson, Jquery
- 형상관리 : github

![db1](https://user-images.githubusercontent.com/53084458/83225697-4eba2600-a1bb-11ea-8c0b-ec5aaf935ebf.jpg)
![db](https://user-images.githubusercontent.com/53084458/83225703-511c8000-a1bb-11ea-918d-e007cb946542.jpg)

- DB 설계


#

# 담당페이지 설명 및 시연자료
## fifteenGG 프로젝트에서 
### 1. 듀오찾기 페이지,
### 2. 챔피언통계 페이지,
### 3. 승률통계 페이지를 담당 구현하였습니다.

#

## 1. 듀오찾기 게시판
### "듀오찾기 게시판"은 게시글 작성, 검색, 목록을 한 페이지에 담아냈습니다.
 - 게이머 특성상 페이지에 오래 머무르지 않아 짧은시간에 많은 정보를 나타내기 위함입니다.
 - 연장선으로 게시글 내용도 클릭없이 바로 보이며, 클릭시 작성 닉네임값으로 팀원이 구현한 검색페이지로 이동됩니다.
 ###
### "듀오찾기 게시판"은 게시글 삭제가 필요 없습니다.
- 한사람이 짧은시간에 여러 게시물을 올릴 수 있기때문에 불필요한 중복을 처리해야 했습니다.
- 하지만 시각적 표현이 필요하여 취소선으로 대체되었습니다.
#

## 화면 게시물등록, 검색, 목록등을 구현한 Spring MVC패턴 코드입니다.
### 사용자가 화면에서 액션이 취해지면 이벤트를 처리하는 "Controller"입니다.
#

![partyController](https://user-images.githubusercontent.com/53084458/82750191-6a9f7f80-9de9-11ea-9781-358d1979e8b5.jpg)

- @RequestMapping 어노테이션으로 어떤 Controller로 처리할지 경로를 설정했습니다.
- @Autowired로 의존하는 객체(Service)를 주입시켰습니다.
#

## Controller를 통해 나타낼 DATA, DATA의 가공처리등을 책임지는 "Model"입니다.  
  
### Model Service입니다.

![partyService](https://user-images.githubusercontent.com/53084458/82750201-6f643380-9de9-11ea-9405-be16a9ed16d9.jpg)

- @Service로 Repository를 통해 DB에서 DATA를 가져온 후 Controller에 전달해주는 클래스임을 명시했습니다.
- @Repository로 DAO에서는 해당 클래스가 DB에 접근하는 클래스임을 명시했습니다.
- DAO에서 @Autowired sqlSession 의존성을 주입했습니다.
- sqlSessionTemplate의 경우 commit과 rollback등으로 mapper의 관리를 도와줍니다.

#

#### 어노테이션 경우 더 높은 계층 @Component라는 어노테이션이 존재하지만
#### 구체적으로 @Controller, @Service, @Repository 어노테이션을 사용하게되면 시각적으로 더욱 판단하기 편리합니다.
#
### 흐름
#### 사용자가 View에서 액션을 하게되면 Controller에서 액션에 맞게 Model로 정보를 전달하게 됩니다.
#### Model에서는 DB까지 사용자 요청에 맞게 DATA를 저장, 수정 등 올바르게 가공하여
#### 다시 Model을 통해 Controller에서 View로 결과를 출력 최종적으로 사용자까지 도달하게 됩니다.

#

### Jquery를 사용하여 게시글 타이머 및 입력시간 표시를 구현했습니다.

<img width="464" alt="만료시취소선화면" src="https://user-images.githubusercontent.com/53084458/82659017-f33fe380-9c62-11ea-9a41-7130c5a48682.png">
<img width="692" alt="만료시취소선" src="https://user-images.githubusercontent.com/53084458/82659008-f0dd8980-9c62-11ea-8aa7-5e60326dd74b.png">

#### JavaScript UNIX포맷 함수인 Date().getTime(), JAVA의 UNIX포맷 함수인 currentTimeMillis()를 활용
#### 초<분<시간<일 단위로 변수를 정의한 후 현재시간과 입력시간을 비교해 구현했습니다.
- 24시간이 지나면 자동적으로 게시한 날짜로 변경됩니다.


## 게시글 작성 시연입니다.

![게시글작성](https://user-images.githubusercontent.com/53084458/82656301-7c085080-9c5e-11ea-9ac4-e07c08394f8c.gif)



### 제목은 자동으로 매핑됩니다.
- 인터넷엔 동의어가 많습니다, 게임용어는 더욱 그렇습니다. 제목을 일정한 패턴으로 통일시켜 이를 검색에 활용하였습니다.


##
## 검색

<img width="483" alt="동적쿼리검색용첨부" src="https://user-images.githubusercontent.com/53084458/82661302-b8d84580-9c66-11ea-932c-8488274b257a.png">

- 사용자가 검색 액션을 하게되면 동작하는 쿼리입니다.
- choose태그 안에서 조건에 따라 when또는 otherwise의 코드가 실행됩니다. 

## 검색 시연입니다.

![검색시연자료](https://user-images.githubusercontent.com/53084458/82661296-b675eb80-9c66-11ea-93b4-38f2cc7ce0ee.gif)

### 검색은 Select를 활용했습니다.
- 일정한 패턴의 제목은 여러번 검색할 필요가 없습니다. 3가지 조건만으로 양질의 결괏값을 반환합니다.
- SQL을 공부하며 조건문 실수가 아닌이상 100% 정확한 결과만을 출력하는데서 이를 검색에 활용하였습니다.

#
## 2. 챔피언 통계 페이지입니다.
### Jquery의 Data Table Library를 활용하여 틀을 만들고 CSS로 그래프를 표현했습니다. 
### 그래프는 실제 DB를 기반으로 변동됩니다.
#

## Riot(Rest) API 파싱하기

![파싱1](https://user-images.githubusercontent.com/53084458/82916416-f9102e80-9fac-11ea-8532-2aacafcc7c17.jpg)

- Rest API로부터 받아온 json형식의 DATA를 gson을 사용 클래스매핑하여 파싱하였습니다.

#

![파싱2](https://user-images.githubusercontent.com/53084458/82916408-f6153e00-9fac-11ea-8c42-41b3a7b03d45.jpg)
![파싱쿼리](https://user-images.githubusercontent.com/53084458/82919320-d4b65100-9fb0-11ea-9ef9-8087c285a4a2.jpg)

- 파싱된 DATA는 vo->Service->DAO->Mapper.xml거쳐 INSERT 쿼리를 통하여 저장됩니다.

#

![파싱DB](https://user-images.githubusercontent.com/53084458/82916414-f8779800-9fac-11ea-9bf9-fcc6cd9c0225.jpg)

- 위 과정을 통하여 저장되는 테이블입니다.

#

## 통계를 수치화 하기 위한 쿼리입니다.

<img width="672" alt="통계테이블쿼리문" src="https://user-images.githubusercontent.com/53084458/82663570-e0311180-9c6a-11ea-85b0-777ffe50beb7.png">

#### 처음에는 카테시안 곱 발생, GROUP조건, JOIN에서 많은 문제가 있었지만 각 COLUMN별로 다시 정리해가며
#### 알맞은 테이블 JOIN과 GROUP찾아 카테시안 곱을 해결할 수 있었고 챔피언별 통계 구조의 다중서브쿼리를 완성할 수 있었습니다.


#

## 가공된(수치화) 통계자료를 시각적으로 표현


![종합통계프론트](https://user-images.githubusercontent.com/53084458/82924574-7ccf1880-9fb7-11ea-8a54-bd12e337cc65.jpg)

- 빨간줄:그래프의 길이를 나타냅니다.
- 파란줄:그래프의 색상을 나타냅니다.
- 녹색줄:통계수치를 보여줍니다.
### 결과:실제 수치화 된 데이터를 기준으로 그래프 길이가 변동됩니다.

#

## 통계테이블 최종 출력

![데이터테이블시연자료](https://user-images.githubusercontent.com/53084458/82663564-dd362100-9c6a-11ea-86bf-de71cff8c732.gif)
- 챔피언(사진) 클릭시 팀원이 구현한 챔피언 상세정보 페이지로 이동합니다.

#


### myBatis
#### 첫단에 명시되는 select, update, delete, insert 등의 요소에 집중되도록 설계 되어 빠르고
#### JDBC와 비교해 매우 짧아진 코드로 가독성, 생산성, 유지보수등 이점이 많은 프레임워크임을 배웠습니다.
#



## 3. 승률 통계 페이지입니다.
### Chart.js를 활용하여 DATA를 시각과 하였습니다.
#### 처음에는 챔피언 통계 페이지에 활용할 목적이었으나, 공부를 할수록
#### 한눈에 들어와야할 종합데이터를 표현하기엔 적절하지 않다고 판단되어 좀 더 상세하게 표현 가능한
#### 승률 통계 페이지에서만 활용하게 되었습니다.

## 파싱하여 저장된 DATA를 사용해 승률을 계산한 쿼리입니다.

![승률통계쿼리](https://user-images.githubusercontent.com/53084458/82923319-ba32a680-9fb5-11ea-8fc7-a039c6402c97.jpg)

## Chart.js 코드입니다.

![chartjs보완](https://user-images.githubusercontent.com/53084458/82922967-409ab880-9fb5-11ea-8da8-74e204a4ba39.jpg)

- canvas태그를 사용해 id를 정해주고 기본적인 사이즈를 설정합니다.

#

<img width="714" alt="차트제이에스" src="https://user-images.githubusercontent.com/53084458/82663588-e7f0b600-9c6a-11ea-932f-93ed55163bd0.png">

- 해당 id를 호출해 어떤 그래프타입을 사용할 것인지, 크기와 색상등 세부적인 css를 설정합니다.

#

![3 승률통계](https://user-images.githubusercontent.com/53084458/82663581-e626f280-9c6a-11ea-8241-04d5136341e6.jpg)

- 승률에 대해 그래프로 표현하여 숫자를 보다 확인하기 쉽게 사용자 중점으로 표현 하였습니다. 

#
### 항상 아쉬움이 남지만 뒤돌아보면
### 처음 "Rang프로젝트" 당시 CRUD기능만큼은 해내려 했던 자신보다
### 성장했음을 느껴 개인적으로 굉장히 뿌듯했던
## fifteen.GG 프로젝트 였습니다. 

#
#
#
#
#
#
#
#

# 첫번째 프로젝트 "Rang"

## 저의 첫번째 프로젝트인 "Rang"입니다.
#### 여행을 공유하여 나의 여행을 다른사람들과 소통, 함께할 일행구하기 그리고
#### 다른사람의 여행을 참고하여 나의 여행을 디자인할 수 있는 플랫폼을 목적으로 진행하였습니다.


### 일정

![세미프로젝트 타임라인](https://user-images.githubusercontent.com/53084458/82647471-35f8c000-9c51-11ea-97e1-7bd58b5e0ec7.jpg)

### 2019년 11월 4일 ~ 2019년 12월 20일.




#

### 담당페이지 설명 및 시연자료
#### Rang 프로젝트에서 "너랑나랑" 페이지를 담당하여, 
#### MVC패턴을 기반으로 게시판의 기본적 데이터처리 기능인 Create, Read, Update, Delete 구성하여
#### 게시글 작성, 출력, 수정, 삭제로 기능을 구현하였습니다.

#

## 너랑나랑 페이지.
### 너랑나랑 페이지는 함께 여행할 동료, 친구를 찾는 공간입니다.
#### 참여하기 기능에서 실제 버튼을 눌렀는지, 누르지 않았는지를 실제 DATA로 비교하여
#### 데이터 무결성을 구현하고자 했습니다.

![참여하기기능](https://user-images.githubusercontent.com/53084458/82725522-71aa8d00-9d18-11ea-9d9e-8f66cdae1cf1.jpg)
#

#### 1.사용자가 직접 버튼을 클릭하게 되면 해당 번호를 가진 게시물은 DB에 값이 저장되게 됩니다.
<img width="310" alt="참여하기코드1" src="https://user-images.githubusercontent.com/53084458/82725525-72dbba00-9d18-11ea-884b-f6e26980dc96.png">

#### 2.저장된 값이 COUNT되어 "참여하기" 버튼을 누른 인원을 표시하게 됩니다.

<img width="340" alt="참여하기코드2" src="https://user-images.githubusercontent.com/53084458/82725526-740ce700-9d18-11ea-88e6-f42a8e8de889.png">

#### 3.데이터 무결성을 구현하여 중복클릭을 방지했습니다. 



<img width="411" alt="참여하기코드3" src="https://user-images.githubusercontent.com/53084458/82725521-6f483300-9d18-11ea-84a5-49603bc33c54.png">

#### 참여하기 버튼의 경우 해당 게시물 번호와 유저의 번호(클릭이 아닌경우:0, 클릭한 경우:1)를 비교하여

#### 클릭 여부를 판단해 활성화 or 비활성화를 하게 됩니다.

#


## 게시글 작성 시연입니다.

### JDBC방식을 적용하여 DATA를 DB까지 올바르게 전달하고 올바르게 전달 된 DATA를 
### 게시판 List에 출력할 수 있었습니다. 또 기능들을 구현하면서 MVC패턴에 대해 깊이 이해할 수 있었습니다.
#

![게시글작성](https://user-images.githubusercontent.com/53084458/82644602-8c173480-9c4c-11ea-9a10-03ad688e6022.gif)
#
### 먼저 위 시연처럼 정보를 입력해 등록 액션을 하게되면
### 해당 서블렛에서 정보를 받아 Service를 거쳐 DAO에서 DATA를 처리하게됩니다.
![RangInsertCont](https://user-images.githubusercontent.com/53084458/82750204-712df700-9de9-11ea-8e8a-e08ff88a3c00.jpg)

#
### 정보를 받은 DAO는 JDBC를 이용하여 DB까지 올바르게 정보를 가공 처리합니다.
![RangInsertSQL](https://user-images.githubusercontent.com/53084458/82750209-74c17e00-9de9-11ea-8f02-825947d2fb85.jpg)
#
### 이렇게 처리된 DATA는 사용자 요청에 따라 oracle DB의 정보를 입력하게 되고
### 처리된 DATA를 기반으로 다시 View에 출력하게 됩니다.
#

## 게시글 수정과 삭제 시연입니다.

![게시글수정삭제](https://user-images.githubusercontent.com/53084458/82644845-f62fd980-9c4c-11ea-80bd-0bc262bca87e.gif)

#

![RangUpdate](https://user-images.githubusercontent.com/53084458/82750214-78ed9b80-9de9-11ea-9a7e-debe799ac6fb.jpg)

#
### DAO코드입니다.
#

![RangUpdateDAO](https://user-images.githubusercontent.com/53084458/82750216-7b4ff580-9de9-11ea-9e06-f35a34d2fda5.jpg)

#

### 기존정보에서 수정될 정보를 받아 PreparedStatement를 통해 SQL을 실행하게 됩니다.
### (SQL:UPDATE TBOARD SET TBTITLE = ?, TBCONTENT = ?, TBFILE = ? WHERE TBNO = ?)
### JAVA의 코드는 위에서 아래로 순차적으로 처리되며, "pstmt.setString(1, tb.getTbTitle());"부터 실행
### SQL문의 첫번째 "?"부터 DATA를 처리해 수정작업이 이루어집니다.

#

## Properties 활용

![게시판SQL프로퍼티관리](https://user-images.githubusercontent.com/53084458/82750218-7d19b900-9de9-11ea-9db5-3c8f206c5eb2.jpg)

### properties를 활용하여 JAVA코드와 SQL코드를 별도관리하여 
### 유지보수측면에서 이점을 발휘하는것을 배웠습니다.

#

### 게시판 페이징처리 코드입니다.
![RangPage처리](https://user-images.githubusercontent.com/53084458/82750210-768b4180-9de9-11ea-96ee-3713022ea7c8.jpg)


#


## 상세페이지에서 댓글 등록,수정,삭제하는 시연입니다.


![댓글시연](https://user-images.githubusercontent.com/53084458/82644988-24151e00-9c4d-11ea-8d4a-3c2c85963134.gif)
#



- Rang 프로젝트 DB설계
![5조 랑ppt 최종 (1)_30](https://user-images.githubusercontent.com/53084458/82640993-95050780-9c46-11ea-839f-6e54fbad4f00.png)

### END;





