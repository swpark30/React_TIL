## 리액트 특강



자바스크립트 라이브러리 / 프레임워크



프레임워크

- 뼈대, 기반 구조를 의미 (제어의 역전)



라이브러리

- 단순 활용 가능한 도구 집합
- 사용자가 정의한 클래스 또는 함수에서 호출해서 사용



프레임워크와 라이브러리 차이

- 제어권이 누구에게 있느냐
- 라이브러리 :  사용자가 주도적으로 호출해서 사용



Angular(앵귤러)

- SPA(Single Page Application) 개발을 위한 구글의 클라이언트 측 
  자바스크립트 프레임워크
- 많은 기능 내장
- 타입 스크립트 사용 기반
- MVC 프레임워크를 이용해서 잘 설계되고 구조화된 웹 



Angular 버전

- AngularJS : Angular 1.x버전 : JavaScript
- Angular : Angular 2.x 이상 버전
  - JS 빠짐
  - JavaScript에 국한되지 않는 새로운 프레임워크 제공



SPA(Single Page Application)

- 웹 서비스를 요청할 때마다 서버로부터 페이지 전체를 호출하는 방식이 아니라
  최초 한 번만 페이지 전체를 로딩하고 이후부터는 변경된 데이터만 호출하는 
  방식의 애플리케이션



### Vue

- 입문자가 사용하기에 매우 쉬움
- 앵귤러와 리액트 장점 포함
  - 앵귤러처럼 디렉티브 기능 있고
  - 리액트처럼 버추어 돔 기반 컴포넌트 있음
- CDN으로 불러와서 사용
- html 템플릿 그대로 사용





React 개요

- UI를 쉽게 만들기 위해 페이스북에서 만든 자바스크립트 라이브러리
- 컴포넌트에 집중되어 있는 라이브러리
  - index.html 페이지 1개와 컴포넌트들로 구성
- 앵귤러와 다르게 뷰만 신경쓰고 나머지는 써드파티 라이브러리 필요
- 공식 라이브러리 개념 없음. 여러 가지 솔루션 사용. 생태계 넓고



컴포넌트 (component)

- 동작 가능한 하나의 부품 개념

컴포넌트 역할

- 애플리케이션의 화면을 구성하는 뷰를 생성하고 관리
- 여러 컴포넌트를 조립하여 하나의 완성된 애플리케이션 생성



잘게 나누어진 컴포넌트 모듈(.js)들을 조합해 애플리케이션을 개발하는 오늘날의
개발 접근 방법

- Web Modularity / 컴포넌트 기반 개발
- React가 보편화 시킴



React 특징

- 가장 먼저 가상 돔(Virtual DOM)을 성공적으로 사용
- 이후 다른 많은 라이브러리에서 가상 돔 개념을 채택
- 가상 돔(Virtual DOM)
  - 페이스북에서 리액트를 만들기 전의 발상
    - 브라우저는 돔 기반이기 때문에 데이터가 변경될 때마다 페이지에서
      새로운 뷰를 만들어서 돔을 새로 넣기 때문에 성능적 문제
  - 해결책
    - 변화가 일어날 때마다 실제 돔에 변경된 내용을 넣는 것이 아니라
      자바스크립트로 이루어진 가상의 돔에 한 번 렌더링하고 기존의
      돔과 비교하여 변경된 것만 업데이트



가상돔 변경 과정

- 모델이 있다
- 실제 돔에 그림
- 모델에 변화가 발생하면 (빨간색)
- 가상의 돔에 그림
- 실제 돔과 가상의 돔 비교
- 바뀐 것 찾아내서
- 바뀐 특정 부분에 패치함



리액트 생태계 조성 (가치 사슬, 협력 관계)

- 다양한 생태계를 가지고 있어서
- 좋은 많은 라이브러리들이 만들어지고 널리 사용
- 많은 기업에서 사용 
- 현재 가장 주도적 사용됨



리액트 학습내용

- 설치
- 프로젝트 생성
- 컴포넌트 생성
- 문법 : JSX
- props / state
- 이벤트 처리
- 라우터
- Redux
- 리액트 배포
- 리액트 + 스프링 + MyBatis 연동





리액트 홈 페이지 확인 : https:// reactjs.org

다운로드

- Node.js
  - Chrome V8 JavaScript 엔진 으로 빌드된 JavaScript 런타임
  - 자바스크립트를 웹 브라우저 영역 외에 서버, 모바일 애플리케이션, 
    데스크탑 애플리케이션 등 영역에서 사용 가능하게 해줌
  - React 애플리케이션은 웹 브라우저에서 실행되는 코드이므로 
    Node.js와는 직접적인 연관은 없지만 프로젝트 개발하는데 필요한
    도구들이 Node.js 사용하기 때문에 설치 필요



- NPM (Node Package Manager)
  - 자바스크립트 패키지 관리자 도구
  - Node.js에서 사용할 수 있는 모듈들을 패키지화하여

