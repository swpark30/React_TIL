# React_TIL_Day_03





Redux를 사용하지 않고 하위 컴포넌트 값 변경하는 예제

- 

- 프로젝트 : no-redux-app
- Left1.js
- Left2.js
- Left3.js
- Right1.js
- Right2.js
- Right3.js
- 



Redux를 사용하지 않은 경우

- 상위 컴포넌트에서 하위 컴포넌트로 props를 통해 state값과 함수명 전달
- 하위 컴포넌트에서 상위 컴포넌트로 prop를 통해 함수 호출 전달



Redux : 리덕스

- 리액트 state (상태) 관리 라이브러리
- 가장 많이 사용됨
- 전역 상태를 관리할 때 매우 효과적
- (Context API 사용해서 전역 상태 관리 가능)
  - 별도의 라이브러리 설치하지 않고 전역 상태 관리
  - Context를 만들어 한 번에 원하는 값을 받아와서 사용
- 컴포넌트들 사이에서 동일한 state를 공유해야할 경우 유용
- 다른 컴포넌트를 거치지 않고 state 값을 가져와서 사용하거나 업데이트 가능
- 리액트 뿐 아니라 HTML, JavaScript에서 사용 가능
- 스토어 안에 state 저장하고 컴포넌트들이 구독
- 상태 변화가 생기면 구독 중인 컴포넌트에 통보



Redux 장점

- 유지보수성 높고, 작업 효율성 극대화
- 편리한 개발 도구 지원
- 체계적으로 상태 관리가능하기 때문에 프로젝트 규모가 큰 경우 사용
- 미들웨어 기능 제공하여 비동기 작업을 효율적으로 관리 가능



Redux 개념

- 스토어 
  - state 저장
  - 프로젝트에 리덕스를 적용하기 위해 사용
  - state를 수시로 확인해서 View에게 변경된 사항을 알려주는 역할
  - 한 개의 프로젝트에는 하나의 스토어만 존재
- 리듀서 (reducer)
  - state를 변경하는 함수
  - 전달받은 액션에 따라 새로운 상태를 만들어서 스토어에게 전달
  - 2개의 파라미터를 받음 (현재 state와 action)
  - 즉, 현재의 state 값을 어떻게 바꿀 것인지(action)에 대한 요청 처리
  - 두 값을 참고해서 새로운 상태를 만들어서 반환
    - state 변경하고 변경된 값 반환
- 디스패치
  - 스토어의 내장 함수
  - 액션 발생시키는 역할 (트리거 역할)
    - 리듀서에게 액션을 발생하라고 시키는 역할
    - 액션 객체를 파라미터로 전달
  - 디스패치 함수가 호출되면 스토어는 리듀서 함수를 실행시켜서 새로운
    상태를 만듬
- 액션
  - state에 일어나는 변화(동작)에 대해 선언되는 객체
  - type 필드 필수
  - if(action.type === "PLUS") 더하기 수행



Redux 사용

- Redux 라이브러리 설치
  - 현재 버전이 Redux 4.2 버전 설치되는데
  - createStore가 configureStore로 변경 (복잡)
  - 버전 낮춰서 설치 : 4.12버전으로 설치
  - npm install redux@4.1.2 react-redux
  - react-redux : redux와 react를 연결하는 도구
- 스토어 생성
- 리듀서 함수로 만들어서 사용
- useSelector, useDispatch



Redux 예제

- 프로젝트 : redux-app
- redux와 react-redux 라이브러리 설치
- Left ~ Right 컴포넌트 복사해서 수정



작성 순서

1. store 생성하고 `<Provider>` 지정
   - index.js에서 지정 (App.js에서 해도 됨)
2. 리듀서 생성
   - 함수로 생성 : reducer.js
   - function reducer(currentState, action) {}
3. count 값 출력할 Left3에 count 정의
   - useSelector() 사용
4. 버튼 클릭 시 값 변경
   - Right3 버튼에 이벤트 설정하고
   - 리듓에서 state 값 변경하도록 함
   - 디스패치를 통해서 액션 전달 : type 설정
   - useDispatch() 사용



리액트 + 스프링 + DB 연동 (MyBatis)

