# :pushpin: (리액트) 향수 쇼핑몰
>향수 쇼핑몰 컨셉의 사이트를 리액트로 구현했습니다

>https://wanted-preonboarding-kar.netlify.app/

</br>

## 1. 제작 기간 & 참여 인원
- 2021년 12월 3일
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

### SPA
- 쇼핑몰 컨셉으로 싱글 페이지 어플리케이션을 구현하였습니다   
- 맨 처음 메인 페이지와 캐러셀, 상품들이 뜨고 상단 메뉴바를 클릭하면   
 각 상품 소개 상세 페이지로 연결했습니다

### useState, useEffect
- useState와 useEffect를 사용하여 동적인 기능을 구현했습니다

</div>
</details>

</br>

## 4. 디버깅
### 4-1. 핵심 디버깅

```각 상품들을 map으로 반복시 사진이 저장된 변수가 반복이 안되는 문제```

* 이전에 map으로 반복시에 이미지 src가 주소로 연결이 되었을 때는 문제가 없었는데   
이번에는 로컬에 저장된 사진을 변수에 담아 import하니 반복시 에러가 남
* console.log 검사를 해보니, {변수} 일 때는 문제가 없는데 {변수}+props.i 나   
백틱 등으로 결합해서 사용하려했을 때 결국 img src="perfume0" 이런식으로 문자처럼 인식이 됨
* src 주소를 데이터 객체에 넣어도 보고, 다양하게 시도해봤으나 계속 오류가 해결이 안됨
* 구글링 끝에 ```<img src={ require('../img/perfume' + props.i + '.jpg').default } alt=""/>``` 이렇게   
require와 default를 사용하여 했을 때 이미지까지 map 반복이 잘됨

</br>


### 4-2. 각종 디버깅
<details>
<summary>라우터 Link 사용시 문제</summary>
<div markdown="1">

```
<span Link to ="/">Home </span>
```

* 실수로 span 태그 안에 Link 를 넣어서 작동 안됨
* ```<Link to ="/"> <span>Home </span> </Link>``` 로 해결

</details>

</br>

<details>
<summary>라우터 사용 관련</summary>
<div markdown="1">

* BrowserRouter 없이 바로 Switch, Route 등을 쓰니 사용할 수 없다는 에러
* BrowserRouter 추가 후 에러 해결

</details>
  
</br>

<details>
<summary>setInterval</summary>
<div markdown="1">

* setInterval을 useEffect 내에 넣어 'Best! 품절 임박' 문구를 주기적으로 깜빡이게 구현하려고함
* 에러가 계속 발생했고, useEffect 밖으로 빼서 사용하는 것도 고민해봤으나   
  구글링 했을 때 React의 기능적인 측면에서 setInterval이 부적합하다는 글이 있었음. 더 공부해봐야 할듯함
* 아쉬운대로 setTimeout으로 설정하고, 작동 초 수가 길기 때문에 안전 장치로 clearTimeout도 추가함

</details>
  
</br>

<details>
<summary>원격 저장소 연결</summary>
<div markdown="1">

* 빌드 파일 만든 후 github 배포하려했으나, 에러 메세지가 뜸
* package.json 파일에 homepage url은 연결했지만 git 원격 저장소 연결을 안함
* ```git remote add origin ~~~```으로 연결 후 재시도 했을 때 제대로 배포됨
  
</details>

</br>

<details>
<summary>메인 페이지가 안 뜨는 문제</summary>
<div markdown="1">

* 배포된 페이지를 봤을 때 HOME 을 누르면 메인 페이지가 뜨지만 접속 당시에는   
  상단 메뉴바 외에 아무 것도 뜨지 않음
* github page 배포는 원칙적으로 SPA를 지원하지 않아서 이와 같이 Router를 사용해서 배포했을 때   
  이런 문제가 자주 발생한다고함
* HashRouter로 바꿔주니 해결됨

</details>

## 5. 회고 / 느낀점
> 첫 프로젝트와 비교했을 때 조금 더 리액트 사용이 손에 익은 것 같았다   
  여전히 더 배워야하지만, 전보다 props 통해서 속성을 전달하거나 Router 사용 그리고   
  Hook 사용에 대해 이해하고 사용한 느낌이 들었다   
  아쉬운 점은, 급하게 만들다보니 CSS를 세밀하게 모듈화하지않고 그냥 진행해서   
  중간중간 스타일이 중복으로 적용되는 바람에 지저분한 className이 많이 들어간 것 같다   
  그리고 서버가 없다보니 json 파일이 아니라 임시 파일로 연결해서 단조롭게 된 것이 아쉽다   
  다음에는 SASS와 Redux를 좀 더 배워서 완성도 있게 만들어 보고싶다