- Visual Studio Code



Node.js / NPM 설치

- https://nodejs.org
- Long Term Support 



Visual Studio Code 설치

- https://www.visualstudio.com
- 추가 작업 선택 : 모드 체크
- 나머지는 디폴트로 설치
- 설치 후 처음 실행 시 한글 언어팩 설치



npm과  npx 차이

- npm : 프로그램을 설치하는 프로그램
- npx
  - create-react-app 이라는 프로그램을 임시로 한 번만 실행시키고 지운다는 개념
  - 장점
    - 컴퓨터 공간을 낭비하지 않음
    - 설치 실행할 때마다 새로 다운로드 하기 때문에 항상 최신 상태



프로젝트 생성

- reactWorkspace 폴더 생성 
- VScode : 터미널 / 새 터미널
- reactWorkspace로 이동
  - cd c:\reactWorkspace
- 프로젝트 생성
  - npx create-react-app 프로젝트명
  - npx create-react-app my-app
  - my-app 폴더로 이동 : cd my-app
  - 프로젝트 실행 : npm start
  - 실행 종료 : Ctrl + C
- 프로젝트 구성 
- index.html : `<div id="root">` 여기에 렌더링
- index.js: 앱의 진입점 역할
- App.js : 기본 컴포넌트
- 우리가 할일
  - 컴포넌트 추가
    1. App.js에 추가해도 되고
    2. 별도 파일로 추가 (.js 생성)
  - App.js 컴포넌트에 새로 추가한 컴포넌트 추가
- 클래스 기반 vs 함수 기반 컴포넌트
  - 함수기반 컴포넌트 사용
  - 요즘은 대부분 함수 기반 컴포넌트 사용



컴포넌트 추가

1. App.js에 함수형 컴포넌트 3개 추가
   - 화면에 출력
2. 각 컴포넌트를 js 파일로 분리
   - 앞으로는 이 방법 사용
   - src 폴더 안에 components 폴더 생성
   - Subject.js 생성
     - App.js에서 잘라내서 붙여넣기
   - NAV.js 생성
     - App.js에서 잘라내서 붙여넣기
   - Coneten.js 생성
     - App.js에서 잘라내서 붙여넣기
   - App.js에서 각 컴포넌트 import



컴포넌트 생성 시 주의점

- 컴포넌트 이름은 대문자로 시작

- 반드시 return 포함

- return 안에는 반드시 하나의 최상위 태그로 시작해야함

  - 오류나는 경우

    - `<div></div>`
    - `<div></div>`

  - 모든 태그는 최상위 태그 내에 포함

    - ```
      <div>
      	<div></div>
      	<div></div>
      	<div></div>
      </div>
      ```

    

태그의 클래스 속성 설정시 주의

- class가 아니라 className 사용
- `<div className="nav">`



리액트 문법 : JSX

- 자바스크립트 + XML 확장된 문법
- HTML과 유사하지만 다름
- class 대신 className 사용
- 최상위 태그 사용
- 변수 선언 / 사용 방법
- if문 사용
- 인라인 스타일링 : 카멜 표기법
- 꼭 닫아야 하는 태그
- 주석 
- 사용자 정의 객체(변수) 사용



my-app에 문법 연습용 컴포넌트 추가 : JSX.js



props 

- 컴포넌트의 속성 (값 설정)

- 부모 컴포넌트에서 자식 컴포넌트로 값을 전달할 때 사용(읽기 전용)

- 컴포넌트 렌더링할 때 값을 전달해 주고 싶을 때 사용

- 부모 컴포넌트 : App.js

  - 값을 직접 보내도 되고, 변수의 값을 보내도 됨
  - `<Subject title="제목"></Subject>` 
  - 또는
  - let title = "제목";
  - `<Subject title={title}></Subject>` 

- 자식 컴포넌트에서 받음: Subject.js

  - ```
    const Subject = (title) => {
    	{title}
    }
    ```



프로젝트 생성: props-app

- Subject.js 컴포넌트 



이미지 출력

1. public 안에 assets 폴더 생성하고 이미지 파일 저장
   - js파일에서 기본으로 public 경로 찾아감
2. src 폴더 안에 images 폴더에 이미지 저장하고 import 해서 사용



state

- 변수 (변경 가능)
- 컴포넌트 내부에서 변경될 수 있는 값
- 이 값이 변경될 때 리 렌더링 됨
- 함수형 컴포넌트에서는 useState() 함수 사용해서 state 값 변경
- Hooks
  - 기존의 함수형 컴포넌트에서 할 수 없었던 다양한 기능을 제공
  - useState(): 상태 관리
  - useEffect(): 렌더링 직후 작업 설정

- useState() 사용법
  - import React, {useState} from 'react';
  - const[state명(변수명), setter함수명] = useState(초기값);



