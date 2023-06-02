css는 화면을 꾸며주는 것이므로,
code가 화면에 어떻게 그려질지 상상하는 것이 중요하다.

`reset. css`
브라우저의 기본적인 세팅을 초기화하고 css해야한다.

- 구글에 reset. css 검색 후 HTML 을 복사후 head의 title 밑에 붙여넣는다.

```
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Overwatch</title>
    👉 <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.main.css" />
    (*title밑에 붙여넣기)
    <link rel="stylesheet" href="./main.css" />
    (그 밑에는 파일 연결하는 순서이다.)
```

<br>

# 📌 표현 단위

- px
  픽셀
  기본 font 크기: 16px 이다.

- %
  상대적 백분율
  부모요소에 영향을 받아 자식요소는 부모 요소 값의 %로 나타난다.

- em
  요소의 글꼴 크기
  글꼴마다 크기가 상대적이다.
  ❓❓❓❓❓
  글꼴의 크기인데 왜 font-size에다가 적용하지 않고(예시 font-size: 20em;)
  width값에 적용시키나???
  (rem도 마찬가지)

- rem
  루트요소(html)의 글꼴 크기
  루트요소: 최상위 요소(html)

- vw
  뷰포트 가로너비의 백분율
  뷰포트: 브라우저 화면에 표시되는 페이지의 전체 영역
  예시)
  50vw;는 화면의 가로비율을 줄이면 줄인만큼의 50%가 줄어든다.
  왔다갔다 줄였다가 늘리면 계속 화면의 50%만큼 줄었다가 늘어나며 유동적으로 변한다.

- vh
  뷰포트 세로 너비의 백분율
  <br>

# 🔎 width, height

> 가로와 세로의 너비

`auto` (기본값)

- 브라우저가 **자동**으로 너비를 계산해준다.
- 기본값으로 설정되어 있어 값을 입력하지 않아도 자동으로 계산해준다.
- 선택자에 따라 자동계산되는 값은 선택자를 따른다.

선택자에 따라 달라지는 자동 계산 예시)

- span은 인라인 요소로 딱! 콘텐츠의 크기 만큼만 나타난다.
  (크기가 콘텐츠 크기만큼 줄어듬)
  (가로: 줄어듬 / 세로: 줄어듬)

- div는 블록 요소이므로 가로사이즈가 최대로 늘어난다.
  (가로: 늘어남 / 세로: 콘텐츠 크기만큼 줄어듬)

`단위`

- 단위에는 px, em, vw등의 단위로 크기를 지정한다.
- 정확한 단위를 기재하고 싶을 때 사용한다.
- px픽셀 단위가 주로 사용된다.

```
div {
  width: 100px;
}

해석👉 div에 스타일을 적용시켜주며, {가로는: 100px이다;}
 (세로는 입력하지 않았으므로 자동계산되어 나타난다. = height: auto;)
```

# 🔎 max-width, max-height

> 커질 수 있는 **최대** 가로/세로 너비

- 부모요소에게 영향을 받지 않게 된다.

<br>

`none` (기본값)

- 최대너비 제한 없음

`단위`

- px, em, vw 등 단위로 지정한다.

<br>

# 🔎 min-width, min-height

> 작아질 수 있는 **최소** 가로/세로 너비

- 부모요소에게 영향을 받지 않게 된다.

<br>

`0`

- 최소 너비 제한 없음
- 0은 숫자를 입력할 필요 없다.

`단위`

- px, em,vw 등 단위로 지정한다.
  <br>

# 🔎 margin

> 요소의 **외부 여백**(공간)을 지정하는 **단축 속성💡**

-음수를 사용할 수 있다. `-` -음수를 사용할 경우 요소가 겹쳐지게 될 수도 있다. -단축속성으로 상하좌우 값을 모두 다르게 입력가능하다.

`0` (기본값)

- 외부 여백 없음

`auto`

- 브라우저가 여백을 계산
- 가로(세로) 너비가 있는 요소의 가운데 정렬에 활용한다.

`단위`

- px, em,vw 등 단위로 지정한다.

---

_**💡 아래의 특징이 다른 단축속성에도 동일하게 적용된다.**
( 단축 속성일 경우에만 적용가능 )_

