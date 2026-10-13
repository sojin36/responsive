📱 CSS 반응형 웹과 @media

1. 📌 오늘 배운 내용

오늘은 CSS의 @media를 활용한 반응형 웹에 대해 배웠다.

반응형 웹이란?
PC, 태블릿, 모바일 등 사용하는 기기의 화면 크기에 맞춰 웹사이트의 레이아웃과 디자인이 변하는 웹을 의미한다.

예를 들어 PC에서는 메뉴를 가로로 배치하고, 모바일에서는 세로로 배치할 수 있다.

2. 💡 @media란?

@media는 특정 조건에 따라 서로 다른 CSS 스타일을 적용할 수 있도록 해주는 CSS 문법이다.

주로 반응형 웹을 만들 때 사용하며, 화면 너비나 방향 등에 따라 디자인을 변경할 수 있다.

기본 문법
@media (조건) {
  /* 조건이 만족될 때 적용할 CSS */
}

@media : 특정 조건에 맞는 CSS를 적용한다.
조건 : CSS를 적용할 기준을 작성한다.
{ } : 조건이 만족될 때 적용할 CSS를 작성한다.

3. 📏 max-width와 min-width
① max-width

화면 너비가 지정한 값 이하일 때 CSS를 적용한다.

@media (max-width: 600px) {
  h1 {
    font-size: 20px;
  }
}


화면 너비가 600px 이하라면 제목의 글자 크기가 20px로 변경된다.

② min-width

화면 너비가 지정한 값 이상일 때 CSS를 적용한다.

@media (min-width: 601px) {
  h1 {
    font-size: 32px;
  }
}


화면 너비가 601px 이상이라면 제목의 글자 크기가 32px로 변경된다.

속성	의미	예시
max-width	지정한 너비 이하	600px 이하
min-width	지정한 너비 이상	601px 이상

※ max-width는 최대 너비, min-width는 최소 너비를 기준으로 한다.

4. 🖥️ 화면 크기에 따라 스타일 변경하기

화면 크기에 따라 요소의 너비와 배경색을 변경할 수 있다.

.box {
  width: 500px;
  height: 200px;
  background-color: skyblue;
}

@media (max-width: 600px) {
  .box {
    width: 100%;
    background-color: pink;
  }
}

코드 설명
기본 상태에서는 상자의 너비가 500px이고 배경색은 하늘색이다.
화면 너비가 600px 이하가 되면 상자의 너비가 부모 요소의 100%로 변경된다.
이때 상자의 배경색도 분홍색으로 변경된다.
height는 별도로 변경하지 않았으므로 기존 200px이 유지된다.

이처럼 @media를 사용하면 화면 크기에 맞춰 디자인을 다르게 설정할 수 있다.

5. 📐 Flex와 @media 함께 사용하기

@media는 flex와 함께 사용하면 화면에 따라 요소의 배치를 변경할 수 있다.

HTML
<div class="menu">
  <div>홈</div>
  <div>소개</div>
  <div>문의</div>
</div>

.menu {
  display: flex;
  gap: 20px;
}

@media (max-width: 600px) {
  .menu {
    flex-direction: column;
  }
}

결과
PC 화면: 메뉴가 가로로 배치된다.
화면 너비가 600px 이하: 메뉴가 세로로 배치된다.

display: flex는 요소를 유연하게 배치할 수 있도록 해주며, flex-direction: column은 요소를 세로 방향으로 배치한다.

6. 🖨️ @media는 반응형에만 사용될까?

@media는 반응형 웹뿐만 아니라 다양한 환경에서도 사용할 수 있다.

인쇄할 때 버튼 숨기기
@media print {
  button {
    display: none;
  }
}


웹페이지를 인쇄할 때 버튼이 표시되지 않도록 설정할 수 있다.

화면 방향에 따라 스타일 변경하기
@media (orientation: landscape) {
  h1 {
    color: red;
  }
}


화면이 가로 방향일 때 제목의 글자색을 빨간색으로 변경한다.

7. ✅ 오늘의 핵심 정리
반응형 웹은 화면 크기에 따라 레이아웃과 디자인이 변경되는 웹이다.
@media는 특정 조건에 따라 CSS를 적용하는 문법이다.
max-width는 지정한 너비 이하일 때 적용된다.
min-width는 지정한 너비 이상일 때 적용된다.
@media는 화면 크기뿐만 아니라 인쇄 환경이나 화면 방향에도 사용할 수 있다.
flex와 @media를 함께 사용하면 화면 크기에 따라 요소의 배치를 변경할 수 있다.

📝 오늘 배운 점

오늘은 CSS의 @media를 통해 화면 크기에 따라 스타일을 변경하는 방법을 배웠다.

처음에는 max-width와 min-width의 차이가 헷갈렸지만, 각각 지정한 너비 이하와 이상을 의미한다는 점을 이해했다.

또한 @media가 반응형 웹뿐만 아니라 인쇄 환경이나 화면 방향에 따라서도 CSS를 다르게 적용할 수 있다는 것을 알게 되었다.

앞으로 다양한 화면 크기에서 직접 테스트하면서 반응형 웹을 구현하는 연습을 해야겠다.

#CSS #반응형웹 #MediaQuery #Frontend #WebDevelopment