# Redux


### 목차
 1. 리덕스란 
 2. 리덕스 스토어
 3. Reducer
 4. 액션(Action)


------------
### 1) 리덕스란   
리덕스는 리액트 컴포넌트의 state 전달 방식의 문제점을 해결하기 위해 만들어졌다.   
프로젝트가 커지면서 컴포넌트수 와 state 도 많아지기 마련이다.   
state는 부모 컴포넌트로 부터 상속 받아 전달된다.   
프로젝트가 커지면서 부모 컴포넌트에 상속받는 자식 컴포넌트가 많아지면서 전달하기 위해 불필요한 상속이 생긴다.   
그런 불필요한 상속을 더욱 쉽고 심플하게 리덕스는 state 를 전달할수있다.   
-----------
### 2) 리덕스 스토어
리덕스 스토어는 기존 방식에 컴포넌트 전달 방식이 아닌 리덕스 스토어 하나에서 모든 state를 관리하며 컴포넌트에 원하는 상태값과 함수를 뿌려준다.     
#### 기존 방식과의 차이점
1. 리덕스 스토어는 글로벌 상태관리이면 기존 방식은 로컬방식 이라고 할수있다.
--------------
### 3)Reducer

  ```js
  const INITIAL_STATE = {
  currentState: null, //초기화
};

const Reducer = (state = INITIAL_STATE, action) => {
  switch (action.type) {
    case "ReducerTypeCheck":
      return {
        ...state,
        currentState: action.payload,
      };

    default:
      return state;
  }
};

export default Reducer;
```
---------
### 4)액션(Action)
액션은 state의 변화방식을 알려주는 인자이다.     
User > Application > Action > Store   
기본적으로 redux의 state는 불변이기 때문에   
action을 통해 이전 state에 추가하는 방식이다.   