---

`📍 top, right, bottom, left`
: 위, 오른쪽, 아래, 왼쪽의 모든 방향에 외부여백을 줄 수 있다.

**1. margin뒤에 방향을 입력하여 외부여백을 주기**

- margin-top
- margin-right
- margin-bottom
- margin-left

**2. margin 값을 방향 순서대로 입력하여 외부여백 주기**

-꼭 순서를 지켜서 값을 입력해야 한다. -순서는 시계방향 순서이다. -값은 최대 4개까지 입력가능하다.

- **모든 방향**: 값을 하나만 입력
  예) `margin: 10px;`

- **상하, 좌우**: 순서대로 2개의 값 입력
  예) `margin: 10px 20px;`
  👉`margin: 10px(상하여백) 20px(좌우여백);`

- **상, 중, 하**: 순서대로 3개의 값 입력
  예) `margin: 10px 20px 30px;`
  👉`margin: 10px(위) 20px(좌우) 30px(아래);`

- 상하좌우값이 모두 다른 여백일 때는 **시계방향 순서**대로 입력
  예) `margin: 10px 20px 30px 40px;`
  👉`margin: 10px(위) 20px(오른쪽) 30px(아래) 40px(왼쪽);`

---

<br>

# 🔎 padding

> 요소의 **내부 여백**(공간)을 지정하는 **단축 속성💡**

-내부에 여백이 생기면서 요소의 크기가 커진다.
(요소+내부여백 = 커짐)

-단축속성으로 상하좌우 값을 모두 다르게 입력가능하다.

`0` (기본값)

- 내부 여백 없음

`단위`

- px, em,vw 등 단위로 지정한다.

`%`

- 부모요소의 가로너비에 대한 비율로 지정한다.
  <br>

# 🔎 border

> 요소의 **테두리 선**을 지정하는 **단축 속성**💡

-요소의 크기가 커진다.
(요소+테두리 = 커짐)

💡 **단축 속성**
border: 선두께 선종류 선색상;
위의 순서대로 입력하는 것을 권장한다.

(기본값) `border: medium none black;`

#### 📍 `borser-width` 선 두께

- 단위 : px, em, %등 단위로 지정한다.

- 단축속성으로 시계방향대로 값을 입력하면 상,우,하,좌의 두께를 입력할 수 있다.
  예) border-width: 10px 20px 30px 40px;

#### 📍 `border-style` 선 종류

- none: (기본값) 선 없음
- soild: 실선 (일반 선)
- dashed: 파선(끊어진 선/점선이 길게된 선)
  등이 있지만, 그 외는 잘 사용되지 않는다.
- dotted: 점선(점으로 된 선)

- **단위속성으로 상하좌우에 모두 다른 스타일을 적용**할 수 있다.

#### 📍 `border-color` 선 색상

- black: (기본값) rjawjdtor
- 색상: 선의 색상 입력
- transparent: 투명
- **단위속성으로 상하좌우에 모두 다른 컬러를 적용**할 수 있다.

**👉 색상표현**
`색상이름`
브라우저 제공 색상 이름
red, tomato, royalblue

`16진수 색상`
Hex 색상코드
#000, #FFFFF

`RGB`
빛의 삼원색
rgb(0,0,0,0.5)

`RGBA`
빛의 삼원색 + 투명도
투명도: 0~1 (0: 투명 / 1: 불투명)
rgba(0,0,0,0.5)

등 으로 색상을 표현한다.

#### 📍 `border-방향 / border-방향-속성`

- border-top: 두께 종류 색상;
- border-top-width: 값;
- border-top-style: 값:
- border-top-color: 값;
  등 으로 사용할 수 도 있다.
  <br>

# 🔎 border-radius

> 요소의 모서리를 둥글게 깎는다.

특정한 모서리만 깎이게도 할 수 있다.

❔ 어떻게 둥글게 깎을까?

1. 모서리에 원을 둔다.
2. 원의 반지름만큼 둥글게 깎인다.

`0` (기본값)
둥글게 깎지 않는다.

`단위`
px, em, ve등의 단위로 지정한다.

`특정 모서리만 깎기`
시계방향대로 모서리 순서를 지정한다.
border-radius: 0 10px 0 0;

