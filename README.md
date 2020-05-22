# KH정보교육원 이수

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

# fifteenGG 프로젝트

###
![개발일정15gg](https://user-images.githubusercontent.com/53084458/82660573-9265da80-9c65-11ea-9fec-b4365a025c15.jpg)

## 담당페이지 설명 및 시연자료
### fifteenGG 프로젝트에서 
#### 1. 듀오찾기 페이지 
#### 2. 챔피언통계 페이지 
#### 3. 승률통계 페이지를 담당 구현하였습니다.

#

### 1. 듀오찾기 페이지
- "듀오찾기 게시판"은 게시글 작성, 검색, 목록을 한 페이지에 담아냈습니다.
 #### who? : 게이머 특성상 페이지에 오래 머무르지 않아 짧은시간에 많은 정보를 나타내기 위함입니다.
 ###
- "듀오찾기 게시판"은 게시글 삭제가 필요 없습니다.
#### who? : 한사람이 짧은시간에 여러 게시물을 올릴 수 있기때문에 불필요한 중복을 처리해야 했습니다.
#### 하지만 발표를 위하여 취소선으로 대체되었습니다.
###


<img width="464" alt="만료시취소선화면" src="https://user-images.githubusercontent.com/53084458/82659017-f33fe380-9c62-11ea-9a41-7130c5a48682.png">
<img width="692" alt="만료시취소선" src="https://user-images.githubusercontent.com/53084458/82659008-f0dd8980-9c62-11ea-8aa7-5e60326dd74b.png">


#

## 게시글 작성 페이지 시연입니다.
###

![게시글작성](https://user-images.githubusercontent.com/53084458/82656301-7c085080-9c5e-11ea-9ac4-e07c08394f8c.gif)

#

###
- 제목은 자동으로 매핑됩니다.
#### who? : 인터넷엔 동의어가 많습니다, 게임용어 에선 더욱 그렇습니다. 제목을 일정한 패턴으로 통일시켜 이를 검색으로 활용하였습니다.
- 검색은 Select를 활용했습니다.
#### who? : 일정한 패턴의 제목은 여러번 검색할 필요가 없습니다. 3가지 조건만으로 양질의 결과를 반환합니다.

##
## 검색 시연입니다.

![검색시연자료](https://user-images.githubusercontent.com/53084458/82661296-b675eb80-9c66-11ea-93b4-38f2cc7ce0ee.gif)
<img width="483" alt="동적쿼리검색용첨부" src="https://user-images.githubusercontent.com/53084458/82661302-b8d84580-9c66-11ea-932c-8488274b257a.png">

##
## Jquery의 Data Table을 활용하여 틀을 만들고 CSS로 그래프를 DATA를 기반으로 시각화 하였습니다.
![데이터테이블시연자료](https://user-images.githubusercontent.com/53084458/82663564-dd362100-9c6a-11ea-86bf-de71cff8c732.gif)
<img width="672" alt="통계테이블쿼리문" src="https://user-images.githubusercontent.com/53084458/82663570-e0311180-9c6a-11ea-85b0-777ffe50beb7.png">
##
## Chart.js를 활용하여 DATA를 시각과 하였습니다.
![3 승률통계](https://user-images.githubusercontent.com/53084458/82663581-e626f280-9c6a-11ea-8241-04d5136341e6.jpg)
<img width="714" alt="차트제이에스" src="https://user-images.githubusercontent.com/53084458/82663588-e7f0b600-9c6a-11ea-932f-93ed55163bd0.png">


#
#      Rang 프로젝트


### 일정
![세미프로젝트 타임라인](https://user-images.githubusercontent.com/53084458/82647471-35f8c000-9c51-11ea-97e1-7bd58b5e0ec7.jpg)




#

### 담당페이지 설명 및 시연자료
#### Rang 프로젝트에서 "너랑나랑" 페이지를 담당하여, 
#### MVC패턴을 기반으로 게시판의 기본적 데이터처리 기능인 Create, Read, Update, Delete 구성하여
#### 게시글 작성, 출력, 수정, 삭제로 기능을 구현하였습니다.

#
## 게시글 작성 시연입니다.



![게시글작성](https://user-images.githubusercontent.com/53084458/82644602-8c173480-9c4c-11ea-9a10-03ad688e6022.gif)
#

## 게시글 수정과 삭제 시연입니다.


![게시글수정삭제](https://user-images.githubusercontent.com/53084458/82644845-f62fd980-9c4c-11ea-80bd-0bc262bca87e.gif)

#

- 상세페이지에서 댓글 등록,수정,삭제하는 시연입니다.


![댓글시연](https://user-images.githubusercontent.com/53084458/82644988-24151e00-9c4d-11ea-8d4a-3c2c85963134.gif)
#

- Rang 프로젝트 DB설계
![5조 랑ppt 최종 (1)_30](https://user-images.githubusercontent.com/53084458/82640993-95050780-9c46-11ea-839f-6e54fbad4f00.png)

