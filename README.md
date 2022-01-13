# :pushpin: (리액트) 원티드 프리 온보딩 선발 과제
> 원티드 홈페이지 Navbar, Carousel 클론 코딩

>https://wanted-preonboarding-kar.netlify.app/

</br>

## 1. 제작 기간 & 참여 인원
- 2022년 1월 7일 ~ 13일
- 개인 프로젝트

</br>

## 2. 사용 기술
#### `Front-end`
  - React JS
  - Jsx
  - CSS

</br>

## 3. 핵심 기능

<details>
<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">

### 클론 코딩
- 원티드 홈페이지의 상단 부분을 클론 코딩했습니다
- 모바일 / 데스크탑 반응형으로 구현했습니다
  
### Global Nav Bar
- 상단 메뉴 부분을 마크업했고, 기존 홈페이지의 svg 등 소스를 그대로 가져왔습니다
- 과제 조건 상 마크업만 구현했습니다
  
### Carousel
- 총 11장의 배너가 5초에 한번 이동하고, 클릭하거나 마우스로 스와이프 가능하도록 구현했습니다
- 모바일에서는 스와이프 기능이 잘 구현되지 않았습니다

</div>
</details>

</br>

## 4. 디버깅
### 4-1. 핵심 디버깅

```리액트에서 setInterval 사용시 발생하는 이슈```

* 이전 프로젝트에서도 setInterval을 사용하다가 문제가 생겨 setTimeout으로 바꾼적이 있음   
그 부분을 간과하고 이번 과제에 그대로 사용했는데 중간쯤에서 렉이 걸리는 상황이 발생함
* 리액트 프로그래밍 모델과 setInterval의 임피던스 불일치로 인해 생긴 문제
* 참고) https://velog.io/@jakeseo_me/번역-리액트-훅스-컴포넌트에서-setInterval-사용-시의-문제점
* useInterval Hook 을 사용하여 해결함

</br>


### 4-2. 각종 디버깅
<details>
<summary>create-react-app 사용시 문제</summary>
<div markdown="1">

```
You are running `create-react-app` 4.0.3, which is behind the latest release 

(5.0.0).

We no longer support global installation of Create React App.
```

* 버전으로 인한 문제 생김. 재설치한뒤 npx 빼고 사용하니 되었음

</details>

</br>

<details>
<summary>svg 아이콘 입력시 네임스페이스 속성이 지원되지 않는 상황</summary>
<div markdown="1">

* xmlns:xlink -> xmlnsXlink 처럼 JSX와 호환되도록 구문 변환 적용하니 해결

</details>
  
</br>

<details>
<summary>span 관련 css 문제</summary>
<div markdown="1">

* span으로 묶여있는 New(N) 버튼 w와 h가 안 먹어서 고민   
* span은 inline 이라서 안 먹혔던 것. inline-block으로 바꾸니 해결   

</details>
  
</br>

<details>
<summary>조금 어이 없는 실수</summary>
<div markdown="1">

* 캐러셀 슬라이드가 하나씩 나와야하는데 한꺼번에 나온 뒤 5초 후   
동시에 사라지는 현상이 발생.. css 계속 고쳐봤으나 해결이 안되어서   
첫줄부터 반복해서 확인함   

* 알고보니 carousel-conten'n't 로 클래스 네임 주고.. css엔 content로..   
스펠링 실수로 css가 전혀 안 먹혀서 발생한 문제.. 고치니 바로 작동함   
  
</details>

</br>

<details>
<summary>useInterval 작동하며 슬라이드가 밀리는 문제</summary>
<div markdown="1">

* slide에 margin을 줬을 때, 슬라이드가 넘어가면서 점점 한쪽으로 치우치는 문제   
슬라이드가 교체되면서 margin이 점점 늘어나서 생긴 문제인듯 보임   
slide가 아닌 carousel-content에 margin을 줘서 해결

</details>
  
</br>

<details>
<summary>netlify 배포 관련</summary>
<div markdown="1">

* gh-pages로 먼저 배포해보고, 이후 netlify로 배포하고자 했을 때 build.command   
부분 에러가 계속 발생   

```
npm install netlify-cli -g   
netlify deploy
```
로 해결
  
* 이 후 배포는 되었다고 떴지만 화면에 아무 것도 안 뜨는 문제   
homepage 링크가 github으로 되어있어서 netlify url로 다시 설정 후 배포

</details>


## 5. 회고 / 느낀점
> 원티드 선발 과제를 위한 클론 코딩이었는데, 리액트로 프로젝트를 만들어본적은 있지만   
  반응형으로 만들어본건 처음이라 (리액트) 아쉬움이 많았다.   
  JS에 비해 아직 리액트는 덜 익숙하다보니 모바일 퍼스트로 구현하지않고 데스크탑 기준으로   
  먼저 만든 후에 모바일 버전을 다시 추가하려하니 번거로움이 있었다.   
  그리고 기존에는 gh-pages로만 거의 배포를 하다가 netlify로 하다보니 조금은 시간이 걸렸다.   
  그래도 계속 사용하다보니 리액트 Hooks나 배포 등에 조금씩 익숙해지는 느낌인데   
  더 공부하며 연습해야겠다!