<br>

# 🔎 box-sizing

> **크기 계산 기준**을 지정한다.

padding(내부여백), border(테두리)로 인한 크기 변화를
안일어나게 할 수 있다.
예) `box-sizing: border-box;`
<br>

`content-box` (기본값)

- 요소의 내용(content)으로 크기 계산
- 크기 변화 X,
  요소 변화를 안일어나게 하려면 수동으로 계산해야한다.
  (padding, border만큼 크기가 늘어난다.)

`border-box`

- 요소의 내용 + padding + border로 크기 계산
- padding, border를 사용해도 크기가 커지지 않게 한다.

<br>

# 🔎 overflow

> 요소의 크기 이상으로 **내용이 넘쳤을때,** 보여짐을 제어하는 **단축속성**💡

부모요소에 작성하면,
자식요소에 잘린 요소를 숨겨준다.

`visible` (기본값)
넘친 내용을 그대로 보여줌

`hidden`
넘친 내용을 숨김

`auto`
넘친 내용이 있는 경우에만 잘라내고 그 부분만 스크롤바 형성
(`scroll`을 이용하면 x,y축 모두 스크롤바가 형성된다. - 잘사용X)
<br>
💡 개별 속성
`overflow-x`
x축으로 넘치는 부분만 숨긴다.

`overflow-y`
y축으로 넘치는 부분만 숨긴다.

<br>

# 🔎 display

> 화면 출력(보여짐) 특성

📍 <각 요소에 이미 지정되어 있는 값들>

`block`
상자(레이아웃) 요소
예) div

`inline`
글자요소
예) span

`inline-block`
글자 + 상자 요소

`기타`
table, table-row, table-cell 등

🔻 사용 예시

```
[CSS]
span {
  width: 120px;
  height: 30px;
  background-color: yellow;
}
👉span은 인라인 요소이므로, 가로/세로 넓이를 지정할 수 없다.
이때, 블록 요소로 변경하고 싶으면 display를 이용하면 된다. (아래 예시처럼)


span {
  display: block;
  width: 120px;
  height: 30px;
  background-color: yellow;
}
👉display: block; (화면에: 블록요소로 보여지게한다.;)의 css를 넣어줌으로써
가로/세로의 값을 가질 수 있게 된다.
```

<br>

📍 <따로 지정해야 하는 값들>
`flex`
플렉스 박스 (1차원 레이아웃)

`grid`
그리드 (2차원 레이아웃)

`none`
보여짐 특성 없음
= 화면에서 안보임
<br>

---

# 📍 flex

flex는 1차원 레이아웃을 말한다.
차원: x, y축

- 부모 요소에 `display: flex;`를 적용하면, **Flex Container**가 되고,
  그 자식 요소는 **Flex Items**가 된다.
  이때, 자식 요소가 수평정렬되게 된다.
- 💡 Flex container와 Flex Items에 사용되는 속성은 서로 다르다.
  <br>

### 📍 Flex Container

> `display: flex;`가 적용된 요소를 말한다. (또는 line-flex)

#### `display: flex;`

- 블록 요소처럼 적용된다.
- 수평 정렬

#### `display: inline-flex;`

인라인 요소처럼 적용된다.

# 🔎 flex-direction

> 주 축을 설정한다. (수평과 수직 정렬)
> 💡 Flex Container에 사용되는 속성

`row` (기본값)

- 수평정렬
  행 축
  (좌 -> 우)
  (왼쪽이 start / 오른쪽이 end)

`row-reverse`

- 수평정렬
  행 축
  (우 -> 좌)
  (오른쪽이 start / 왼쪽이 end)

`column` (block 요소가 수직정렬이므로 잘 쓰이지X)

- 수직정렬
  열 축
  (위 -> 아래)

<br>

# 🔎justify-content

> 주 축의 정렬 방법 (수평)
> 💡 Flex Container에 사용되는 속성

`flex-start` (기본값)

- flex-items를 시작점으로 정렬

`flex-end`

- flex-items를 끝점으로 정렬

`center`

- flex-items를 가운데 정렬

<br>

# 🔎align-content

> 교차 축의 여러 줄 정렬 방법 (수직)
> 💡 Flex Container에 사용되는 속성

