# React_TIL_Day_02



이벤트 처리

- 이벤트 처리 시 주의점
  - 이벤트 이름은 카멜 표기법으로 사용 : onClick, onKeyUp
  - 이벤트에 함수 형태의 값 전달
    - onClick = {onClickEnter}
  - DOM 요소에만 이벤트 설정 가능
    - 사용자가 직접 만든 컴포넌트에는 이벤트 설정 불가
    - 예 : MyComponent에 onClick 설정 시
    - `<MyComponent onClick={doSomthing} />`
    - 클릭 시 doSomthing() 함수를 호출하는 것이 아니라 (속성) 이름이
      onClick인 props를 MyComponent 컴포넌트에 전달하는 것
    - 전달받은 props를 컴포넌트 내부의 DOM 이벤트로 설정
    - `<div onClick={props.onClick}></div>`



`<input>` 태그의 입력 값 처리 이벤트

- onChange 이벤트 발생
- 입력된 값 : e.target.value



`<input>` 태그의 onChange 예제

- `<input>` 태그에 입력된 값으로 다른 state 값 변경
  - 입력된 값으로 제목 변경



state를 배열로 사용

- ```
  const [titles, setTitles] = useState([
  	"지금 우리 학교는",
  	"오징어 게임"
  ]);
  
  titles[0], titles[1]
  ```

- 배열 출력 : map() 사용

  - 배열 내장 함수

  - 각 배열의 요소에 대해 처리된 새로운 결과를 새로운 벼열에 담아 반환하는 함수

  - value, index 전달

  - ```
    titles.map((title, index) => (
    	<p>{title}</p>
    ))
    ```



자바스크립트 스프레드 연산자 : ...

- 기존값 유지
- 기존배열에 새 항목 추가
- 객체나 배열의 값을 복제할 때 사용
- [...기존배열, 새항목]
- newArr = oldArr; // newArr 변경하면 oldArr도 변경
- newArr = [...oldArr]; // oldArr 기존값 유지



배열 내장 함수 filter() 함수

- 컴포넌트에서 배열의 불변성을 유지하면서 배열 원소를 제거해야 할 경우 사용
- 기존의 배열은 그대로 둔 상태에서 특정 조건을 만족하는 원소들만 따로
  추출하여 새로운 배열 생성
- 조건을 확인하는 함수를 파라미터로 설정
- 이 함수에서 true를 반환 



라우팅 (Routing)

- URL에 따라 해당 화면 출력 가능 (링크)

- 다른 주소에 다른 화면을 보여주는 것

- 리액트 라이브러리 자체에 라우팅 기능이 내장되어 있지 않지만
  리액터 라우터 라이브러리를 사용하여 쉽게 구현 가능

- react-router-dom 라이브러리 설치

- index.js에서

  - import {BrowserRouter} from 'react-router-dom';

  - 기존

    - ```
      <React.StrictMode>
          <App />
      </React.StrictMode>
      ```

  - BrowerRouter로 변경

    - ```
      <BrowerRouter>
          <App />
      </BrowerRouter>
      ```

  - Router 컴포넌트로 특정 주소에 컴포넌트 연결

    - ```
      <Routes>
          <Route path="/" component={Home}/>
          <Route path="/about" component={About}/>
      </Routes>
      
      <Link to="/about">About 화면 보기</Link>
      ```

    - import {Link, Routes, Rout} from 'react-router-dom';



npm install react-router-dom 으로 설치



components 폴더 안에 컴포넌트 생성



Link 컴포넌트를 사용하여 다른 주소로 이동

- 리액터 라우터를 사용할 때는 `<a>`태그 사용하지 못함
  - `<a>` 태그는 페이지 전환 과정에서 페이지를 새로 불러오기 때문에 
    애플리케이션이 갖고 있던 상태들이 모두 없어짐
  - 렌더링 컴포넌트도 모두 사라지고 다시 처음부터 렌더링함
- `<Link>` 태그 사용
  - 페이지를 새로 불러오지 않고 애플리케이션을 그대로 유지한 상태에서 
    페이지 









path를 통해 파라미터 전달

- MovieDetail.js