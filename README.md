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

