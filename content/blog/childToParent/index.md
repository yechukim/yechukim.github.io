---
title: children에서 parent 컴포넌트 컨트롤하기 (feat.콜백 함수)
date: "2021-10-11"
description: "하위 컴포넌트에서 상위 컴포넌트 컨트롤하기"
---
## Children ---> Parent

하지만 프로젝트 도중 child 컴포넌트에서 parent를 컨트롤 해주어야 하는 경우가 생겼다. 물론 parent에서 상태관리를 하고 이를 child에게 넘겨주는 것이 the best way 겠지만, 현재로서 전체를 바꾸기에는 무리가 있어서 어쩔 수 없이 child에서 parent를 컨트롤 하기로 했다.

## callback 넘겨주기
parent 컴포넌트에서 callback을 child 에 넘겨주고, child 컴포넌트에서 해당 콜백에 값을 넣어주어 parent에 정의한 상태를 set해주면 된다.

내 코드의 예시를 보면 다음과 같다.
parent 컴포넌트에 다음과 같이 정의한다고 생각해보자. child 컴포넌트에 callback을 넘겨준다(onPermission)

```jsx
//parent 
const [permission, setPermission] = useState(false)
...
const onPermission = (value) => {
  setPermission(value)
}
...
<MyChildComponent onPermission={onPermission}>

```
그리고 child 컴포넌트에서는 다음과 같이 쓸 수 있다. 
```jsx
//child
const MyChildComponent = ({onPermission}) => {

  useEffect(()=> {
    onPermission(true)
  },[])

}

```
그러면 처음에 부모 컴포넌트에서는 false였던 permission이 child component의 useEffect에서 넣어준 값을 통해 `setPermission(true)`가 되어 permission 이 true로 변하게 된다.

