css를 통해서 html을 제어할 수 있는 항목들

- 박스 모델
- 글꼴, 문자
- 배경
- 배치
- 플렉스(정렬)
- 전환
- 변환
- 띄움
- 애니메이션
- 그리드
- 다단
- 필터

# > 박스모델

인라인 요소 : 가로 넓이가 최대한 줄어들고 가로와 세로 사이즈를 지정할 수 없다.
블록 요소 : 가로 넓이가 최대한 늘어나고 가로와 세로 사이즈를 지정 가능하다.
ex) span (의미X 콘텐츠 영역을 설정하는 용도) -> 인라인 요소 (단위지정X)
div -> 블록 요소 (단위지정O)

> **width / height**

요소의 가로/세로 너비
auto : (기본값:요소에 이미 들어있는 속성의 값)브라우저가 너비를 알아서 계산
단위 : px, em, vw등 단위로 지정

> **max-width / max-height**

요소가 커질 수 있는 최대 가로/세로 너비
none : 최대 너비 제한 없음
단위 : px, em, vw등 단위로 지정

> **min-width / min-height**

요소가 작아질 수 있는 최소 가로/세로 너비
0 : 최소 너비 제한 없음
단위 : px, em, vw등 단위로 지정

# css에서 사용할 수 있는 단위

- px : 픽셀
  화면에 출력하는 점으로 된 단위(1920pxX1080px해상도)
- % : 상대적 백분율
  몇 퍼센트의 크기를 가지는지 나타내는 단위
- em : 요소의 글꼴 크기
  상대적인 크기
- rem : 루트 요소(html)의 글꼴 크기
  루트=최상의 요소 -> html에서 지정한 크기만 사용
- vw : 뷰포트 가로 너비의 백분율
  V=뷰포트=브라우저의 페이지영역 / W=width=가로 너비
- vh : 뷰포트 세로 너비의 백분율

# 외부 여백

> **margin : 외부 여백을 지정**

요소의 외부 여백(공간)을 지정하는 단축 속성
음수를 사용할 수 있음 (-마이너스)
0 : 외부 여백 없음
auto : 브라우저가 여백을 계산 (가로/세로 너비가 있는 요소의 가운데 정렬에 활용함)
단위 : px,em, vw 등 단위로 지정

개별 속성 : 각각의 방향을 지정할 수 있음

- margin-top : 위쪽에만 여백을 지정
- margin-right : 오른쪽에만 여백을 지정
- margin-left : 왼쪽에만 여백을 지정
- margin-bottom : 아래쪽에만 여백을 지정

**margin은 단위를 1개~4개까지 입력하여 각각의 방향을 지정할 수 있는 단축 속성이다.**

- margin : 10px;
  = 여백 : 위,아래,왼,오른쪽 모두 10px로 지정한다.
- margin : 10px 20px;
  = 여백 : 위,아래는 10px, 왼,오른쪽은 20px로 지정한다.
- margin : 10px 20px 30px;
  = 여백 : 위10px, 왼,오른쪽20px, 아래30px로 지정한다.
- margin : 10px 20px 30px 40px;
  = 여백 : 위10px, 오른쪽20px, 아래30px, 왼쪽40px로 지정한다.
  = 위에서부터 시계방향대로 돌아감

# 내부 여백

> **> padding : 내부 여백 지정 (요소의 크기가 커짐)**

요소의 내부 여백(공간)을 지정하는 단축속성
0 : 내부 여백 없음
단위 : px, em, vw 등 단위로 지정
% : 부모 요소의 가로 너비에 대한 비율로 지정

단축 속성/개별속성으로 margin과 동일하게 4개의 방향을 각각 지정할 수 있다.

# 테두리 선과 색상표현

> **> border : 요소의 테두리 선을 지정하는 단축 속성 (요소의 크기가 커짐)**

- border: 선-두께 선-종류 선-색상;

**개별 속성 : 두께(border-width), 종류(border-style), 색상(border-color)을 모두 입력해야지 테두리가 생겨남** 1.두께 2.종류 3.색상 순서로 입력하기

두께 단위 : px, em, % 등
종류 : solid(실선) 등...

> ### border-width
>
> : 단축속성으로 1~4개의 숫자를 입력하여 각 방향에 대한 두께를 지정할 수 있다.

> ### border-style
>
> : 요소 테두리 선의 종류 / 단축속성

- none : 선 없음
- solid : 실선 (일반 선)
- dotted : 점선
- dashed : 파선
  등등