`stretch` (기본값)

- flex-items를 시작점으로 정렬

`flex-start`

- flex-items를 시작점으로 정렬

`flex-end`

- flex-items를 끝점으로 정렬

`center`

- flex-items를 가운데 정렬

<br>

# 🔎align-items

> 교차 축의 한 줄 정렬 방법 (수직)
> 💡 Flex Container에 사용되는 속성

`stretch` (기본값)

- flex-items를 교차 축으로 정렬

`flex-start`

- flex-items를 각 줄의 시작점으로 정렬

`flex-end`

- flex-items를 각 줄의 끝점으로 정렬

`center`

- flex-items를 각 줄의 가운데 정렬

<br>

# 🔎flex-wrap

> flex items 묶음(줄바꿈) 여부
> 💡 Flex items에 사용되는 속성

nowrap상태로 냅두면 flex로 수평정렬을 하였다가 해당되는 공간안에 요소들이
수평으로 정렬이 안될 경우
요소들이 찌부되어 표현이 된다.
이러한 현상을 원치 않을 경우 wrap으로 요소들을 내려(줄바꿈)줄 수 있다.

`nowrap` (기본값)

- 묶음(줄바꿈) 없음

`wrap`

- 여러 줄로 묶음

# 🔎order

> flex items의 순서
> 💡 Flex items에 사용되는 속성

`0` (기본값)
순서없음

`숫자`
숫자가 작을 수록 먼저 온다.

<br>

# 🔎flex-grow

> flex items의 증가 너비 비율
> 💡 Flex items에 사용되는 속성

`0` (기본값)
증가 비율 없음

`숫자`
증가 비율

<br>

# 🔎flex-shrink

> flex items의 감소 너비 비율
> 💡 Flex items에 사용되는 속성

`1` (기본값)
flex container 너비에 따라 감소 비율 적용

`숫자`
감소 비율

<br>

# 🔎flex-basis

> flex items의 공간 배분 전 기본 너비
> 💡 Flex items에 사용되는 속성

`auto` (기본값)
요소의 content 너비

`단위`
px, em, rem등 단위로 지정

<br>

---

# 🔎 opacity

> 투명도

`1`
불투명

`0~1`
0부터 1사이의 소수점 숫자
이때 소수점 앞에 있는 0은 생략가능하다.

`0`
투명

```
opacity: 0.07;
👉7%

opacity: 0.5;
👉50%

opacity: 0.7;
👉70%

opacity: 1;
👉100% (불투명)

```

<br>

---

#### 📍 글꼴

# 🔎 font-style

> 글자의 기울기

`normal` (기본값)
기울기 없음

`italic`
이텔릭체

# 🔎 font-weight

> 글자의 두께(가중치)

`nomail` `400` (기본값)
기본 두께

`bold` `700`
두껍게

`100~900`
100단위의 숫자 9개,
normal과 bold 이외 두께

# 🔎 font-size

> 글자의 크기

`16px` (기본값)
기본 크기

`단위`
px, em, rem 등 단위로 지정

# 🔎 line-height

> 한 줄의 높이 (행간과 유사)

`normal` (기본값)
단위가 있지 않다.

`숫자` -요소의 글꼴 크기의 배수로 지정
(폰트 사이즈의 Xn배)

-폰트 사이즈가 달라져도 한 줄의 높이가 높아진다.

-%보다 숫자 사용을 권장

`단위`
px, em, rem 등 단위로 지정

# 🔎 font-family

> 글꼴(서체) 지정

`font-family: 글꼴1, "글 꼴2", ... 글꼴계열;`

- 띄어쓰기 등 특수문자가 포함된 글꼴 이름은 ""큰따옴표로 묶어야 한다.
- 맨 마지막에 글꼴 계열은 필수로 작성하여야 한다.
- 여러 글꼴을 작성할때는 , 쉼표로 구분해주어야 한다.
  <br>

👉 글꼴을 여러개 작성하는 이유

- 글꼴이 적용이 안될 수 있다.
- 가장먼저 작성된 글꼴을 우선 사용하되,
  적용이 안되면 그 다음 글꼴을 사용한다.
  <br>

**📍 글꼴 계열**