- 리액트 + 스프링 연결 테스트
- 백엔드 프로그램 준비
  - spring_boot_mybatis의 product 관리 코드 사용
  - 컨트롤러만 새로 작성(기존 컨트롤러 코드 복사해서 일부 수정)
  - Service / DAO / VO / Mapper 그대로 사용
- 리액트 홈/메뉴 작성
  - 라우팅 기능 추가
- 리액트에서 스프링 백엔드를 통한 CRUD 기능 구현



1. 리액트 + 스프링 연결 테스트
   - 스프링 부트 프로젝트 생성
     - @RestController인 ReactController 생성
   - 리액트 프로젝트 생성
     - axios로 http://localhost:8080 접속해서 결과 받아서 출력
     - 오류 발생(CORS 오류)
       - 리액트 3000 포트 사용 스프링 8080 포트 사용하는 다른 사이트
     - 오류 해결 : WebConfig.java 설정
   - 실행해서 오류없이 반환 값 잘 받아오는지 확인



비동기 작업

- 네트워크 송수신 과정에서 시간이 걸리기 때문에 작업을 즉시처리하지 못하고
  응답을 기다렸다가 전달받은 데이터를 처리하는 방식
- 시간이 많이 걸리는 작업
  - 서버로부터 데이터를 요청하고 기다리는 작업
- 서버에게 API 호출해서 결과를 수신
- 이런 과정에서 해당 작업을 비동기적으로 처리



콜백 지옥 (Callback Hell)

- 비동기 호출이 자주 일어나는 프로그램에서 발생하는 문제
- 함수의 매개변수가 전달되는 콜백 함수가 반복되어서 코드 들여쓰기 수주의
  깊이가 무한 반복되는 경우
- 해결 방안 : Promise 사용
  - 비동기 메소드에서 동기 메소드처럼 값을 반환해서 비동기 연산이 종료된
    이후의 결과 값을 처리하기위한 처리기를 



Axios 

- 자바스크립트 라이브러리 중 하나인 Fetch API와 같은 비동기 통신 라이브러리
- 리액트에서는 Axios를 더 많이 사용
- Promise 기능을 쉽게 해주는 문법으로 async / await 사용
- 이렇게 하면 Promise 끝날 때까지 기다리고, 결과값을 특정 변수에 저장할 수
  있음



async : 함수 앞에 붙여 사용

- async를 사용하게 되면 함수를 항상 Promise를 반환



await

- async 함수 안에서만 사용 가능
- 함수 안에서 await을 만나면 Promise가 처리될 때까지 대기
- await을 이용하면 콜백함수 처리 없이 비동기 처리 가능



useEffect()

- 컴포넌트가 렌더링될 때마다 특정 작업을 수행 하도록 설정할 수 있는 Hook
- 설정한 함수를 컴포넌트가 화면에 맨 처음 렌더링 할 때만 실행하고 없데이트
  될 때는 실행하지 않으려면, 두 번째 파라미터를 빈 배열 사용 ([])
- 렌더링될 때 한 번만 호출
- 서버를 호출하거나 컴포넌트가 마운트되면서 1회만 수행되는 동작이 필요할 
  때 사용



CORS 오류

- Cross-Origin Resource Sharing
- 추가 HTTP 헤더를 사용해서
- 한 출처(origin)에서 실행 중인 웹 애플리케이션이 다른 출처(origin)의 선택한
  자원에 접근할 수 있는 권한을 부여하도록 브라우저에게 알려주는 체제



2. 백엔드 프로그램 준비
   - spring_boot_mybatis의 product 관리 코드 사용
   - 컨트롤러만 새로 작성(기존 컨트롤러 코드 복사해서 일부 수정)
   - Service / DAO / VO / Mapper 그대로 사용
3. ㅇㅇㅇ
4. 리액트에서 스프링 백엔드를 통한 CRUD 기능 구현
   - 상품 정보 조회
     - `<ProductList>`
     - `<ProductListItem>` : 행 (반복 : map() 안에서)
     - 스프링에 컨트롤러 추가
     - 리액트에서 `<ProductList>` 컴포넌트 생성
   - 상품 상세 정보 조회 : `<ProductDetailView>`
   - 상품 정보 등록 : 
   - 상품 정보 수정 : 