> ### boder-color
>
> : 요소 테두리 선의 색상을 지정 / 단축속성

- black : (기본값)검정색
- 색상 : 선의 색상
- transparent : 투명

> ### border-방향 / border-방향-속성

: 요소의 테두리 선을 지정하는 기타 속성들
ex)

- border-top: 두께 종류 색상;
- border-top-width: 두께;
- border-top-style: 종류;
- border-top-color: 색상;

# 색상표현

: 색을 사용하는 모든 속성에 적용 가능한 색상 표현

- 색상 이름 : 브라우저에서 제공하는 색상이름
  ex) red, tomato, royalblue 등
- ** Hex 색상코드 : 16진수 색상** **(주로사용)**
  ex) #000, #FFFFFF
- RGB : 빛의 삼원색
  ex) rgb(255,255,255)
- RGBA : 빛의 삼원색 + 투명도
  ex) rgba(0,0,0,0.5) : 빛의삼원색+투명도(0.몇)으로 지정
  등등

# 크기 계산

> box-sizing

: 요소의 크기 계산 기준을 지정

- content-box : (기본값) 요소의 내용(conrtent)으로 크기 계산
  > - border-box : 요소의 내용 + padding + border로 크기 계산

ex) box-sizing: border-box;
= 요소에 지정한 크기로 내부 여백, 테두리 등을 설정하여 크기가 늘어나지 않음

# 넘침 제어 (크기가 벗어난 곳을 자름)

> overflow

: 요소의 크기 이상으로 내용이 넘쳤을 때, 보여짐을 제어하는 단축 속성

- visible : (기본값) 넘친 내용을 그대로 보여줌
- hidden : 넘친 내용을 잘라냄
- auto : 넘친 내용이 있는 경우에만 잘라내고 스크롤 바 생성
- scroll : 스크롤 바 생성 (x,y축 모두)

사용법 ex)
overflow: hidden;
= 요소의 크기가 벗어난 것을 숨긴다.
overflow: auto;
= 요소의 크기가 벗어난 범위만 잘라내고 스크롤바 생성 (x또는y축)

개별속성
overflow-x : x축으로 넘치는 부분만 잘라냄
overflow-y : y축으로 넘치는 부분만 잘라냄

# 출력 특성

> display

: 요소의 화면출력(보여짐) 특성

- block (기본값) : 상자(레이아웃)요소
- inline (기본값) : 글자 요소
- inline-block (기본값) : 글자 + 상자 요소
- **flex : 플렉스 박스 (1차원 레이아웃)**
- **grid : 그리드 (2차원 레이아웃)**
- **none : 보여짐 특성 없음, 화면에서 사라짐**
- 기타 (기본값) : table, table-row, table-cell 등...

사용법 ex)

- display: block;
  = 화면에서 출력되는 인라인 요소(=글자)를 block요소로 바꾸어준다. -> 가로/세로 너비를 지정가능해진다.
- display: none;
  = 화면에서 출력되는 요소들을 안보이게 숨겨준다.

# 투명도

> opacit

: 요소의 투명도

- 1: (기본값) 불투명
- 0~1 : 0부터 1사이의 소수점 숫자로 투명도 조절

사용법 ex)

- opacity: 0.07; -> 투명도가 7%로 가장 투명함 (예시안에서 상대적으로 가장 투명함)
- opacity: 0.4; -> 투명도가 40%로 중간 정도 투명함
- opacity: 0.7; -> 투명도가 70%로 가장 불투명함
- opacity: 1; -> 불투명 함

# 글꼴

기본값은 16px로 지정되어져있다.

> font-style

: 글자의 기울기

- normal : 기울기 없음
- italic : 이텔릭체 (기울어진 글자/oblique보다는 이텔릭체를 주로 사용)
- oblique : 기울어진 글자

> font-weight

: 글자의 두께(가중치)

- normal,400 : (기본값) 기본 두께
- bold,700 : 두껍게
- 100~900 : 100단위의 숫자9개, normal과 bold 이외 두께

> font-size

: 글자의 크기

- 16px : (기본값) 기본 크기
- 단위 : px,em, rem 등 단위로 지정
  등등

> line-height

: 한 줄의 높이, 행간과 유사

- normal : (기본값) 브라우저의 기본 정의를 사용
- 숫자 : 요소의 글꼴 크기의 배수로 지정
- 단위 : px, em, rem 등의 단위로 지정

사용법 ex)