`serif`
바탕체 계열
(뻗침이 있는 글꼴)

`san-serif`
고딕체 계열
(깔끔한 글꼴)

`monospace`
고정너비 글꼴 계열
(가로폭이 동등)

...등
<br>

---

#### 📍 문자

별 의미 없는 긴 문장이 필요할 경우
(https://www.lipsum.com)으로 접속하면 작성된 문장을 사용가능하다.

# 🔎 color

> 글자의 색상

`rgb(0,0,0)` (기본값)
검정색

`색상`
기타 지정가능한 색상

# 🔎 text-align

> 문자의 정렬방식

`left` (기본값)
왼쪽 정렬

`right`
오른쪽 정렬

`center`
가운데 정렬

# 🔎 text-decoration

> 문자의 선(장식)

`none` (기본값)
장식 없음

`underline`
밑줄

`line-through`
중앙 선

# 🔎 text-indent

> 문자의 첫 줄을 들여쓰기

음수를 사용하여
반대로 내어쓰기(outdent)를 쓸 수 있다.
<br>

`0` (기본값)
들여쓰기 없음

`단위`
px, em, rem 등 단위로 지정한다.
<br>

---

#### 📍 배경

# 🔎 background-color

> 배경 색상

`transparent` (기본값)
투명함

`색상`
지정 가능한 색상

# 🔎 background-image

> 배경 이미지 삽입

`none` (기본값)
이미지 없음

`url`
이미지 경로
사용 예) background-image: url("경로 입력")

# 🔎 background-repeat

> 배경 이미지 반복

`repeat` (기본값)
이미지를 수직, 수평으로 반복

`no-repeat`
반복 없음

`repeat-x`
이미지를 수평으로만 반복

`repeat-y`
이미지를 수직으로만 반복

# 🔎 background-position

> 배경 위치

`방향`

- top, bottom, left, right, center 방향
- 방향에서는 위치 순서가 상관없다.

```
background-position: top right;

해석👉 배경 이미지의 위치는: 위, 오른쪽에 위치한다.;
(right와 top의 순서를 바꿔도 상관없다.)
```

`단위`

- px, em, rem등 단위로 지정
- **x,y축을 지정** 할 수 있다.
  💡 css에서의 x,y축
  x축(가로)은 왼쪽에서 오른쪽으로 진행되며,
  y축(세로)은 위에서부터 아래로 내려온다.

```
background-position: 100px 30px;

해석👉 배경 이미지의 위치는: x축에서 100px떨어져 있고, y에서 30px 떨어진 곳에 위치한다.;
(x축 100px = 오른쪽으로 100px이동
 y축 30px = 아래로 30px이동)
```

# 🔎 background-size

> 배경 이미지 크기

`auto` (기본값)
이미지의 실제 크기

`단위`
px, em,rem 등 단위로 지정

`cover`
비율을 유지하고,
이미지의 더 넓은 너비에 맞춘다.

`cintain`
비율을 유지하고,
이미지의 더 짧은 너비에 맞춘다.

# 🔎 background-attachment

> 배경이미지 스크롤 특성

`scroll` (기본값)
이미지가 화면을 따라서 같이 스크롤

`fixed`
이미지가 뷰포트에 고정된다.
(스크롤X)
<br>

---

#### 📍 배치

# 🔎 position

> **위치 지정 기준**을 잡아준다.

**position과 함께 사용되는 속성들**
👉 top, bottom, left, right, z-index

- 이 속성들은 모두 음수를 사용할 수 있다.
- 단위 : px, em, rem 등으로 단위를 지정한다.

```
🔻 사용 예시
position: relative;
top: 100px;
right: -30px;
```

<br>

`static` (기본값)
기준없음

`relative`
**자기(요소) 자신**을 기준으로 배치된다.

- 💡 배치를 위한 position: relative; 는 거의 사용하지 XXX !!!
- 기존에 원래 있던 자리에서 이동된다.
- 배치 전, 기존 자리는 시각적으로만 비어있다. (비정상적인 출력구조)
- 이동된 요소는 허상이 된다. (비정상적인 출력구조)
  <br>
