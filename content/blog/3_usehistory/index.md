---
title: useHistory로 이동시 state 값 넣기, useLocation 의 사용 
date: "2022-09-12"
description: "useHistory 이용시 useLocation을 사용하여 상태값에 접근할 수 있다."
---

## useHistory & useLocation
개발중에 useHistory를 사용하여 `history.push()`안에 path를 넣어 이동하고 있었다. 
이동시에 전달해주고 싶은 값이 있어서 방법을 찾아보았다.
일반적으로는 다음과 같이 코드를 작성했다.
```js 
const history = useHistory()
history.push('/main')
```

이때 상태도 전달할 수 있는데 다음과 같이 path를 그냥 넣어주지 않고, 
pathname과 state를 넣어주기만 하면 된다.
```js 
const history = useHistory()
history.push({
  pathname:'/main',
  state: {
    user_id: userId
  }
})
```
그러면 `/main` 페이지에서는 어떻게 상태값에 접근할 수 있을까?
```js
const location = useLocation() 
const useid = location.sate.user_id 

```

이렇게 접근해서 사용할 수 있다 :tada:


