# 20251212

http > 보안 취약 // https > 인증 필요
http = :80
ex) http://127.0.0.1 = http://127.0.0.1:80 
<img width="856" height="477" alt="image" src="https://github.com/user-attachments/assets/7c16961f-f94b-473e-8742-ddb3660e463b" />

URL, URI 차이점?
URL : 위치 주소, URI : 정확한 파일까지
html : 문서와 비슷(word, excel...) css : 디자인 javascript : 앞의 2개 동적 기능 구현
UI / UX

스타일 설정 우선 순위
각 텍스트 태그에 직접 설정> <head>에 스타일 지정> css파일로 스타일 지정
단, !important 입력 시 우선 순위 / 너무 많이 이용 시 헷갈릴 수 있음
상황에 따라 유연하게 지정

ex) p style="padding: 0 30px;"
padding: top right bottom left (시계 방향 순서)
p style="padding: 0 30 0 30;" == p style="padding: 0 30px;"

div
display: block; / inline-block; / flex; / grid; 
float: left; 

예제)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    * {box-sizing: border-box;}
    /* 
    div {width: 100px; height: 100px; border: 1px solid #000;}
    .db {display: inline-block}
    .fl {float: left;} */
    td {height: 100px;}
  </style>
</head>
<body>
  <!-- <div class="db fl">1</div>
  <div class="db fl">2</div>
  <div style="clear: both;">3</div> -->
  <table border="1" style="width: 100%;">
    <tr>
      <td colspan="2"></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td rowspan="2"></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </table>
</body>
</html>

## 1. Flex

`display: flex` 또는 `display: inline-flex`를 지정한 컨테이너 안에서 아이템들을 **유연하게( flexible )** 배치하는 방식입니다.

* 수평/수직 중앙 정렬이 어려움
* 요소 간 간격 일정하게 배치하기 어려움
* 아이템이 넘칠 때 줄바꿈이 어려움
* 레이아웃을 반응형으로 쉽게 만들기 어려움

## 2. Grid

`display: grid` 또는 `display: inline-grid`를 선언한 **부모 요소** 의 Container 안에서 Grid 레이아웃 규칙이 적용됩니다.

### flex : flex-grow (유연하게 늘리기)
'''css
flex-grow: 1;
flex-grow: 0; /* 기본값 */
'''
생각보다 잘 쓰이진 않아 보인다.
flex는 부모 항목 외 자식 항목 정렬할 시 자주 쓰이는 것으로 보인다.

내용 정렬
### Flex : align-items (수직축 방향 정렬)
```css
align-items: stretch;
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;
```

### Flex : align-content (여러 행 정렬). > flex-wrap: wrap; 설정 후 사용
```css
align-content: stretch;
align-content: flex-start;
align-content: flex-end;
align-content: center;
align-content: space-between;
align-content: space-around;
align-content: space-evenly;
```


251212study_04.html
(체스판 배열)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
<style>
    * {box-sizing: border-box;}
    html, body  {margin: 0; padding: 0;}
    /* div {height: 100px;} */
    .body {display: flex; width: 100%; height: calc(100vh/6);}
    .body div {flex-grow: 1;}
    .bg1 {background-color: aqua;}
    .bg2 {background-color: brown;}
</style>
</head>
<body>
    <div class="body">
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
    </div>
    <div class="body">
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
    </div>    
    <div class="body">
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
    </div>
    <div class="body">
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
    </div>    
    <div class="body">
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
    </div>
    <div class="body">
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
        <div class="bg2"></div>
        <div class="bg1"></div>
    </div>    
</body>
</html>

width: 100%, width: 100vw 차이점
<img width="738" height="238" alt="image" src="https://github.com/user-attachments/assets/afa390d8-9a3a-45b8-a456-dc8dbf6db88c" />

# 참고 : height: 100vh를 대신하는 방법
height: 100vh는 뷰포트(브라우저 창)의 높이 전체를 차지하겠다는 의미입니다. 
이를 대체하는 방법은 주로 부모 요소에 따라 달라집니다.A. 부모를 따라 높이 꽉 채우기 (뷰포트 높이와 동일한 효과)100vh는 뷰포트 높이에 고정되지만, 100%는 부모의 높이에 의존합니다. $\text{HTML}$에서 <body>가 뷰포트 전체 높이를 차지하도록 설정하면, 그 자식인 .body는 height: 100%로 $\text{100vh}$와 같은 효과를 낼 수 있습니다.CSS/* 부모 요소(<html>과 <body>)의 높이를 뷰포트 높이와 동일하게 만듦 

*/
html, body {
    height: 100%; /* 또는 height: 100vh; */
    margin: 0;
}

/* 이제 .body는 부모(<body>)의 높이를 꽉 채울 수 있음 */
.body {
    display: flex;
    height: 100%; /* ⬅️ 100vh 대신 100%를 사용하여 동일 효과 */
    /* width: auto; (생략 가능) */
}


B. 콘텐츠에 따라 유동적으로 높이 결정만약 .body가 뷰포트를 꽉 채울 필요가 없고, 내부 콘텐츠의 양에 따라 높이가 유연하게 늘어나도록 하고 싶다면, height: 100vh를 제거하면 됩니다.
CSS 속성설명height: auto; (생략 가능)$\text{div}$의 기본 동작으로, $\text{Flex item}$의 높이를 포함하여 내부 콘텐츠 높이에 맞춰 유동적으로 늘어납니다.

min-height: 100vh; 
콘텐츠가 적을 때는 최소한 뷰포트 높이를 유지하고, 콘텐츠가 많아지면 뷰포트 높이 이상으로 늘어나게 만듭니다. 뷰포트 꽉 채우기 + 콘텐츠 오버플로우 대비에 가장 적합합니다.
💡 가장 강력한 대안: height: 100vh를 대체하면서 내용물의 양에도 유연하게 대처하려면 **min-height: 100vh;**를 사용하는 것이 좋습니다.