- 💡 위치상 **부모 요소로 지정**하는 position: relative; 용도로 주로 사용한다.
- 위치상 부모 요소로 지정하고 싶을 때 사용하며,
  top, bottom, left, right등 을 입력하지 않으면 부모요소로 지정이 된다.

`absolute`
**위치 상** **부모**요소를 기준으로 배치된다.

- **위치상** 부모 요소를 꼭! 확인해야 한다.
- 자식요소와는 상호작용하지 않게 된다.
- 위치상 부모 요소가 없으면, 뷰포트가 기준이 된다.

`fixed`
**뷰포트**(브라우저)를 기준으로 배치된다.

- 주변 자식요소와 상호작용하지 않게 된다.
- 뷰포트가 길어서 스크롤로 화면을 내리면,
  뷰포트를 기준으로 배치되었으므로,
  **화면을 내려도 그 자리에 그대로 배치**되어 보이게 된다.
  (메뉴바, 베너 등에 활용)
  <br>

```
🔻 예시
  (absolute값을 써도 뷰포트가 기준이 되는 경우)
.container {
  width: 300px;
  background-color: royalblue;
}
.container .item {
 background-color: orange;
}
.container .item:nth-child(1) {
  width: 100px;
  height: 100px;
}
.container .item:nth-child(2) {
  width: 140px;
  height: 70px;
  position: absolut;
  bottom: 30px;
}
해석👉 위치상 부모요소(position: relative;)를 부여해주지 않아서,
       부모요소가 없으므로,
       position: absolut;를 부여해준 2번째 요소는
       뷰포트를 기준으로 배치된다.


🔻 예시
  (relative로 부모요소를 부여해준 경우)
.container {
  width: 300px;
  background-color: royalblue;
  position: relative;
}
.container .item {
 background-color: orange;
}
.container .item:nth-child(1) {
  width: 100px;
  height: 100px;
}
.container .item:nth-child(2) {
  width: 140px;
  height: 70px;
  position: absolut;
  bottom: 30px;
}
해석👉 .container에 relative를 부여하여 부모요소를 만들어주었다.
       2번째 요소는 .container를 기준으로 위치가 이동한다.
```

---

## 💡 요소 쌓임 순서 (stack order)

> 어떤 요소가 사용자와 더 가깝게 있는지(위에 쌓이는지) 결정

💡 **위에 쌓이는 순서**

1. 요소에 position 속성의 값이 있는 경우 위에 쌓인다. (기본값인 static 제외)
   👉 position 속성과 값 : `position: relative;` `position: absolute;` `position: fixed;`
2. 1번 조건이 같은 경우, z-index 속성의 숫자 값이 높을 수록 위에 쌓인다.
3. 1번과 2번 조건까지 같은 경우, HTML의 구조가 나중에 작성 될 수록 위에 쌓인다.

**요약**

1. position 속성 값
2. z-index
3. HTML 구조

```
🔻 예시1
[CSS]
.container .item:nth-child(1) {
  position: relative;

}
.container .item:nth-child(2) {
  position: absolute;

}
해석👉 이경우, 1번째와 2번째 모두 position 값이 부여가 되었으므로,
       [💡 위에 쌓이는 순서]의 1번은 동일하다,
       그리고 x-index가 없으므로 2번도 동일,
       HTML의 구조상 2번째가 나중에 작성이 되었으므로,

       결국 2번째가 가장 위에 쌓인다.


🔻 예시2
.container .item:nth-child(1) {
  position: relative;
  z-index: 1;

}
.container .item:nth-child(2) {
  position: absolute;

}
.container .item:nth-child(3) {
  z-index: 2;

}

해석👉 3번째는 position이 부여되지 않았으므로, 가장 마지막이며
       1과 2는 position이 모두 있으므로 동일,
       1에서 z-index가 쓰였으므로

       1번 -> 2번 -> 3번 순서로 쌓인다.
```

📍 `z-index`

> 요소의 쌓임 정도를 지정한다.

`auto` (기본값)
= 0
부모 요소와 동일한 쌓임 정도

`숫자`

- 숫자가 높을 수록 위에 쌓인다.
- 뒤에 배치하고 싶을 경우엔, 음수도 쓰이지만 잘 쓰이진 않는다.
- 숫자가 아무리 높아도,
  position값이 부여되지 않았다면, position 뒤에 쌓인다.
