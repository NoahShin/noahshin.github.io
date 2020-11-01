---
title: "wecode TIL day 1 (Oct 19)"
date: 2020-10-19
categories: wecode TIL HTML CSS
---

### wecode 첫날, OT & HTML CSS 기초 과제

원래 15기였지만 14기 시작 일주일 전 자리가 비어 앞으로 옮긴 케이스.
4주 사전스터디를 안해서 아쉽고 불안했지만 "하면 되겠지" 라는 마인드로 시작.
은우님의 OT끝에 Repl.it으로 HTML & CSS 기초 과제 시작.내 속도는 많이 느린편이였다.

### 1. HTML = Hypertext Markup Language

웹페이지를 만들기 위한 언어 & 브라우져를 위한 존재, (확장자파일 저장은 꼭 .html로 끝내기)
파일의 신체구조는 항상 아래와 같은 형식

```
<!DOCTYPE>
html
head
body
```

### 2. tag & content & attribute(속성) & element

￼![](https://images.velog.io/images/noahshin__11/post/739c8158-e7bf-4a2b-8ac1-5961622f253f/image.png)

다른 태그는 다 닫아줘야하는데 img, br 같은 태그는 안 닫아도 된다.

**div, a, img는 태그이고
class, href, src, alt는 속성이다.**

#### element (요소)

<태그이름> 요소요소요소요소<태그이름/>
끝 태그가 필요없는 (img) 태그들은 그 자체로 요소가 된다.

```
<!DOCTYPE html> 선언은 내가 HTML5버젼을 사용하겠다~ 라고 브라우져에게 알리는 것

<meta charset="utf-8"> : 한글, 일본어, 중국어가 포함된 페이지라면 utf-8 이라는 값으로 문자 인코딩을 해야한다. (그렇지 않으면 외계어 101 클래스 오픈)
<meta name="viewport" content="width=device-width">: 모바일과 컴퓨터의 절대적 크기가 다르기 때문에 해당 정보를 추가하지 않으면 데스크탑 버전의 웹페이지가 축소되어 보이는 현상이 나타납니다.

<h1>, <h2>, <h3>, <h4>, <h5>  숫자가 클수록 작아진다.
<span> 한줄에 이어서 나오는 inline-element
<p> 문단-> 줄바꿈이 일어남
<div> 디비젼
<a> 링크 걸로 싶을때,  (example) <a href="https://www.noah_shin_is_awesome" target="_blank">a 태그?</a>
위 중에 target=“_blank” 하면 지금 tab을 놔두고 새 tab으로 뜬다.

id = “  “ 단 하나밖에 못가진다.
class = “ “ 여러태그에 중복될 수 있는 이름
여러 속성 추가할수 있음
<div id="profile" class="content-wrap"></div>
```

## CSS (Cascading Style Sheets)

CSS란 뼈대만 있는 HTML에게 옷을 입혀주는 것

**대신 어느 css파일인지 브라우저에 알려야 하므로 링크를 해주는 태그를 추가한다.(필수)**

```
<link href="index.css" rel="stylesheet" type="text/css" />
```

1. **link ** — link 태그로 css파일 링크
2. **href** — href 속성에 css 파일 경로 작성
3. **type** — 어떤 파일인지 알려준다. css file의 type값은 항상 "text/css"
4. **rel** — rel은 HTML file과 CSS file과의 관계를 설명하는 속성. **css파일을 링크할 때는 항상 "stylesheet"값을 대입.(필수)**
   ￼![](https://images.velog.io/images/noahshin__11/post/e1268a57-8924-4d3b-8ca6-13a340ae5080/image.png)

#### \*\*class 는 .클래스이름

#### id 는 #아이디이름

#### 없으면 태그이름 그냥 쓴다.\*\*

### 텍스트 정렬

property 이름은 text-align이고 값은 left, center, right
￼![](https://images.velog.io/images/noahshin__11/post/09faa323-92f6-4b79-a014-de91e074d654/image.png)

Text - indent 들여쓰기 기능, 에세이 쓸 때 Tab 기능
￼![](https://images.velog.io/images/noahshin__11/post/92c691f6-19e2-44d4-ad29-42fcfcf6e399/image.png)

이건 스페이스 바

```
 &nbsp;
```

위 코드 하나당 스페이스 하나

```
<p>스페이스 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;넣는 예제</p>
```

위 출력값 >>> 스페이스 넣는 예제

### Margin 과 Padding

￼![](https://images.velog.io/images/noahshin__11/post/14a15270-8ab0-4cca-8011-7f5b0c6fa889/image.png)
￼![](https://images.velog.io/images/noahshin__11/post/0593439f-6398-4d19-858f-f70febd674c4/image.png)
**패딩도 위와 같음!**
￼![](https://images.velog.io/images/noahshin__11/post/f4df56a4-a2b3-48fd-80e1-7bffd4f7aab2/image.png)
**보더 꾸밀때 코드 순서**
dotted & dashed & solid & double & groove & ridge & inset & outset <<<보더 꾸미는 종류, 하지만 안 외워도 된다.

** 중요포인트! 상자에 밑줄 긋고 싶을때 underline 하는게 아니가 border-bottom으로 꾸민다.**

### Box-sizing

보더를 꾸밀 때 가로를 300px 라고 지정하여도 보더나 패딩이 추가가 되면 원하는 데로 안 나올 경구가 있다. 디자인 시안에는 컴포넌트의 가로값만을 알 수 있는데, 이때 충돌을 막기 위해 CSS property가 개발 되었다.
￼![](https://images.velog.io/images/noahshin__11/post/a290cbf7-61f9-427f-a4e9-60346ae329fc/image.png)
편-안

#### 그래서 거의 대부분의 웹페이지에 box-sizing 프로퍼티를 기본적으로 적용한다고 한다.

### 일일히 태그마다 적용하기에는 코드가 길어지기에 아래와 같은 "\*" selector로 적용한다.

￼![](https://images.velog.io/images/noahshin__11/post/0ea916e5-7720-4820-8480-45e1e5c4d5f8/image.png)

### 상속(Inheritance)

위쪽 클래스에 아무리 색깔이 검정이라 하여도 나도 color 코드 화이트를 가지고 있으면 난 화이트이다.

### 그룹(Grouping)

￼![](https://images.velog.io/images/noahshin__11/post/b0fbcff4-8986-461a-860e-e2659af92492/image.png)

### CSS Selector

￼![](https://images.velog.io/images/noahshin__11/post/bf94bf55-0ef5-4509-aea1-ee9bfc949b9f/image.png)
class나 id가 selector일때 태그와 결합할 수 있습니다.

첫 번째는 p태그이면서 p-tag class이다.
두 번째는 p태그이면서 third-line id이다.
￼![](https://images.velog.io/images/noahshin__11/post/e9ef91b9-5011-4d88-bfc1-124b0ddffb48/image.png)
위 내용은 pre클래스 내부에 있는 span 이라는 뜻이다.

### img 태그로 이미지 넣기

- **alt**: 이미지가 서버에서 이미지가 삭제됐거나 잘못된 이미지 주소일 때, 이미지 대신 보여줄 텍스트
- **src**: 이미지 파일 경로 or 이미지 url 주소

#### CSS 이미지 가로 사이즈

css에 가로만 지정하면 원본의 세로 값은 그대로 남아있는 것이 아니라, 가로 지정한 비율에 맞춰서 세로도 알맞게 줄어들었습니다. 가로/세로 중에서 하나의 값만 입력해도 브라우저에서 알아서 같은 비율로 나머지 크기도 줄여준다.

### 레이아웃

block 요소일 때 width 값을 주면 더이상 늘어나지 않고, margin에 auto로 설정하면 가로 중앙에 오게 할 수 있다.
￼![](https://images.velog.io/images/noahshin__11/post/eda7d348-86e6-433d-94d9-4ab6f949d7bd/image.png)

위 사진 내용: Margin 위아래 20px 좌우 가운데

### 리스트

￼![](https://images.velog.io/images/noahshin__11/post/c6b3e955-444b-458a-bdc6-dd3fdf00d122/image.png)
￼![](https://images.velog.io/images/noahshin__11/post/d1dfb730-07e3-4b38-9422-42d3ba6162ae/image.png)
￼![](https://images.velog.io/images/noahshin__11/post/41c325c1-af71-417c-a27c-83fa398011f5/image.png)
￼![](https://images.velog.io/images/noahshin__11/post/c5d9c474-d19b-45fc-9cfc-53d462529451/image.png)
**리스트 앞에 아무것도 넣기 싫다고 li태그만 사용하면 안된다. 목록은 항상 ul이나 ol태그로 감싸야 한다.
(list-style: none; 이러면 점이나 숫자 사라짐)**

￼![](https://images.velog.io/images/noahshin__11/post/f5e32564-7e19-4112-81da-46703e1c0cd9/image.png)
￼![](https://images.velog.io/images/noahshin__11/post/7558522e-b531-48a9-8247-b79491048957/image.png)
리스트가 1억개라고 상상하면 그걸 하나하나 클래스를 지정하기가 어려울 때 쓰는 코드.
첫 번째 사진은 리스트에서 마지막 리스트 패딩바텀을 0으로 지정.
두 번째 사진은 리스트의 홀수와 짝수의 색 변경.