- font-size: 16px;
  line-height: 32px;
  = 글씨-사이즈 는 16px크기이며,
  줄의 높이는 32px크기이다.

- line-heght: 2; (단위가 적혀있지 않는 경우)
  = 줄의 높이는 폰트사이즈의 2배이다.

- line-height: 200%;
  = 줄의 높이는 폰트사이즈의 2배이다.

**! 이때 줄 높이를 단위를 입력한 px를 사용하기 보다는 폰트 글씨의 배수로 적용시켜서
폰트를 바꾸면 줄 간격도 동일한 배수로 바뀔 수 있도록 설정하는 것이 좋다 !
**

> font-famliy: 글꼴1, "글꼴2", **글꼴계열**;

: 글꼴(서체) 지정
띄어쓰기 등 특수문자가 포함된 글꼴 이름은 큰 따옴표로 묶어야한다.

후보1, 후보2, ... 글꼴계열; 작성
제일 앞에 있는 글꼴을 사용하고자 하며 글꼴이 지원이 안될 시 후보2를 적용시킴 후보3,4,5...등 계속 후보를 둘 수 있다. 모두 쓸수 없다면 마지막 글꼴 계열을 사용하게 된다.
그리고 마지막에 글꼴계열;을 필수적으로 입력해주어야한다.

- serif : 바탕체 계열 (뻣침?이 있는 글꼴)
- **sans-serif : 고딕체 계열 (깔끔한 글꼴)**
- monospace : 고정너비(가로폭이 동등) 글꼴 계열
- cursive : 필기체 계열
- fantasy : 장식 글꼴 계열 (꾸밈이 많은 글꼴)

# 문자

> color

: 글자의 색상

- rgb(0,0,0) : (기본값)검정색
- 색상 : 기타 지정 가능한 색상
  **! font-color 또는 text-color라고 앞에 키워드를 붙이지 않는다 !**

> text-align

: 문자의 정렬 방식

- left : (기본값) 왼쪽정렬
- right : 오른쪽 정렬
- center : 가운데 정렬
- justify : 양쪽 정렬

> text-decoration

: 문자의 장식(선)

- none : (기본값) 장식없음
- underline : 밑줄
- line-through : 중앙선

! a태그는 예외로 기본 속성으로 밑줄이 쳐져서 화면에 출력된다 !

> text-indent

: 문자 첫 줄의 들여쓰기 (띄어짐)

- 0 : (기본값) 들여쓰기 없음
- 단위 : px,em, rem 등 단위로 지정
- 음수를 사용가능하다. (=내어쓰기outdent이다.)

# 배경

> background-color

: 요소의 배경 색상

- transparent : (기본값)투명함
- 색상 : 지정 가능한 색상

> background-image

: 요소의 배경 이미지 삽입 / 바둑판식 배열

- none : (기본값) 이미지 없음
- url("경로"); : 이미지 경로
  ex) background-image: url("경로");

> background-repeat

: 요소의 배경 이미지 반복 / 바둑판식 배열이 기본값으로 출력됨

- repeat : (기본값) 이미지를 수직, 수평 반복
- repeat-x : 이미지를 x축으로 수평 반복
- repeat-y : 이미지를 y축으로 수직 반복
- no-repeat : 반복 없음

> background-position

: 요소의 배경 이미지 위치

- 방향 : top, bottom, left, right, center 방향
- 단위 : px, em, rem 등 단위로 지정 (x,y축으로 값이 적용됨)
  ex) background-position: top right;
  = 배경의 위치 는 위에서 오른쪽에 위치한다. (위,오른쪽의 순서가 바껴도 상관없음)
  background-position: 100px 30px;
  = 배경의 위치는 x축으로 100px, y축으로 30px에 위치한다. (y축은 위가 아닌 아래로 내려감)

> background-size
> _사용법 ex) background-size: cover;_

: 요소의 배경 이미지 크기

- auto : (기본값) 이미지의 실제 크기
- 단위 : px, em, rem 등 단위로 지정
- cover : 비율을 유지, 요소의 더 넓은 너비에 맞춤
- contain : 비율을 유지, 요소의 더 짧은 너비에 맞춤

> background-attachment
> 사용법 ex) background-attachment: fixed;

: 요소의 배경 이미지 스크롤 특성

- scroll : (기본값) 이미지가 요소를 따라서 같이 스크롤
- fixed : 이미지가 뷰포트에 고정, 이미지가 스크롤되지 않음
- local : 요소 내 스크롤 시 이미지가 같이 스크롤