- 숫자는 1씩 높여가며 관리해 주어야 좋다.
  (z-index: 999; 처럼 사용하지X)

<br><br>

#### **💡 display의 속성이 block으로 변경되는 경우**

position 속성의 값으로 absolute, fixed가 지정된 요소는 (relative는 제외)
자동으로 display가 블록으로 변경된다.

---

<br>

# 🔎transition

> 요소의 전환(시작과 끝) 효과를 지정하는 단축 속성

`transition: 속성명 지속시간 타이밍함수 대기시간;` \*지속시간은 단축형으로 작성 할 때, 필수 포함 속성이다!

`transform: 변환함수1 변환함수2 변환함수3 ...;`

`transform: 원근법 이동 크기 회전 기울임;`

## 📍 transition-porperty

> 전환 효과를 사용할 **속성 이름**을 지정

`all` (기본값)
모든 속성에 적용

`속성이름`
전환 효과를 사용할 속성 이름 명시

## 📍 transition-duration

> 전환 효과의 **지속시간**을 지정

`0s` (기본값)
전환 효과 없음

`시간`
지속시간(s)을 지정

```
예를 들어 가로길이의 전환은 0.5s로 전환하고
색의 전환은 5s로 전환 하고 싶을 경우 , 를 사용한다.
(transition부분 참고)

[css]
div {
  width: 100px;
  height: 100px;
  background-color: orange;
  transition:
    width ,5s,
    background-color: 2s;
}
div:active {
  width: 3000px;
  background-color: royalblue;

```

## 📍 transition-timing-function

> 전환 효과의 **타이밍 함수**을 지정

`ease` (기본값)
느리게 - 빠르게 - 느리게
cubic-bezier(0.25,0.1,0.25,1)

`linear`
일정하게
cubic-bezier(0,0,1,1)

`ease-in`
느리게 - 빠르게

`ease-out`
빠르게 - 느리게

`ease-in-out`
느리게 - 빠르게 - 느리게

\*구글에 (easing funtions)검색해보고 easing 함수 치트 시트에서 움직임 확인 가능,
(easing funtions mdn)검색하면 css에 적용시킬 수 있는 정보가 나온다.
(tweenmax easing) 검색하면 easing함수를 시각적으로 다루는 페이지를 이용할 수 있다.

## 📍 transition-delay

> 전환 효과가 몇 초뒤에 시작할 지 **대기 시간**을 지정

`0s` (기본값)
대기시간 없음

`시간`
대기시간(s)을 지정

transition에 숫자가 동시에 있을 경우 첫번째가 지속시간 두번째가 대기시간이다
ex) transition: 1s .5s
(지속시간: 1초 / 대기시간 0.5초)

<br>

## 📍 2D 변환함수

perspective 원근법 함수는 제일 앞에 작성되어져야 한다.

`translate(x,y)` 이동 (x축, y축)
`translateX(x)` 이동 (x축)
`translateY(y)` 이동 (y축)
`scale(x,y)` 크기 (x축, y축)

`rotate(degree)` 회전 (각도)
`skewX(x)` 기울임 (x축)
`skewY(y)` 기울임 (y축)

## 📍 3D 변환함수

perspective 원근법 함수는 제일 앞에 작성되어져야 한다.

`perspective(n)` 원근법 (거리)

`rotateX(x)` 회전 (x축)
`rotateY(y)` 회전 (y축)

<br>

# 🔎perspective

> 하위 요소를 관찰하는 원근 거리를 지정

함수의 perspective와는 달리 속성 요소이며, 부모 요소에 위치를 지정한다.
요소에 넣는 함수 사용보다는
부모 요소에 넣는 속성요소를 사용해 주는 것을 권장한다.

```
함수의 perspective 사용법
transfrom: perspective(500px) rotareY(45deg);

속성의 perspective 사용법
perspective: 500px;

```

`단위`
px등 단위로 지정

<br>

# 🔎backface-visibility

> 3D 변환으로 회전된 요소의 뒷면 숨김 여부

`visible` (기본값)
뒷면 보임

`hidden`
뒷면 숨김

뒷면을 숨긴 요소는 화면에 보이지 않는다.
